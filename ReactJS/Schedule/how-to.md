---
title: How-to
description: Custom Configuration with Schedule control
platform: ReactJS
control: schedule
documentation: ug
keywords: validation and customization of appointment window fields, highlight different work-hours, Appointment filters
---
# How To

## Validate the Custom Appointment Window Fields

The client-side validation of the fields present within the custom appointment window can be handled before submitting it, by adding appropriate validation classes to each field.

Refer the steps [here](/reactjs/schedule/customization#appointment-window-customization) and create a sample for Custom Appointment window, before proceeding with the following validations.

In the custom appointment window sample, create an additional CSS class **validation** as mentioned below to add it to the appropriate fields, if the validation of such fields fails.

{% highlight html %}

<style> 
    .validation {
        border-color: red;
    }
</style>

{% endhighlight %}

The sample contains the fields like Subject, Description, StartTime and EndTime which needs to be validated at client-side. To do so, add the required validation code within the script section as follows.

{% highlight html %}

<script type="text/javascript">

// To Validate the Subject field.
$("#subject").focusout(function() {
    if ($.trim($("#subject").val()) == "") {
        $("#subject").addClass("validation");
        return false;
    }
})

// To Validate the Description field.
$("#customDescription").focusout(function() {
    if ($.trim($("#customDescription").val()) == "") {
        $("#customDescription").addClass("validation");
        return false;
    }
})

// To Validate the Time duration of the appointments
$("#EndTime").focusout(function() {
    if (new Date($("#EndTime").val()).getDate() >= new Date($("#StartTime").val()).getDate()) {
        if (new Date($("#StartTime").val()).getTime() >= new Date($("#EndTime").val()).getTime())
            alert("EndTime value is lesser than the StartTime value");
    }
})

</script>

{% endhighlight %}

Now, after adding the above validations – whenever the fields within the custom appointment window are skipped without filling any information, it will be notified to the users appropriately.

## Highlight Different Work Hours for Each Resources

By default, the work hours of the Scheduler is highlighted based on the start and end values provided within the [workHours](/reactjs/schedule/customization#hour-customization:working-hours) object. It remains same for all the resources, when the Scheduler is rendered with multiple resources. To customize this behavior so as to highlight different work hours range for each of the resources, the following workaround can be utilized by making use of the Scheduler events **create** and [actionComplete](/api/js/ejschedule#events:actioncomplete).

Initially, set the **highlight** as false for the **workHours**, so as to disable the highlighting of default work hour range.

{% highlight html %}

var dManager = [{
    Id: 100,
    Subject: "Research on Sky Miracles",
    StartTime: new Date(2015, 04, 05, 9, 00),
    EndTime: new Date(2015, 04, 05, 10, 30),
    OwnerId: 3,
    RoomId: 2
}];

var groupData = { resources: ["Rooms, Owners"] };
var roomData = {
    dataSource: [
        { text: "ROOM 1", id: 1, groupId: 1, color: "#cb6bb2" },
        { text: "ROOM 2", id: 2, groupId: 1, color: "#56ca85" }
    ],
    text: "text", id: "id", groupId: "groupId", color: "color"
};
var ownerData = {
    dataSource: [
        { text: "Nancy", id: 1, groupId: 1, color: "#ffaa00", on: 10, off: 18 },
        { text: "Steven", id: 3, groupId: 2, color: "#f8a398", on: 6, off: 10 },
        { text: "Michael", id: 5, groupId: 1, color: "#7499e1", on: 11, off: 15 }
    ],
    text: "text", id: "id", groupId: "groupId", color: "color", start: "on", end: "off"
};
var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" width="100%" height="525px" currentDate={new Date(2017, 5, 5)} group={groupData} appointmentSettings-dataSource={dManager} appointmentSettings-id="Id" appointmentSettings-subject="Subject" appointmentSettings-startTime="StartTime" appointmentSettings-endTime="EndTime" appointmentSettings-description="Description" appointmentSettings-allDay="AllDay" appointmentSettings-recurrence="Recurrence" appointmentSettings-recurrenceRule="RecurrenceRule" appointmentSettings-resourceFields= "RoomId,OwnerId">
                <resources>
                    <resource allowMultiple={false} field="RoomId" title="Room" name="Rooms" resourceSettings={roomData}></resource>
                    <resource allowMultiple={true} field="OwnerId" title="Owner" name="Owners" resourceSettings={ownerData}></resource>
                </resources>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

## Display Scheduler with Appointments Filtered by Subject

It is possible to display the Scheduler with appointments, which is filtered based on the Subject. For example, if we keep a text box and start typing a character – the list of appointments whose subject matches the typed character alone will be shown on the Scheduler. The following code example depicts the way to achieve this.

{% highlight html %}

<!--textbox for entering search character-->
<input id='txtSearch' type='text' onkeyup='searchKeyUp()' />

<!--Container for ejScheduler widget-->
<div id="schedule-default"></div>

<script type="text/javascript">
// This function executes when a character is entered in the textbox
function searchKeyUp() {
    var searchString = $("#txtSearch").val();
    var schObj = $("#Schedule1").data("ejSchedule");
    var result = schObj.searchAppointments(searchString);
    schObj.option("appointmentSettings", { dataSource: [] });
    if (!ej.isNullOrUndefined(result) && result.length != 0 && searchString != "")
        schObj.option("appointmentSettings", { dataSource: result });
    else
        schObj.option("appointmentSettings", { dataSource: window.Default });
}

</script>

{% endhighlight %}

{% highlight html %}

window.Default = [{
    Id: 101,
    Subject: "Bering Sea Gold",
    StartTime: new Date(2015, 11, 5, 10, 00),
    EndTime: new Date(2015, 11, 5, 11, 00),
    Description: "",
    AllDay: false,
    Recurrence: false,
    Categorize: "1,3"
}, {
    Id: 102,
    Subject: "Bering Sea Gold",
    StartTime: new Date(2015, 11, 2, 16, 00),
    EndTime: new Date(2015, 11, 2, 17, 30),
    Description: "",
    AllDay: false,
    Recurrence: false,
    Categorize: "2,5"
}, {
    Id: 104,
    Subject: "What Happened Next?",
    StartTime: new Date(2015, 11, 5, 12, 30),
    EndTime: new Date(2015, 11, 5, 15, 00),
    Description: "",
    AllDay: false,
    Recurrence: false,
    Categorize: "4,1"
}, {
    Id: 105,
    Subject: "Daily Planet",
    StartTime: new Date(2015, 11, 3, 01, 00),
    EndTime: new Date(2015, 11, 3, 02, 00),
    Description: "",
    AllDay: false,
    Recurrence: false,
    Categorize: "1,3,6"
}, {
    Id: 107,
    Subject: "How It's Made",
    StartTime: new Date(2015, 11, 1, 06, 00),
    EndTime: new Date(2015, 11, 1, 07, 30),
    Description: "",
    AllDay: false,
    Recurrence: true,
    RecurrenceRule: "FREQ=WEEKLY;BYDAY=MO,TU;INTERVAL=1;COUNT=15",
    Categorize: "2,3,6"
}, {
    Id: 108,
    Subject: "Deadest Catch",
    StartTime: new Date(2015, 11, 3, 16, 00),
    EndTime: new Date(2015, 11, 3, 17, 00),
    Description: "",
    AllDay: false,
    Recurrence: false,
    Categorize: "2,4,6,1"
}, {
    Id: 109,
    Subject: "MayDay",
    StartTime: new Date(2015, 3, 30, 06, 30),
    EndTime: new Date(2015, 3, 30, 07, 30),
    Description: "",
    AllDay: false,
    Recurrence: false,
    Categorize: "5,3"
}, {
    Id: 115,
    Subject: "Cash Cab",
    StartTime: new Date(2015, 3, 30, 15, 00),
    EndTime: new Date(2015, 3, 30, 16, 30),
    Description: "",
    AllDay: false,
    Recurrence: true,
    RecurrenceRule: "FREQ=DAILY;INTERVAL=1;COUNT=5",
    Categorize: "1,3"
}];

var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" currentDate={new Date(2017, 5, 5)} showCurrentTimeIndicator={false} appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

## Customize the Default Appointment Window

Apart from the custom appointment window, it is possible to customize the default appointment window by adding/removing the required number of fields into it. This can be achieved through the **appointmentWindowOpen** event of the scheduler.

The following code example depicts the way to achieve the customization of default appointment window.

{% highlight html %}

var dManager = [{
    Id: 100,
    Subject: "Wild Discovery",
    StartTime: new Date(2015, 11, 2, 9, 00),
    EndTime: new Date(2015, 11, 2, 10, 30),
    Location: "CHINA",
    AppointmentType: "Tentative",
    Status: "90%"
}];

var Scheduler = React.createClass({
    onAppointmentWindowOpen: function(args) {
        // to add custom element in default appointment window
        if (this._appointmentAddWindow.find(".custom-fields").length == 0) {
            var customDesign = "<tr class='custom-fields'><td class='e-textlabel'>Event Type</td><td><input class='app-type' type='text'/></td><td class='e-textlabel'>Event Status </td><td><input class='status' type='text'/></td></tr>";
            $(customDesign).insertAfter(this._appointmentAddWindow.find("." + this._id + "appointmentArrow"));
        }

        if (!ej.isNullOrUndefined(args.appointment)) {
            // if double clicked on the appointments, retrieve the custom field values from the appointment object and fills it in the appropriate fields.
            this._appointmentAddWindow.find(".app-type").val(args.appointment.AppointmentType);
            this._appointmentAddWindow.find(".status").val(args.appointment.Status);
        } else {
            // if double clicked on the cells, clears the field values.
            this._appointmentAddWindow.find(".app-type").val("");
            this._appointmentAddWindow.find(".status").val("");
        }
    },
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" currentDate={new Date(2017, 5, 5)} showCurrentTimeIndicator={false} appointmentWindowOpen={this.onAppointmentWindowOpen} appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

## Synchronize the Schedule with Outlook

Schedule appointments can be synchronized with Outlook and vice versa, by making use of the Microsoft Outlook 12/15 Object library. 

The following code example depicts the way to synchronize the Schedule with Outlook.

{% highlight html %}

var dataManager = ej.DataManager({
    url: '@Url.Action("GetApp", "Home")',
    crudUrl: '@Url.Action("Batch","Home")',
    adaptor: new ej.UrlAdaptor(),
    crossDomain: true
});

var appointData = {
    dataSource: dataManager,
    id: "Id",
    subject: "Subject",
    startTime: "StartTime",
    endTime: "EndTime",
    startTimeZone: "StartTimeZone",
    endTimeZone: "EndTimeZone",
    allDay: "AllDay",
    recurrence: "Recurrence",
    recurrenceRule: "RecurrenceRule"
};

var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" currentDate={new Date(2017, 5, 5)} appointmentSetings={appointData}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

Schedule control is not directly compatible with the Outlook calendar object, as it returns the COM object. Therefore, in order to bind the schedule control with those data retrieved from outlook, then it is necessary to convert the COM object into the schedule acceptable object format. To do so add the following code example in your code behind.

{% highlight c# %}

using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;
using System.Web.Mvc;
using System.ComponentModel;
using System.Configuration;
using System.Data;
using System.Data.SqlClient;
using Microsoft.Office.Interop.Outlook; // required Microsoft Assembly 
using System.Web.Script.Serialization;
using System.Web.UI;
using System.Web.UI.WebControls;
using ScheduleCRUDJS.Models;
using System.Collections;
namespace ScheduleCRUDJS.Controllers
{
    public class HomeController : Controller
    {
        ScheduleDataDataContext db = new ScheduleDataDataContext();

        public ActionResult Index()
        {
            return View();
        }

        [HttpPost]
        public JsonResult GetApp() // function to display the outlook appointments in Schedule initially
        {
            IEnumerable data = GetData(); 
            return Json(data, JsonRequestBehavior.AllowGet);
        }
        public List<MultipleResource> GetData() // function to return the outlook appointments
        {
            Microsoft.Office.Interop.Outlook.Application oApp = new Microsoft.Office.Interop.Outlook.Application();
            Microsoft.Office.Interop.Outlook.NameSpace mapNamespace = oApp.GetNamespace("MAPI");
            Microsoft.Office.Interop.Outlook.MAPIFolder CalendarFolder = mapNamespace.GetDefaultFolder(Microsoft.Office.Interop.Outlook.OlDefaultFolders.olFolderCalendar);
            Microsoft.Office.Interop.Outlook.Items outlookCalendarItems = CalendarFolder.Items;
            List<Microsoft.Office.Interop.Outlook.AppointmentItem> appointmentList = new List<Microsoft.Office.Interop.Outlook.AppointmentItem>();

            foreach (Microsoft.Office.Interop.Outlook.AppointmentItem item in outlookCalendarItems)
            {
                appointmentList.Add(item);
            }

            List<MultipleResource> newApp = new List<MultipleResource>();
            // converting COM object into IEnumerable object
            for (var i = 0; i < appointmentList.Count; i++)
            {
                MultipleResource app = new MultipleResource();
                app.Id = i;
                app.Subject = appointmentList[i].Subject;
                app.AllDay = appointmentList[i].AllDayEvent;
                app.StartTime = Convert.ToDateTime(appointmentList[i].Start.ToString());
                string endTime = appointmentList[i].End.ToString();
                DateTime appEndDate = Convert.ToDateTime(endTime);
                if (endTime.Contains("12:00:00 AM") && app.AllDay == true)
                    app.EndTime = appEndDate.AddMinutes(-1);
                else
                    app.EndTime = appEndDate;
                app.Recurrence = false;
                app.RecurrenceRule = null;
                newApp.Add(app);
            }
            return newApp;
        }
        public JsonResult Batch(EditParams param)
        {
            if (param.action == "insert" || (param.action == "batch" && param.added != null))          // this block of code will execute while inserting the appointments
            {
                var value = param.action == "insert" ? param.value : param.added[0];
                int intMax = db.MultipleResources.ToList().Count > 0 ? db.MultipleResources.ToList().Max(p => p.Id) : 1;
                DateTime startTime = Convert.ToDateTime(value.StartTime);
                DateTime endTime = Convert.ToDateTime(value.EndTime);
                MultipleResource appoint = new MultipleResource()
                {
                    Id = intMax + 1,
                    StartTime = startTime,
                    EndTime = endTime,
                    StartTimeZone = value.StartTimeZone,
                    EndTimeZone = value.EndTimeZone,
                    Subject = value.Subject,
                    OwnerId = value.OwnerId,
                    AllDay = value.AllDay,
                    Recurrence = value.Recurrence,
                    RecurrenceRule = value.RecurrenceRule
                };
                db.MultipleResources.InsertOnSubmit(appoint);
                db.SubmitChanges();
                Microsoft.Office.Interop.Outlook.Application outlookApp = new Microsoft.Office.Interop.Outlook.Application();
                Microsoft.Office.Interop.Outlook.AppointmentItem newAppointment = null;
                newAppointment = (Microsoft.Office.Interop.Outlook.AppointmentItem)outlookApp.CreateItem(Microsoft.Office.Interop.Outlook.OlItemType.olAppointmentItem);
                newAppointment.Start = Convert.ToDateTime(value.StartTime).ToUniversalTime();
                newAppointment.End = Convert.ToDateTime(value.EndTime).ToUniversalTime();
                newAppointment.Subject = value.Subject.ToString();
                newAppointment.Save();
            }
            IEnumerable data = new ScheduleDataDataContext().MultipleResources.Take(200);
            return Json(data, JsonRequestBehavior.AllowGet);
        }
    }
}

{% endhighlight %}

N> In order to achieve the above scenario, need to refer the Microsoft assembly in your application (Microsoft Outlook 12/15 Object library [Microsoft.Office.Interop.Outlook] and refer it in the controller page as shown above).
