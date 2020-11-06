---
title: Export and print the Schedule with its appointments	
description: Export/Print the complete Scheduler or specific appointment alone
platform: ReactJS
control: schedule
documentation: ug
keywords: export, import and print 
---
# Export and Print

## Export Appointments to ICS file

The Appointments can be exported as a whole collection or else a single appointment alone can be exported from the Scheduler. By default, the appointments are exported to .ics format which can then be imported and used in any of the other external calendars.

### Single Appointment Exporting

A single appointment can be exported by making use of its Id. You can achieve this functionality by making use of an [exportSchedule](/api/js/ejschedule#methods:exportschedule) method by passing the id of an appointment to export as one of its parameter.

It can also be achieved in another way by enabling the context menu settings and then adding a custom menu option for export appointment functionality. When right clicked on an appointment, and **export Appointment** option is chosen, the exporting functionality can be handled through the [menuItemClick](/api/js/ejschedule#events:menuitemclick) event, within which the **exportSchedule** method should be defined with the following parameters,

* Action name (to be called in the server-side)
* Server Event (optional)
* Appointment Id (mandatory for single Appointment exporting)

The following code example shows the way to export single appointment from the Scheduler.

{% highlight html %}

var dManager = [{
    Id: 100,
    Subject: "Wild Discovery",
    StartTime: new Date(2015, 11, 2, 9, 00),
    EndTime: new Date(2015, 11, 2, 10, 30),
    Location: "CHINA"
}];

var contextMenuData = {
    enable: true,
    menuItems: {
        appointment: [
            { id: "open", text: "Open Appointment" },
            { id: "delete", text: "Delete Appointment" },
            { id: "export", text: "Export Appointment" }
        ]
    }
};

var Scheduler = React.createClass({
    onMenuItemClick: function(args) {
        if (args.events.ID == "export") {
            var obj = $("#Schedule1").data("ejSchedule");
            // exportSchedule() method will send a post to the server-side to call a specified action.
            obj.exportSchedule("ExportToICS", null, args.targetInfo.Id);
        }
    },
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" currentDate={new Date(2017, 5, 5)} contextMenuSettings={contextMenuData} menuItemClick={this.onMenuItemClick} appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

N> The Id value of the appointment passed in the above code example can be retrieved in the server-side action through Request.Form["AppointmentId"], as the id passed from the script is stored as hidden value in the input field of the form under this name internally.

### Exporting all Appointments

To export the entire Scheduler appointments, the same [exportSchedule](/api/js/ejschedule#methods:exportschedule) method can be used without passing the id value to its parameter list. To achieve this, keep an individual button to export, and when it is clicked - the Scheduler can be allowed to export all the appointments.

The following code example depicts the way to export all the Scheduler appointments as a whole.

{% highlight html %}

<!--Container for ejScheduler widget-->
<div id="schedule-default"></div>

<!-- Button div for Export Option-->
<button id="exportButton">Export</button>

{% endhighlight %}

{% highlight html %}

var dManager = [{
    Id: 100,
    Subject: "Wild Discovery",
    StartTime: new Date(2015, 11, 2, 9, 00),
    EndTime: new Date(2015, 11, 2, 10, 30),
    Location: "CHINA"
}];

var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" currentDate={new Date(2017, 5, 5)} width="100%" height="525px" appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

var Button = React.createClass({
    onClick: function(args) {
        var obj = $("#Schedule1").data("ejSchedule");
        // Calls the server-side action ExportToICS
        obj.exportSchedule("ExportToICS", null, null);
    },
    render: function () {
        return (
            <EJ.Button id="btnExport" width="70px" height="30px" click={this.onClick}>
            </EJ.Button>
       );
    }
});

ReactDOM.render(<Button />, document.getElementById('exportButton'));
ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

The server-side action **ExportToICS** contains the following code example to export the Scheduler appointments.

{% highlight c# %}

public void ExportToICS(FormCollection form)
{
    IEnumerable data;
    string JSONModel = Request.Form["ScheduleModel"];
    var model = JsonConvert.DeserializeObject<Dictionary<string, object>>(JSONModel);
    var Id = Request.Form["AppointmentId"];
    if(Id != null)
        data = db.DefaultSchedules.Where(app => app.Id.ToString() == Id.ToString()).ToList(); // To export single appointment
    else
        data = db.DefaultSchedules.ToList();  // To export all the appointments
    ScheduleExport obj = new ScheduleExport(model, data);
}

{% endhighlight %}

## PDF Export

Scheduler supports exporting it along with all its appointments in PDF format, for which the same [exportSchedule](/api/js/ejschedule#methods:exportschedule) method can be used without passing any id value to its parameter list. To achieve this, keep an individual button to export and when it is clicked, the Scheduler with appointments can be allowed to export as PDF.

The following code example depicts the way to export the Scheduler with appointments in PDF format.

{% highlight html %}

<!--Container for ejScheduler widget-->
<div id="Schedule1"></div>

<!-- Button div for Export Option-->
<button id="btnExport">Export</button>

{% endhighlight %}

{% highlight html %}

var dManager = [{
    Id: 100,
    Subject: "Wild Discovery",
    StartTime: new Date(2015, 11, 2, 9, 00),
    EndTime: new Date(2015, 11, 2, 10, 30),
    Location: "CHINA"
}];

var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" currentDate={new Date(2017, 5, 5)} width="100%" height="525px" appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

var Button = React.createClass({
    onClick: function(args) {
        var obj = $("#Schedule1").data("ejSchedule");
        obj.exportSchedule("http://js.syncfusion.com/ejservices/api/Schedule/PdfExport", null, null);
        args.cancel = true;
    },
    render: function () {
        return (
            <EJ.Button id="btnExport" width="70px" height="30px" click={this.onClick}>
            </EJ.Button>
       );
    }
});

ReactDOM.render(<Button />, document.getElementById('exportButton'));
ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

The server-side action **PDFExport** contains the following code example to export the Scheduler.

{% highlight c# %}

public ActionResult PDFExport(string scheduleModel)
{
    PdfExport exp = new PdfExport();
    JavaScriptSerializer serializer = new JavaScriptSerializer();
    SchedulePDFExport convert= new SchedulePDFExport();
    // Here calling the public method to convert the model values to ScheduleProperties type from string type
    ScheduleProperties scheduleObject = convert.ScheduleSerializeModel(scheduleModel);
    // Here converting the schedule appointments data into enumerable object by deserializing
    IEnumerable scheduleAppointments = (IEnumerable)serializer.Deserialize(Request.Form["ScheduleProcesedApps"], typeof(IEnumerable));
    // Here passing the theme values from enum collection
    PdfDocument document = exp.Export(scheduleObject, scheduleAppointments, ExportTheme.FlatSaffron,Request.Form["locale"]);
    document.Save("Schedule.pdf", HttpContext.ApplicationInstance.Response, HttpReadType.Save);
    return RedirectToAction("PDFExportController");
}

{% endhighlight %}

N> To pass the theme value as a string instead of the enum value, refer to the following code example of passing the string type theme value.
{% highlight c# %}
    PdfDocument document = exp.Export(scheduleObject, scheduleAppointments, "flat-saffron",Request.Form["locale"]);
{% endhighlight %}

### Setting Page Options

It is possible to set/change the PDF page settings such as size, margins (left, right, top and bottom), transition, and rotate angle and header/footer values by passing the page settings and page document template object values into the export method.

#### Page Settings

You can set/apply the following page property values to the PDF file before exporting it with the Scheduler by using the `PdfPageSettings` object.

a) Page Size
b) Orientation
c) Margins ( Left, Right, Top, Bottom)
d) Transition ( Direction, Dimension, Duration, Motion, PageDuration, Scale, Style)
e) Rotate ( RotateAngle0, RotateAngle90, RotateAngle180, RotateAngle270)
f) Height
g) Width

To apply the above page setting values, you need to create an object for the `PdfPageSettings` class. Then, you can assign the values to the available properties within it such as Size = PdfPageSize.A3, Orientation = PdfPageOrientation.Landscape and so on. Once done, pass this object into the export method which will set these page settings values to the PDF file before exporting it. Refer to the following code example (server-side) to set/change the page settings values.

{% highlight c# %}

public ActionResult PDFExport(string scheduleModel)
{
    JavaScriptSerializer serializer = new JavaScriptSerializer();
    SchedulePDFExport convert= new SchedulePDFExport();
    ScheduleProperties scheduleObject = convert.ScheduleSerializeModel(scheduleModel); // Here calling the public method to convert the model values to ScheduleProperties type from string type

    IEnumerable scheduleAppointments = (IEnumerable)serializer.Deserialize(Request.Form["ScheduleProcesedApps"], typeof(IEnumerable)); // Here deserialize the appointments to enumerable object

    PdfExport exp = new PdfExport();

    // Here the 50f is the default value for the margins. If you are not assigning any separate values like Margins.Left = 15 means 50f value will be setting to all the Margin properties.
    PdfPageSettings pageSettings = new PdfPageSettings(50f);

    // Here you can assign the PdfPageSize enum value (ex: A3, A4)
    pageSettings.Size = PdfPageSize.A3;

    // Here Landscape value assigned to the orientation. You can set either Landscape/Portrait for this Orientation property
    pageSettings.Orientation = PdfPageOrientation.Landscape;

    // Here assigned different values for the margins
    pageSettings.Margins.Left = 15;

    pageSettings.Margins.Right = 15;

    pageSettings.Margins.Top = 20;

    pageSettings.Margins.Bottom = 20;

    // Here assigned the Transition Direction as BottomToTop. You can also set any of the Transition values to this property
    pageSettings.Transition.Direction= PdfTransitionDirection.BottomToTop;

    // Here assigned the Rotate Angle as RotateAngle180. You can also set any of the Rotate values to this property
    pageSettings.Rotate = PdfPageRotateAngle.RotateAngle180;

    // Here passing the page settings object value into the export method.
    PdfDocument document = exp.Export(scheduleObject, scheduleAppointments, ExportTheme.FlatSaffron, Request.Form["locale"], pageSettings);
    document.Save("Schedule.pdf", HttpContext.ApplicationInstance.Response, HttpReadType.Save);
    return RedirectToAction("PDFExportController");
}

{% endhighlight %}

#### Header/Footer Settings

You can also set the header and footer options to the PDF page before it is being exported, by passing the `PDFDocumentTemplate` object values as mentioned in the following code example.

{% highlight c# %}

public ActionResult PDFExport(string scheduleModel)
{
    JavaScriptSerializer serializer = new JavaScriptSerializer();
    SchedulePDFExport convert= new SchedulePDFExport();
    ScheduleProperties scheduleObject = convert.ScheduleSerializeModel(scheduleModel); // Here calling the public method to convert the model values to ScheduleProperties type from string type

    IEnumerable scheduleAppointments = (IEnumerable)serializer.Deserialize(Request.Form["ScheduleProcesedApps"], typeof(IEnumerable)); // Here deserialize the appointments to enumerable object
    PdfExport exp = new PdfExport();
    PdfDocument document = new PdfDocument();
    PdfPage pdfPage = document.Pages.Add();

    //Create a header and draw the string.
    // Here the bounds value is used to store the position/axis value, where the header and footer content to be displayed
    RectangleF bounds = new RectangleF(0, 0, document.Pages[0].GetClientSize().Width, 50);

    // Creating object for the PdfPageTemplateElement
    PdfPageTemplateElement header = new PdfPageTemplateElement(bounds);

    // Here setting the font style and color to display the header/footer content
    PdfSolidBrush brush = new PdfSolidBrush(Color.Gray);

    PdfFont font = new PdfStandardFont(PdfFontFamily.Helvetica, 6, PdfFontStyle.Bold);

    PdfStringFormat format = new PdfStringFormat();

    format.Alignment = PdfTextAlignment.Center;

    format.LineAlignment = PdfVerticalAlignment.Middle;

    header.Graphics.DrawString("Schedule", font, brush, new RectangleF(0, 18, header.Width, header.Height), format);

    //Create a Page template that can be used as footer (here creating template to display the page number).
    PdfPageTemplateElement footer = new PdfPageTemplateElement(bounds);

    //Create page number field.
    PdfPageNumberField pageNumber = new PdfPageNumberField(font, brush);

    //Create page count field.
    PdfPageCountField count = new PdfPageCountField(font, brush);

    //Add the fields in composite fields.
    PdfCompositeField compositeField = new PdfCompositeField(font, brush, "Page {0} of {1}", pageNumber, count);

    compositeField.Bounds = footer.Bounds;

    //Draw the composite field in footer.
    compositeField.Draw(footer.Graphics, new PointF(470, 40));

    PdfDocumentTemplate headerFooterTemplate = new PdfDocumentTemplate();

    //Here assigning the header template value to the PdfDocumentTemplate Object.
    headerFooterTemplate.Top = header;

    //Here assigning the footer template value to the PdfDocumentTemplate Object.
    headerFooterTemplate.Bottom = footer;

    //Here passing the PdfDocumentTemplate Object value into the export method.
    document = exp.Export(scheduleObject, scheduleAppointments, ExportTheme.FlatSaffron, Request.Form["locale"], headerFooterTemplate);
    document.Save("Schedule.pdf", HttpContext.ApplicationInstance.Response, HttpReadType.Save);
    return RedirectToAction("PDFExportController");
}

{% endhighlight %}

N>The header and footer values can be passed to the PDF file only through the template option. In the above mentioned code example, the template has been written with the text “Schedule” to display it as the header text and the page number (ex: Page 1 of 2) has been displayed in the footer part.

It is also possible to pass both the `PageSettings` and header/footer template objects in the export method altogether to apply the page settings as well as the header and footer options to the PDF file which can be referred from the following code example,

{% highlight c# %}

public ActionResult PDFExport(string scheduleModel)
{
    //Here add the code example of both the page settings and header/footer values settings.
    //Then pass both PdfPageSettings and PdfDocumentTemplate object into the export method.

    document = exp.Export(scheduleObject, scheduleAppointments, ExportTheme.FlatSaffron, Request.Form["locale"], pageSettings, headerFooterTemplate);
    document.Save("Schedule.pdf", HttpContext.ApplicationInstance.Response, HttpReadType.Save);
    return RedirectToAction("PDFExportController");
}

{% endhighlight %}

## Excel Export

Scheduler supports exporting all or simply the current view appointments in an Excel format, for which the [exportToExcel](/api/js/ejschedule#methods:saveasexcel) method is used. To showcase this functionality, here we have kept an individual button to export and therefore when it is clicked, the appointments are allowed to export to a Excel format file.

In [exportToExcel](/api/js/ejschedule#methods:exportToExcel) method, we can pass three arguments as follows:

* Action name (to be called in the server-side)
* Server Event (Optional)
* Appointment export type (Either to include or exclude the occurrence appointments)

The appointments with additional fields can also be exported based on the number of new fields added to specific class. For this, we should create a class with specific fields to be exported and based on that class, object can be deserialized and passed for exporting.

The following code example depicts the way to export the appointments in an Excel format.

{% highlight html %}

<!--Container for ejScheduler widget-->
<div id="Schedule1"></div>

<!-- Button div for Export Option-->
<button id="btnExport">Export</button>

{% endhighlight %}

{% highlight html %}

var dManager = [{
    Id: 100,
    Subject: "Wild Discovery",
    StartTime: new Date(2015, 11, 2, 9, 00),
    EndTime: new Date(2015, 11, 2, 10, 30),
    Location: "CHINA"
}];

var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" currentDate={new Date(2017, 5, 5)} width="100%" height="525px" appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

var Button = React.createClass({
    onClick: function(args) {
        var obj = $("#Schedule1").data("ejSchedule");
        obj.exportToExcel("http://js.syncfusion.com/ejservices/api/Schedule/XlsExport", null, false);
        args.cancel = true;
    },
    render: function () {
        return (
            <EJ.Button id="btnExport" width="70px" height="30px" click={this.onClick}>
            </EJ.Button>
       );
    }
});

ReactDOM.render(<Button />, document.getElementById('exportButton'));
ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

The server-side action **XlsExport** contains the following code example to export the Scheduler.

{% highlight c# %}

public ActionResult XlsExport()
{
    List<AppointmentData> scheduleAppointments = (List<AppointmentData>)JsonConvert.DeserializeObject(Request.Form["ScheduleAppointment"], typeof(List<AppointmentData>));
    ExcelExport xlExport = new ExcelExport();
    return xlExport.Export(scheduleAppointments, ExcelVersion.Excel2013);
}

public class AppointmentData
{
    public int Id { get; set; }
    public string Subject { get; set; }
    public string StartTime { get; set; }
    public string EndTime { get; set; }
    public bool AllDay { get; set; }
    public bool Recurrence { get; set; }
    public string RecurrenceRule { get; set; }
}

{% endhighlight %}

In Export method, the appointments are mandatory to be passed as a first argument. In addition, we can also pass the specific filename (on which the exported file should be saved in the machine) and excel version as optional parameters, to export the file on specified filename and version.

## Print

Two types of Print options are available – either to print the entire Scheduler layout including all the appointments in it or else to print any particular appointment alone. The public method [print](/api/js/ejschedule#methods:print) is used to print the entire Scheduler.

### Print the Scheduler

The following code example shows the way to print the entire Scheduler, by keeping an extra button in a page – on which clicking the button will print the entire Scheduler.

{% highlight html %}

<!--Container for ejScheduler widget-->
<div id="Schedule1"></div>

<!--Button div for Print Option-->
<button id="exportButton">Print</button>

{% endhighlight %}

{% highlight html %}

var dManager = [{
    Id: 100,
    Subject: "Wild Discovery",
    StartTime: new Date(2015, 11, 2, 9, 00),
    EndTime: new Date(2015, 11, 2, 10, 30),
    Location: "CHINA"
}];

var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" currentDate={new Date(2017, 5, 5)} width="100%" height="525px" appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

var Button = React.createClass({
    onClick: function(args) {
        var obj = $("#Schedule1").data("ejSchedule");
        obj.print();
    },
    render: function () {
        return (
            <EJ.Button id="btnExport" width="70px" height="30px" click={this.onClick}>
            </EJ.Button>
       );
    }
});

ReactDOM.render(<Button />, document.getElementById('exportButton'));
ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

### Printing Specific Appointments

To print a particular appointment, either the default context menu **print** option can be used or else the [print](/api/js/ejschedule#methods:print) method can be used by passing the id of the appointment to be printed as its argument.

#### Using Context Menu

Here, the print action is handled internally by default, so that when an appointment is right clicked – choosing print option from the context menu that pops-out will automatically print that particular appointment.

N> To handle this functionality, the context menu settings needs to be enabled with print option added to the appointment items.

The following code example depicts the way to print a particular appointment.

{% highlight html %}

var dManager = [{
    Id: 100,
    Subject: "Wild Discovery",
    StartTime: new Date(2015, 11, 2, 9, 00),
    EndTime: new Date(2015, 11, 2, 10, 30),
    Location: "CHINA"
}];

var contextMenuData = {
    enable: true,
    menuItems: {
        appointment: [
            { id: "open", text: "Open Appointment" },
            { id: "delete", text: "Delete Appointment" },
            { id: "print", text: "Print Appointment" }
        ]
    }
};

var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" currentDate={new Date(2017, 5, 5)} contextMenuSettings={contextMenuData} appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

#### Using print() method

The public method `print` needs to be used here by passing the appointment object as its argument, that needs to be printed.

For example, here the below code example depicts the way to print the particular appointment programmatically by calling the **print** function within the [appointmentClick](/api/js/ejschedule#events:appointmentclick) event, which triggers whenever the user clicks on an appointment.

{% highlight html %}

var dManager = [{
    Id: 100,
    Subject: "Wild Discovery",
    StartTime: new Date(2015, 11, 2, 9, 00),
    EndTime: new Date(2015, 11, 2, 10, 30),
    Location: "CHINA"
}];

var Scheduler = React.createClass({
    onAppointmentClick: function(args) {
        var schObj = $("#Schedule1").data("ejSchedule");
        schObj.print(args.appointment);
    },
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" currentDate={new Date(2017, 5, 5)} appointmentClick={this.onAppointmentClick} appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

## Import Appointments

To import appointments into the Scheduler, server-side method `renderingImportAppointments` needs to be used, which returns the list of appointments retrieved from the specified file path.

Refer the following code example to import the appointments into Scheduler.

{% highlight html %}

var dManager = [{
    Id: 100,
    Subject: "Wild Discovery",
    StartTime: new Date(2015, 11, 2, 9, 00),
    EndTime: new Date(2015, 11, 2, 10, 30),
    Location: "CHINA"
}];

var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" currentDate={new Date(2017, 5, 5)} appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

var Button = React.createClass({
    onScheduleImport: function(args) {
        var dataManger = ej.DataManager({ url: '@Url.Action("ScheduleImportData", "Schedule")', crossDomain: true });
        $("#Schedule1").ejSchedule({
            appointmentSettings: {
                dataSource: dataManger
            }
        });
    },
    render: function () {
        return (
            <EJ.Button id="btnExport" width="70px" height="30px" click={this.onScheduleImport}>
            </EJ.Button>
       );
    }
});

ReactDOM.render(<Button />, document.getElementById('exportButton'));
ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

The server-side action `ScheduleImportData` contains the following code example to import the Scheduler appointments.

{% highlight c# %}

public JsonResult ScheduleImportData() {
    var destinationPath = @"FilePath\iCalender.ics";
    ScheduleImport importApps = new ScheduleImport();
    var app = importApps.renderingImportAppointments(destinationPath);
    int intMax = app.Max(a => a.Id);
    List<ScheduleAppointmentsObjData> result = new List<ScheduleAppointmentsObjData>();
    for (var i = 0; i < app.Count; i++) {
        app[i].Id = intMax + 1;
        ScheduleAppointmentsObjData row = new ScheduleAppointmentsObjData(app[i].Id, app[i].Subject, app[i].Location, app[i].StartTime, app[i].EndTime, app[i].Description, null, null, app[i].Recurrence, null, null, app[i].AppointmentCategorize, null, app[i].AllDay, null, null, app[i].RecurrenceRules, null, null);
        result.Add(row);
        intMax = app[i].Id;
    }
    return Json(result, JsonRequestBehavior.AllowGet);
}

{% endhighlight %}
