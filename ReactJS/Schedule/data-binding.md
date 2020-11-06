---
title: Data binding with Schedule	
description: Binding local and remote data to Scheduler
platform: ReactJS
control: schedule
documentation: ug
keywords: data binding, local data, remote data
---
# Data Binding

## Appointment Fields

The below listed names are the appointment fields which holds the appropriate column names from the dataSource.

<table>
    <tr>
        <th>Field name<br/><br/></th>
        <th>Description<br/><br/></th>
    </tr>
    <tr>
        <td>id<br/><br/></td>
        <td>Binds the <b>id</b> field name for indexing and performing CRUD operation on the appointments. It’s optional.<br/><br/></td>
    </tr>
    <tr>
        <td>startTime<br/><br/></td>
        <td>Binds the appointment start time field name which is <b>mandatory</b> and also its related validation rules.<br/><br/></td>
    </tr>
    <tr>
        <td>startTimeZone<br/><br/></td>
        <td>Binds the name of the start timezone field in the dataSource and also its related validation rules. If the <b>startTimeZone</b> field is not mentioned, then the appointment makes use of the Scheduler timeZone or System timeZone.<br/><br/></td>
    </tr>
    <tr>
        <td>endTime<br/><br/></td>
        <td>Binds the appointment end time field name which is <b>mandatory</b> and also its related validation rules.<br/><br/></td>
    </tr>
    <tr>
        <td>endTimeZone<br/><br/></td>
        <td>Binds the name of the end timezone field in the dataSource and also its related validation rules. If the <b>endTimeZone</b> field is not mentioned, then the appointment makes use of the Scheduler timeZone or System timeZone.<br/><br/></td>
    </tr>
    <tr>
        <td>subject<br/><br/></td>
        <td>Binds the appointment subject field name which holds the summary of the appointment and also its related validation rules. <br/><br/></td>
    </tr>
    <tr>
        <td>location<br/><br/></td>
        <td>Binds the name of the location field and also its related validation rules. It indicates the appointment location/occurrence place. This field needs to be bind to the Scheduler, when an API <b>showLocationField</b> is set to true.<br/><br/></td>
    </tr>
    <tr>
        <td>description<br/><br/></td>
        <td>Binds the appointment description field name and also its related validation rules.<br/><br/></td>
    </tr>
    <tr>
        <td>allDay<br/><br/></td>
        <td>Binds the name of the `allDay` field. It accepts the <b>boolean</b> value and indicates whether the appointment is an all-day appointment or not.<br/><br/></td>
    </tr>
    <tr>
        <td>categorize<br/><br/></td>
        <td>Binds the name of the categorize field and also its related validation rules. It indicates the category or status value (red categorize, green, yellow and so on). <br/><br/></td>
    </tr>
    <tr>
        <td>priority<br/><br/></td>
        <td>Binds the name of the priority field, its related validation rules and also indicates the priority (high, low, medium and none) of the appointments. This field should be bind to the Scheduler, when <b>prioritySettings.enable</b> is set to true.<br/><br/></td>
    </tr>
    <tr>
        <td>resourceFields<br/><br/></td>
        <td>Binds one or more fields in the resource collection. It maps the resource field names with the appointments, denoting to which resource the appointments actually belongs.<br/><br/></td>
    </tr>
    <tr>
        <td>recurrence<br/><br/></td>
        <td>Binds the name of the recurrence field. It accepts the <b>boolean</b> value and indicates whether the appointment is a recurrence appointment or not.<br/><br/></td>
    </tr>
    <tr>
        <td>recurrenceRule<br/><br/></td>
        <td>Binds the name of the recurrenceRule field. It holds the recurrence pattern associated with the appointments.<br/><br/></td>
    </tr>
    <tr>
        <td>recurrenceId<br/><br/></td>
        <td>Binds the recurrence Id field which acts as a parent id for Scheduler recurrence appointments.<br/><br/></td>
    </tr>
    <tr>
        <td>recurrenceExDate<br/><br/></td>
        <td>Binds the recurrence Exception field which accepts the recurrence Exception date values.<br/><br/></td>
    </tr>
</table>

The below example depicts the appointment fields accepting the string type mapper fields,

{% highlight html %}

var dManager = [{
    Id: 1,
    Subject: "Music Class",
    StartTime: new Date("2015/11/7 06:00 AM"),
    StartTimeZone: "UTC +05:30",
    EndTime: new Date("2015/11/7 07:00 AM"),
    EndTimeZone: "UTC +05:30",
    Description: "Never Give up on Obstacles",
    location: "US",
    AllDay: false,
    Recurrence: true,
    RecurrenceRule: "FREQ=WEEKLY;BYDAY=MO,TU;INTERVAL=1;COUNT=15",
    Categorize: "1",
    Priority: "medium",
    OwnerId: 3,
    RecurrenceId: 1,
    RecurrenceExDate: null
}];
var categorizeData = { enable: true };
var priorityData = { enable: true };
var groupData = { resources: ["Owners"] };
var ownerData = {
    dataSource: [
        { text: "Nancy", id: 1, color: "#f8a398" },
        { text: "Steven", id: 3, color: "#56ca85" },
        { text: "Michael", id: 5, color: "#51a0ed" }
    ],
    text: "text", id: "id", color: "color"
};
var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" width="100%" height="525px" currentDate={new Date(2017, 5, 5)} showLocationField={true} categorizeSettings={categorizeData} prioritySettings={priorityData} group={groupData} resources={resourceData} appointmentSettings-dataSource={dManager} appointmentSettings-id="Id" appointmentSettings-subject="Subject" appointmentSettings-startTime="StartTime" appointmentSettings-endTime="EndTime" appointmentSettings-description="Description" appointmentSettings-allDay="AllDay" appointmentSettings-recurrence="Recurrence" appointmentSettings-recurrenceRule="RecurrenceRule" appointmentSettings-resourceFields= "OwnerId">
                <resources>
                    <resource allowMultiple={true} field="OwnerId" title="Owner" name="Owners" resourceSettings={ownerData}></resource>
                </resources>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

## Appointment Field Validation

It is possible to validate the required fields of the appointment window from client-side before submitting it, by adding appropriate validation rules to each fields. The appointment fields have been extended to accept both String and object type values. Therefore, in order to perform validations, it is necessary to specify object values for the appointment fields.

Refer the appointment fields specified with validation rules from the following code example.

{% highlight html %}

var dManager = ej.DataManager(window.Default).executeLocal(ej.Query().take(10));
var categorizeData = {
    enable: true,
    allowMultiple: false,
    dataSource: [
        { text: "Blue Category", id: 1, color: "#43b496", fontColor: "#ffffff" },
        { text: "Green Category", id: 2, color: "#7f993e", fontColor: "#ffffff" },
        { text: "Orange Category", id: 3, color: "#cc8638", fontColor: "#ffffff" },
        { text: "Purple Category", id: 4, color: "#ab54a0", fontColor: "#ffffff" },
        { text: "Red Category", id: 5, color: "#dd654e", fontColor: "#ffffff" },
        { text: "Yellow Category", id: 6, color: "#d0af2b", fontColor: "#ffffff" }
    ],
    text: "text", id: "id", color: "color", fontColor: "fontColor"
};
var appointmentSettingsData = {
    id: "Id",
    dataSource: dManager,
    subject: { field: "Subject", validationRules: { required: true } },
    location: { field: "Location", validationRules: { required: true, customRule: "/^[a-zA-Z0-9- ]*$/" } },
    startTime: { field: "StartTime", validationRules: { required: true } },
    endTime: { field: "EndTime", validationRules: { required: true } },
    description: { field: "Description", validationRules: { required: true, minlength: 5, maxlength: 500 } },
    allDay: "AllDay",
    recurrence: "Recurrence",
    recurrenceRule: "RecurrenceRule",
    categorize: { field: "Categorize", validationRules: { required: true, messages: { required: "Categories are required." } } }
};
var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" width="100%" height="525px" currentDate={new Date(2017, 5, 5)} showLocationField={true} categorizeSettings={categorizeData} appointmentSettings={appointmentSettingsData}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

## Binding to JSON Data Array

To bind the Scheduler events data as array of JSON objects, refer the below code example.

**Example** - Array of JSON Data Binding

{% highlight html %}

var appointmentData = [
    {
        Id: 1,
        Subject: "Music Class",
        StartTime: new Date("2015/11/7 06:00 AM"),
        EndTime: new Date("2015/11/7 07:00 AM")
    }, {
        Id: 2,
        Subject: "School",
        StartTime: new Date("2015/11/7 9:00 AM"),
        EndTime: new Date("2015/11/7 02:30 PM")
    }
];
var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" width="100%" height="525px" currentDate={new Date(2017, 5, 5)} appointmentSettings-dataSource={appointmentData}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

## Binding Remote Data Service

The appointment data can be bound to the Scheduler through the [Odata](http://www.odata.org) remote services, where the service URL is mapped with [Data manager](/js/datamanager/overview) and then configured to the Schedule dataSource API.

{% highlight html %}

var dataManager = ej.DataManager({
    // referring data from remote service (url binding)
    url: "http://mvc.syncfusion.com/OdataServices/Northwnd.svc/"
});
// query to fetch the records from the specified table “Events”
var queryManager = ej.Query().from("Events").take(10);
var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" width="100%" height="525px" currentDate={new Date(2017, 5, 5)} appointmentSettings-dataSource={dataManager} appointmentSettings-query={queryManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

## OData V4

The OData v4 is an improved version of OData protocols and the DataManager can also retrieve and consume appointment data from [OData v4](http://www.odata.org/documentation) services.

{% highlight html %}

var dataManager = ej.DataManager({
    //OData v4 service
    url: "http://services.odata.org/V4/Northwind/Northwind.svc/Orders/",
    adaptor: new ej.ODataV4Adaptor()
});
var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" width="100%" height="525px" currentDate={new Date(2017, 5, 5)} appointmentSettings-dataSource={dataManager} appointmentSettings-subject="ShipName" appointmentSettings-startTime="OrderDate" appointmentSettings-endTime="RequiredDate" appointmentSettings-description="ShipAddress">
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

## WebAPI Binding

The Schedule appointment data can be bound through the Web API service and it is a programmatic interface to define the request and response messages system that is mostly exposed in **JSON** or **XML**.

{% highlight html %}

var dataManager = ej.DataManager({
    // get the required appointments from Web API service
    url: "http://mvc.syncfusion.com/OdataServices/api/ScheduleData/",
    // enable cross domain
    crossDomain: true
});
var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" width="100%" height="525px" currentDate={new Date(2017, 5, 5)} appointmentSettings-dataSource={dataManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

The server-side code to retrieve the appointments are as follows.

{% highlight c# %}

// To retrieve the appointments from database and bind it to Scheduler
public IEnumerable<Event> GetData(String CurrentDate, String CurrentView, String CurrentAction)
{
    return new NORTHWNDEntities().Events.ToList();
}

{% endhighlight %}

## Data binding using OLEDB

The appointment data can also be bound to the Scheduler using OLEDB database as depicted below.

{% highlight html %}

var dataManager = ej.DataManager({
    url: "Home/GetData", // This will trigger to bind the appointment data initially to the Schedule control
    crudUrl: "Home/Batch", // This will trigger while performing CRUD operation on the Scheduler appointments
    adaptor: new ej.UrlAdaptor()
});
var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" width="100%" height="525px" currentDate={new Date(2017, 5, 5)} appointmentSettings-id="Id" appointmentSettings-dataSource={dataManager} appointmentSettings-subject="Subject" appointmentSettings-startTime="StartTime" appointmentSettings-endtime="EndTime" appointmentSettings-startTimeZone="StartTimeZone" appointmentSettings-endTimeZone="EndTimeZone" appointmentSettings-description="Description" appointmentSettings-allDay="AllDay" appointmentSettings-recurrence="Recurrence" appointmentSettings-recurrenceRule="RecurrenceRule">
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

The server-side controller code to retrieve and bind the appointment data to Scheduler are as follows. Also, define a class with all the required appointment fields as depicted in the below code example.

{% highlight c# %}

// Define a class with all appointment fields
public class ScheduleData
{
    public int Id { get; set; }
    public string Subject { get; set; }
    public DateTime StartTime { get; set; }
    public DateTime EndTime { get; set; }
    public Boolean AllDay { get; set; }
    public Boolean Recurrence { get; set; }
    public string RecurrenceRule { get; set; }
    public string StartTimeZone { get; set; }
    public string EndTimeZone { get; set; }
    public string Description { get; set; }
}

// To retrieve the appointments from database and bind it to Scheduler
public JsonResult GetData()
{
    // Mention your own dataSource to be used here.
    string strAccessConn = "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=|DataDirectory|/ScheduleDb.MDB";
    DataSet myDataSet = new DataSet();
    OleDbConnection myAccessConn = null;
    myAccessConn = new OleDbConnection(strAccessConn);
    OleDbCommand myAccessCommand = new OleDbCommand("SELECT * FROM DefaultSchedule", myAccessConn);
    OleDbDataAdapter myDataAdapter = new OleDbDataAdapter(myAccessCommand);
    myAccessConn.Open();
    myDataAdapter.Fill(myDataSet, "DefaultSchedule");
    List<ScheduleData> datasource = new List<ScheduleData>();
    datasource = myDataSet.Tables[0].AsEnumerable().Select(dataRow => new ScheduleData { Id = dataRow.Field<int>("Id"), Subject = dataRow.Field<string>("Subject"), StartTime = dataRow.Field<DateTime>("StartTime"), EndTime = dataRow.Field<DateTime>("EndTime"), AllDay = dataRow.Field<bool>("AllDay"), Recurrence = dataRow.Field<bool>("Recurrence"), RecurrenceRule = dataRow.Field<string>("RecurrenceRule"), Description = dataRow.Field<string>("Description"), StartTimeZone = dataRow.Field<string>("StartTimeZone"), EndTimeZone = dataRow.Field<string>("EndTimeZone") }).ToList();
    myAccessConn.Close();
    return Json(datasource, JsonRequestBehavior.AllowGet);
}

{% endhighlight %}

The control code to handle the CRUD operation are as follows.

{% highlight c# %}

public JsonResult Batch(EditParams param)
{
    // Mention your own dataSource to be used here.
    string strAccessConn = "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=|DataDirectory|/ScheduleDb.MDB";
    if (param.action == "insert" || (param.action == "batch" && param.added != null))  // this block of code will execute while inserting the appointments
    {
        var value = param.action == "insert" ? param.value : param.added[0];
        using (OleDbConnection myCon = new OleDbConnection(strAccessConn))
        {
            OleDbCommand cmd = new OleDbCommand();
            cmd.CommandType = CommandType.Text;
            cmd.CommandText = "INSERT INTO DefaultSchedule(Subject,StartTime,EndTime,AllDay,Recurrence,RecurrenceRule,Description,StartTimeZone,EndTimeZone) VALUES (@Subject,@StartTime,@EndTime,@AllDay,@Recurrence,@RecurrenceRule,@Description,@StartTimeZone,@EndTimeZone)";
            if (string.IsNullOrEmpty(value.Subject))
                cmd.Parameters.AddWithValue("@Subject", DBNull.Value);
            else
                cmd.Parameters.AddWithValue("@Subject", value.Subject);
            cmd.Parameters.AddWithValue("@StartTime", value.StartTime);
            cmd.Parameters.AddWithValue("@EndTime", value.EndTime);
            cmd.Parameters.AddWithValue("@AllDay", value.AllDay);
            cmd.Parameters.AddWithValue("@Recurrence", value.Recurrence);
            if (string.IsNullOrEmpty(value.RecurrenceRule))
                cmd.Parameters.AddWithValue("@RecurrenceRule", DBNull.Value);
            else
                cmd.Parameters.AddWithValue("@RecurrenceRule", value.RecurrenceRule);
            if (string.IsNullOrEmpty(value.Description))
                cmd.Parameters.AddWithValue("@Description", DBNull.Value);
            else
                cmd.Parameters.AddWithValue("@Description", value.Description);
            if (string.IsNullOrEmpty(value.StartTimeZone))
                cmd.Parameters.AddWithValue("@StartTimeZone", DBNull.Value);
            else
                cmd.Parameters.AddWithValue("@StartTimeZone", value.StartTimeZone);
            if (string.IsNullOrEmpty(value.EndTimeZone))
                cmd.Parameters.AddWithValue("@EndTimeZone", DBNull.Value);
            else
                cmd.Parameters.AddWithValue("@EndTimeZone", value.EndTimeZone);
            cmd.Connection = myCon;
            myCon.Open();
            cmd.ExecuteNonQuery();
            myCon.Close();
        }
    }
    if (param.action == "remove" || param.deleted != null)  // this block of code will execute while removing the appointment
    {
        if (param.action == "remove")
        {
            using (OleDbConnection myCon = new OleDbConnection(strAccessConn))
            {
                myCon.Open();
                OleDbCommand cmd = new OleDbCommand("DELETE FROM DefaultSchedule WHERE Id = @Key", myCon);
                cmd.Parameters.AddWithValue("@Key", param.key);
                cmd.ExecuteNonQuery();
                myCon.Close();
            }
        }
        else
        {
            foreach (var apps in param.deleted)
            {
                using (OleDbConnection myCon = new OleDbConnection(strAccessConn))
                {
                    myCon.Open();
                    OleDbCommand cmd = new OleDbCommand("DELETE FROM DefaultSchedule WHERE Id = @Key", myCon);
                    cmd.Parameters.AddWithValue("@Key", apps.Id);
                    cmd.ExecuteNonQuery();
                    myCon.Close();
                }
            }
        }
    }
    if ((param.action == "batch" && param.changed != null) || param.action == "update")   // this block of code will execute while updating the appointment
    {
        var value = param.action == "update" ? param.value : param.changed[0];
        using (OleDbConnection myCon = new OleDbConnection(strAccessConn))
        {
            myCon.Open();
            OleDbCommand cmd = new OleDbCommand("UPDATE DefaultSchedule SET Subject=@Subject,StartTime=@StartTime,EndTime=@EndTime,AllDay=@AllDay,Recurrence=@Recurrence,RecurrenceRule=@RecurrenceRule,Description=@Description,StartTimeZone=@StartTimeZone,EndTimeZone=@EndTimeZone  WHERE Id = @Key", myCon);
            if (string.IsNullOrEmpty(value.Subject))
                cmd.Parameters.AddWithValue("@Subject", DBNull.Value);
            else
                cmd.Parameters.AddWithValue("@Subject", value.Subject);
            cmd.Parameters.AddWithValue("@StartTime", value.StartTime);
            cmd.Parameters.AddWithValue("@EndTime", value.EndTime);
            cmd.Parameters.AddWithValue("@AllDay", value.AllDay);
            cmd.Parameters.AddWithValue("@Recurrence", value.Recurrence);
            if (string.IsNullOrEmpty(value.RecurrenceRule))
                cmd.Parameters.AddWithValue("@RecurrenceRule", DBNull.Value);
            else
                cmd.Parameters.AddWithValue("@RecurrenceRule", value.RecurrenceRule);
            if (string.IsNullOrEmpty(value.Description))
                cmd.Parameters.AddWithValue("@Description", DBNull.Value);
            else
                cmd.Parameters.AddWithValue("@Description", value.Description);
            if (string.IsNullOrEmpty(value.StartTimeZone))
                cmd.Parameters.AddWithValue("@StartTimeZone", DBNull.Value);
            else
                cmd.Parameters.AddWithValue("@StartTimeZone", value.StartTimeZone);
            if (string.IsNullOrEmpty(value.EndTimeZone))
                cmd.Parameters.AddWithValue("@EndTimeZone", DBNull.Value);
            else
                cmd.Parameters.AddWithValue("@EndTimeZone", value.EndTimeZone);
            cmd.Parameters.AddWithValue("@Key", value.Id);
            cmd.ExecuteNonQuery();
            myCon.Close();
        }
    }
    OleDbConnection myAccessConn = new OleDbConnection(strAccessConn);
    OleDbCommand myAccessCommand = new OleDbCommand("SELECT * FROM DefaultSchedule", myAccessConn);
    OleDbDataAdapter myDataAdapter = new OleDbDataAdapter(myAccessCommand);
    DataSet myDataSet = new DataSet();
    myAccessConn.Open();
    myDataAdapter.Fill(myDataSet, "DefaultSchedule");
    List<ScheduleData> datasource = new List<ScheduleData>();
    datasource = myDataSet.Tables[0].AsEnumerable().Select(dataRow => new ScheduleData { Id = dataRow.Field<int>("Id"), Subject = dataRow.Field<string>("Subject"), StartTime = dataRow.Field<DateTime>("StartTime"), EndTime = dataRow.Field<DateTime>("EndTime"), AllDay = dataRow.Field<bool>("AllDay"), Recurrence = dataRow.Field<bool>("Recurrence"), RecurrenceRule = dataRow.Field<string>("RecurrenceRule"), Description = dataRow.Field<string>("Description"), StartTimeZone = dataRow.Field<string>("StartTimeZone"), EndTimeZone = dataRow.Field<string>("EndTimeZone") }).ToList();
    myAccessConn.Close();
    return Json(datasource, JsonRequestBehavior.AllowGet);
}

// Class definition for EditParams to be used as parameter in the above Crud method for receiving the object value in it.
public class EditParams
{
    public string key { get; set; }
    public string action { get; set; }
    public List<ScheduleData> added { get; set; }
    public List<ScheduleData> changed { get; set; }
    public List<ScheduleData> deleted { get; set; }
    public ScheduleData value { get; set; }
}

{% endhighlight %}

## ASP.NET Web Method Binding

The Schedule appointment data can retrieve data from ASP.NET Web methods by making use of the UrlAdaptor of ejDataManager.

{% highlight html %}

var dataManager = ej.DataManager({
    url: "WebService1.asmx/GetData", // This will trigger to bind the appointments data to schedule control
    batchUrl: "WebService1.asmx/Crud", // This will trigger while saving the appointment through detail window
    insertUrl: "WebService1.asmx/add", // This will trigger while saving the appointment through quick window
    updateUrl: "WebService1.asmx/update", //This will trigger while saving the resize or drag and drop the appointment
    removeUrl: "WebService1.asmx/remove", // This will trigger to delete the single appointment
    adaptor: new ej.WebMethodAdaptor()
});
var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" width="100%" height="525px" currentDate={new Date(2017, 5, 5)} appointmentSettings-id="Id" appointmentSettings-dataSource={dataManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

The server-side code to handle the CRUD operations are as follows.

{% highlight c# %}

// To retrieve the appointments and bind it to Scheduler
[WebMethod]
[ScriptMethod(ResponseFormat = ResponseFormat.Json)]
public static object GetData(String CurrentView, String CurrentAction, DateTime CurrentDate)
{
    // ScheduleAppointmentsObjData is a user-defined class needs to be defined with collection of scheduler appointments
    ScheduleAppointmentsObjDatum obj = new ScheduleAppointmentsObjDatum();
    IList<ScheduleAppointmentsObjData> appoint = obj.GetRecords().ToList();
    return appoint;
}

public class ScheduleAppointmentsObjDatum
{
    [DataObjectMethod(DataObjectMethodType.Select)]
    public List<ScheduleAppointmentsObjData> GetRecords()
    {
        List<ScheduleAppointmentsObjData> list = new List<ScheduleAppointmentsObjData>();
        list.Add(new ScheduleAppointmentsObjData(100, "Bering Sea Gold", "Chennai", "05/02/2014 09:00:00 AM", "05/02/2014 10:30:00 AM", "", "1", "", true, "", "", "", "", false, "", "", "FREQ=DAILY;INTERVAL=2;COUNT=10"));
        list.Add(new ScheduleAppointmentsObjData(101, "Bering Sea Gold", "mum", "05/02/2014 04:00:00 AM", "05/02/2014 05:00:00 AM", "", "1", "", false, "", "", "", "", false, "", "", ""));
        list.Add(new ScheduleAppointmentsObjData(102, "Bering Sea Gold", "Trichy", "05/02/2014 04:00:00 PM", "05/02/2014 05:30:00 PM", "", "1", "", false, "", "", "", "", false, "", "", ""));
        list.Add(new ScheduleAppointmentsObjData(103, "What Happened Next?", "Chennai", "05/04/2014 03:00:00 AM", "05/04/2014 04:30:00 AM", "", "1", "", false, "", "", "", "", false, "", "", ""));
        list.Add(new ScheduleAppointmentsObjData(104, "Bering Sea Gold", "Trichy", "05/04/2014 05:00:00 AM", "05/04/2014 05:40:00 AM", "", "1", "", false, "", "", "", "", false, "", "", ""));
        list.Add(new ScheduleAppointmentsObjData(105, "Daily Planet", "Chennai", "05/03/2014 01:00:00 AM", "05/03/2014 02:00:00 AM", "", "1", "", false, "", "", "", "", false, "", "", ""));
        list.Add(new ScheduleAppointmentsObjData(106, "Alaska: The Last Frontier", "Chennai", "05/03/2014 08:00:00 AM", "05/03/2014 09:00:00 AM", "", "1", "", false, "", "", "", "", false, "", "", ""));
        list.Add(new ScheduleAppointmentsObjData(107, "How It's Made", "Chennai", "05/01/2014 06:00:00 AM", "05/01/2014 06:30:00 AM", "", "1", "", true, "", "", "", "", false, "", "", "FREQ=WEEKLY;BYDAY=MO,TU;INTERVAL=1;COUNT=15"));
        list.Add(new ScheduleAppointmentsObjData(108, "Deadest Catch", "Chennai", "05/03/2014 04:00:00 PM", "05/03/2014 05:00:00 PM", "", "1", "", false, "", "", "", "", false, "", "", ""));
        list.Add(new ScheduleAppointmentsObjData(109, "MayDay", "Chennai", "04/30/2014 06:30:00 AM", "04/30/2014 07:30:00 AM", "", "1", "", false, "", "", "", "", false, "", "", ""));
        list.Add(new ScheduleAppointmentsObjData(110, "MoonShiners", "Chennai", "05/02/2014 02:00:00 AM", "05/02/2014 02:30:00 AM", "", "1", "", true, "", "", "", "", false, "", "", "FREQ=DAILY;INTERVAL=1;COUNT=5"));
        list.Add(new ScheduleAppointmentsObjData(111, "Close Encounters", "Chennai", "04/30/2014 02:00:00 PM", "04/30/2014 03:00:00 PM", "", "1", "", true, "", "", "", "", false, "", "", "FREQ=WEEKLY;BYDAY=MO,TH;INTERVAL=1;COUNT=5"));
        list.Add(new ScheduleAppointmentsObjData(112, "Close Encounters", "Mumbai", "04/30/2014 03:00:00 AM", "04/30/2014 03:30:00 AM", "", "1", "", true, "", "", "", "", false, "", "", "FREQ=WEEKLY;BYDAY=WE;INTERVAL=1;COUNT=3"));
        list.Add(new ScheduleAppointmentsObjData(113, "Highway Through Hell", "Chennai", "05/01/2014 03:00:00 AM", "05/01/2014 07:00:00 AM", "", "1", "", true, "", "", "", "", false, "", "", "FREQ=DAILY;INTERVAL=2;COUNT=10"));
        list.Add(new ScheduleAppointmentsObjData(114, "Moon Shiners", "Chennai", "05/02/2014 04:20:00 AM", "05/02/2014 05:50:00 AM", "", "1", "", false, "", "", "", "", false, "", "", ""));
        list.Add(new ScheduleAppointmentsObjData(115, "Cash Cab", "Chennai", "04/30/2014 03:00:00 PM", "04/30/2014 04:30:00 PM", "", "1", "", true, "", "", "", "", false, "", "", "FREQ=DAILY;INTERVAL=1;COUNT=5"));
        return list;
    }
}

[Serializable]
public class ScheduleAppointmentsObjData
{
    private int _id;
    private String _subject;
    private String _location;
    private String _startTime;
    private String _endTime;
    private String _description;
    private String _owner;
    private String _priority;
    private Boolean _recurrence;
    private String _recurrenceType;
    private String _recurrenceTypeCount;
    private String _remainderCategorize;
    private String _customStyle;
    private Boolean _allDay;
    private String _recurrenceStartDate;
    private String _recurrenceEndDate;
    private String _recurrenceRule;

    public ScheduleAppointmentsObjData()
    {

    }

    public ScheduleAppointmentsObjData(int _id, string _subject, string _location, string _startTime, string _endTime, string _description, string _owner, string _priority, bool _recurrence, string _recurrenceType, string _recurrenceTypeCount, string _remainderCategorize, string _customStyle, bool _allDay, string _recurrenceStartDate, string _recurrenceEndDate, string _recurrenceRule)
    {
        this._id = _id;
        this._subject = _subject;
        this._location = _location;
        this._startTime = _startTime;
        this._endTime = _endTime;
        this._description = _description;
        this._owner = _owner;
        this._priority = _priority;
        this._recurrence = _recurrence; ;
        this._recurrenceType = _recurrenceType;
        this._recurrenceTypeCount = _recurrenceTypeCount;
        this._remainderCategorize = _remainderCategorize;
        this._customStyle = _customStyle;
        this._allDay = _allDay;
        this._recurrenceStartDate = _recurrenceStartDate;
        this._recurrenceEndDate = _recurrenceEndDate;
        this._recurrenceRule = _recurrenceRule;
    }

    public int ID
    {
        get
        {
            return _id;
        }
        set
        {
            _id = value;
        }
    }

    public string Subject
    {
        get
        {
            return _subject;
        }
        set
        {
            _subject = value;
        }
    }
    public string Location
    {
        get
        {
            return _location;
        }
        set
        {
            _location = value;
        }
    }
    public string StartTime
    {
        get
        {
            return _startTime;
        }
        set
        {
            _startTime = value;
        }
    }
    public string EndTime
    {
        get
        {
            return _endTime;
        }
        set
        {
            _endTime = value;
        }
    }
    public string Description
    {
        get
        {
            return _description;
        }
        set
        {
            _description = value;
        }
    }
    public string Owner
    {
        get
        {
            return _owner;
        }
        set
        {
            _owner = value;
        }
    }
    public string Priority
    {
        get
        {
            return _priority;
        }
        set
        {
            _priority = value;
        }
    }
    public Boolean Recurrence
    {
        get
        {
            return _recurrence;
        }
        set
        {
            _recurrence = value;
        }
    }
    public string RecurrenceType
    {
        get
        {
            return _recurrenceType;
        }
        set
        {
            _recurrenceType = value;
        }
    }
    public string RecurrenceTypeCount
    {
        get
        {
            return _recurrenceTypeCount;
        }
        set
        {
            _recurrenceTypeCount = value;
        }
    }
    public string RemainderCategorize
    {
        get
        {
            return _remainderCategorize;
        }
        set
        {
            _remainderCategorize = value;
        }
    }
    public string CustomStyle
    {
        get
        {
            return _customStyle;
        }
        set
        {
            _customStyle = value;
        }
    }
    public Boolean AllDay
    {
        get
        {
            return _allDay;
        }
        set
        {
            _allDay = value;
        }
    }
    public string RecurrenceStartDate
    {
        get
        {
            return _recurrenceStartDate;
        }
        set
        {
            _recurrenceStartDate = value;
        }
    }
    public string RecurrenceEndDate
    {
        get
        {
            return _recurrenceEndDate;
        }
        set
        {
            _recurrenceEndDate = value;
        }
    }
    public string RecurrenceRule
    {
        get
        {
            return _recurrenceRule;
        }
        set
        {
            _recurrenceRule = value;
        }
    }
}

// Method to retrieve appointments from the ScheduleAppointmentsObjDatum Class
public static IList<ScheduleAppointmentsObjData> GetAllRecords()
{
    ScheduleAppointmentsObjDatum obj = new ScheduleAppointmentsObjDatum();
    IList<ScheduleAppointmentsObjData> appoint = obj.GetRecords().ToList();
    return appoint;
}

// Method to convert appointment object of dictionary type into valid format.
public static ScheduleAppointmentsObjData GetObjectValue(Dictionary<string, object> objValue)
{
    Dictionary<string, object> KeyVal = objValue;
    ScheduleAppointmentsObjData appointValue = new ScheduleAppointmentsObjData();
    foreach (KeyValuePair<string, object> keyValue in KeyVal)
    {
        if (keyValue.Key == "ID")
            appointValue.ID = Convert.ToInt32(keyValue.Value);
        else if (keyValue.Key == "Subject")
            appointValue.Subject = Convert.ToString(keyValue.Value);
        else if (keyValue.Key == "Location")
            appointValue.Location = Convert.ToString(keyValue.Value);
        else if (keyValue.Key == "StartTime")
            appointValue.StartTime = Convert.ToDateTime(keyValue.Value).ToString("MM'/'dd'/'yyyy hh:mm:ss tt");
        else if (keyValue.Key == "EndTime")
            appointValue.EndTime = Convert.ToDateTime(keyValue.Value).ToString("MM'/'dd'/'yyyy hh:mm:ss tt");
        else if (keyValue.Key == "Description")
            appointValue.Description = Convert.ToString(keyValue.Value);
        else if (keyValue.Key == "AllDay")
            appointValue.AllDay = Convert.ToBoolean(keyValue.Value);
        else if (keyValue.Key == "Recurrence")
            appointValue.Recurrence = Convert.ToBoolean(keyValue.Value);
        else if (keyValue.Key == "RecurrenceRule")
            appointValue.RecurrenceRule = Convert.ToString(keyValue.Value);
    }
    return appointValue;
}

// Triggers while creating appointment through quick window.
[WebMethod]
[ScriptMethod(ResponseFormat = ResponseFormat.Json)]
public static void add(object value)
{
    ScheduleAppointmentsObjData appointValue = GetObjectValue(value as Dictionary<string, object>);
    GetAllRecords().Insert(0, appointValue);
}

// Triggers while editing the appointments.
[WebMethod]
[ScriptMethod(ResponseFormat = ResponseFormat.Json)]
public static void update(object value)
{
    ScheduleAppointmentsObjData obj = GetObjectValue(value as Dictionary<string, object>);
    var filterData = GetAllRecords().ToList().Where(c => c.ID == Convert.ToInt32(obj.ID));
    if (filterData.Count() > 0)
    {
        ScheduleAppointmentsObjData appoint = GetAllRecords().Single(A => A.ID == Convert.ToInt32(obj.ID));
        appoint.StartTime = obj.StartTime;
        appoint.EndTime = obj.EndTime;
        appoint.Subject = obj.Subject;
        appoint.Recurrence = obj.Recurrence;
        appoint.AllDay = obj.AllDay;
        appoint.RecurrenceRule = obj.RecurrenceRule;
    }
}

// Triggers on deleting an appointment.
[WebMethod]
[ScriptMethod(ResponseFormat = ResponseFormat.Json)]
public static void remove(int key)
{
    ScheduleAppointmentsObjData removeApp = GetAllRecords().Where(c => c.ID == key).FirstOrDefault();
    if (removeApp != null)
        GetAllRecords().Remove(removeApp);
}

// Triggers for all CRUD actions on Scheduler appointments.
[WebMethod]
[ScriptMethod(ResponseFormat = ResponseFormat.Json)]
public static void Crud(List<object> added, List<object> changed, List<object> deleted)
{
    if (added != null && added.Count > 0)
    {
        ScheduleAppointmentsObjData appointValue = GetObjectValue(added[0] as Dictionary<string, object>);
        GetAllRecords().Insert(0, appointValue);
    }
    if (changed != null && changed.Count > 0)
    {
        ScheduleAppointmentsObjData value = GetObjectValue(changed[0] as Dictionary<string, object>);
        var filterData = GetAllRecords().ToList().Where(c => c.ID == Convert.ToInt32(value.ID));
        if (filterData.Count() > 0)
        {
            ScheduleAppointmentsObjData appoint = GetAllRecords().Where(A => A.ID == Convert.ToInt32(value.ID)).FirstOrDefault();
            appoint.StartTime = value.StartTime;
            appoint.EndTime = value.EndTime;
            appoint.Subject = value.Subject;
            appoint.Recurrence = value.Recurrence;
            appoint.AllDay = value.AllDay;
            appoint.RecurrenceRule = value.RecurrenceRule;
        }
    }
    if (deleted != null && deleted.Count > 0)
    {
        foreach (var delete in deleted)
        {
            ScheduleAppointmentsObjData value = GetObjectValue(delete as Dictionary<string, object>);
            ScheduleAppointmentsObjData removeApp = GetAllRecords().Where(c => c.ID == value.ID).FirstOrDefault();
            if (removeApp != null)
                GetAllRecords().Remove(removeApp);
        }
    }
}

{% endhighlight %}

## MVC Controller Action Binding

The Schedule appointment data can retrieve data from MVC controller. This can be achieved by using the [UrlAdaptor](/js/datamanager/data-adaptors#url-adaptor) of [ej.DataManager](/js/datamanager/overview).

{% highlight html %}

var dataManager = ej.DataManager({
    url: "Home/GetData", // This will trigger to bind the appointments data to schedule control
    batchUrl: "Home/Crud", // This will trigger while saving the appointment through detail window
    insertUrl: "Home/add", // This will trigger while saving the appointment through quick window
    updateUrl: "Home/update", //This will trigger while saving the resize or drag and drop the appointment
    removeUrl: "Home/remove", // This will trigger to delete the single appointment
    adaptor: new ej.UrlAdaptor()
});
var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" width="100%" height="525px" currentDate={new Date(2017, 5, 5)} appointmentSettings-id="Id" appointmentSettings-dataSource={dataManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

The server-side controller code to handle the CRUD operations are as follows.

{% highlight c# %}

// To initially bind the appointments with Scheduler
public JsonResult GetData()
{
    // ScheduleDataDataContext is a LINQ-to-SQL data class name that is defined in the .dbml file to access the tables from the database 
    IEnumerable data = new ScheduleDataDataContext().Appointments.Take(100);
    return Json(data, JsonRequestBehavior.AllowGet);
}

// Triggers while saving a new appointment through quick window
public JsonResult add(Appointment value)
{
    ScheduleDataDataContext db = new ScheduleDataDataContext();
    int intMax = db.Appointments.ToList().Count > 0 ? db.Appointments.ToList().Max(p => p.Id) : 1;
    Appointment appoint = new Appointment()
    {
        Id = intMax + 1,
        StartTime = value.StartTime,
        EndTime = value.EndTime,
        Subject = value.Subject,
        Description = value.Description,
        OwnerId = value.OwnerId,
        Recurrence = value.Recurrence,
        AllDay = value.AllDay,
        RecurrenceRule = value.RecurrenceRule
    };
    db.Appointments.InsertOnSubmit(appoint);
    db.SubmitChanges();
    IEnumerable data = new ScheduleDataDataContext().Appointments.Take(100);
    return Json(data, JsonRequestBehavior.AllowGet);
}

// Triggers while editing/dragging/resizing the existing appointment
public JsonResult update(Appointment value)
{
    ScheduleDataDataContext db = new ScheduleDataDataContext();
    var filterData = db.Appointments.Where(c => c.Id == Convert.ToInt32(value.Id));
    Appointment appoint = db.Appointments.Single(A => A.Id == Convert.ToInt32(value.Id));
    if (filterData.Count() > 0)
    {
        DateTime startTime = Convert.ToDateTime(value.StartTime);
        DateTime endTime = Convert.ToDateTime(value.EndTime);
        appoint.StartTime = startTime;
        appoint.EndTime = endTime;
        appoint.Subject = value.Subject;
        appoint.Description = value.Description;
        appoint.OwnerId = value.OwnerId;
        appoint.Recurrence = Convert.ToByte(value.Recurrence);
        appoint.AllDay = value.AllDay;
        appoint.RecurrenceRule = value.RecurrenceRule;
    }
    db.SubmitChanges();
    IEnumerable data = new ScheduleDataDataContext().Appointments.Take(100);
    return Json(data, JsonRequestBehavior.AllowGet);
}

// Triggers when an appointment is deleted
public JsonResult remove(string key)
{
    ScheduleDataDataContext db = new ScheduleDataDataContext();
    Appointment app = db.Appointments.Where(c => c.Id == Convert.ToInt32(key)).FirstOrDefault();
    if (app != null) db.Appointments.DeleteOnSubmit(app);
    db.SubmitChanges();
    IEnumerable data = new ScheduleDataDataContext().Appointments.Take(100);
    return Json(data, JsonRequestBehavior.AllowGet);
}

// Triggers for any of the Scheduler CRUD operation
public JsonResult Crud(EditParams param)
{
    ScheduleDataDataContext db = new ScheduleDataDataContext();
    if (param.action == "insert" || (param.action == "batch" && param.added != null))  // this block of code will execute while inserting the appointments
    {
        var value = param.action == "insert" ? param.value : param.added[0];
        int intMax = db.Appointments.ToList().Count > 0 ? db.Appointments.ToList().Max(p => p.Id) : 1;
        DateTime startTime = Convert.ToDateTime(value.StartTime);
        DateTime endTime = Convert.ToDateTime(value.EndTime);
        Appointment appoint = new Appointment()
        {
            Id = intMax + 1,
            StartTime = startTime,
            EndTime = endTime,
            Subject = value.Subject,
            Description = value.Description,
            OwnerId = value.OwnerId,
            Recurrence = value.Recurrence,
            AllDay = value.AllDay,
            RecurrenceRule = value.RecurrenceRule
        };
        db.Appointments.InsertOnSubmit(appoint);
        db.SubmitChanges();
    }
    else if (param.action == "remove")  // this block of code will execute while removing the appointment
    {
        Appointment app = db.Appointments.Where(c => c.Id == Convert.ToInt32(param.key)).FirstOrDefault();
        if (app != null) db.Appointments.DeleteOnSubmit(app);
        db.SubmitChanges();
    }
    else if ((param.action == "batch" && param.changed != null) || param.action == "update")   // this block of code will execute while updating the appointment
    {
        var value = param.action == "update" ? param.value : param.changed[0];
        var filterData = db.Appointments.Where(c => c.Id == Convert.ToInt32(value.Id));
        if (filterData.Count() > 0)
        {
            DateTime startTime = Convert.ToDateTime(value.StartTime);
            DateTime endTime = Convert.ToDateTime(value.EndTime);
            Appointment appoint = db.Appointments.Single(A => A.Id == Convert.ToInt32(value.Id));
            appoint.StartTime = startTime.ToUniversalTime();
            appoint.EndTime = endTime.ToUniversalTime();
            appoint.Subject = value.Subject;
            appoint.Description = value.Description;
            appoint.OwnerId = value.OwnerId;
            appoint.Recurrence = Convert.ToByte(value.Recurrence);
            appoint.AllDay = value.AllDay;
            appoint.RecurrenceRule = value.RecurrenceRule;
        }
        db.SubmitChanges();
    }
    IEnumerable data = new ScheduleDataDataContext().Appointments.Take(500); 
    return Json(data, JsonRequestBehavior.AllowGet);
}

// Class definition for EditParams to be used as parameter in the above Crud method for receiving the object value in it.
public class EditParams
{
    public string key { get; set; }
    public string action { get; set; }
    public List<Appointment> added { get; set; }
    public List<Appointment> changed { get; set; }
    public Appointment value { get; set; }
}

{% endhighlight %}

## Loading Data on Demand

Load on demand feature allows the Scheduler to retrieve only the filtered appointment data (for the current Scheduler date range) from the service/database during **loading time**, and that too only for the current Scheduler view. There are 3 parameters made available on the server-side namely **CurrentDate**, **CurrentView** and **CurrentAction** through which only the necessary appointments are retrieved from the database and then assigned to the Scheduler dataSource. With this kind of Scheduler action, consuming only lesser data will reduce the usage of network bandwidth size and loading time.

The **enableLoadOnDemand** property is used to enable or disable the load on demand functionality of the schedule.

{% highlight html %}

var dataManager = ej.DataManager({
    // get the required appointments from service
    url: "http://mvc.syncfusion.com/OdataServices/api/ScheduleData/",
    crossDomain: true
});
var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" width="100%" height="525px" enableLoadOnDemand={true} currentDate={new Date(2017, 5, 5)} appointmentSettings-id="Id" appointmentSettings-dataSource={dataManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

The server-side code to handle the load on demand is as follows.

{% highlight c# %}

// retrieve the appointments based on the current date.
public IEnumerable<Event> GetData(String CurrentDate, String CurrentView, String CurrentAction)
{
    var dateString = Regex.Match(CurrentDate.ToString(), @"^(\w+\b.*?){4}").ToString();
    string format = "ddd MMM dd yyyy";
    DateTime dateTimeValue;
    try
    {
        dateTimeValue = DateTime.ParseExact(dateString, format, CultureInfo.InvariantCulture);
    }
    catch(FormatException)
    {
        var dateSplit = CurrentDate.Split(' ');//For IE<=10 Fri Mar 20 11:00:22 UTC+0530 2015
        if (dateSplit[2].Length == 1) dateSplit[2] = string.Concat("0", dateSplit[2]);
        dateString = string.Concat(dateSplit[0], ' ', dateSplit[1], ' ', dateSplit[2], ' ', dateSplit[dateSplit.Length - 1]);
        dateTimeValue = DateTime.ParseExact(dateString, format, CultureInfo.InvariantCulture);
    }
    // AppointmentDeposit is a user-defined class within which the FilterAppointment method is defined.
    AppointmentDeposit rep = new AppointmentDeposit();
    var data = rep.FilterAppointment(dateTimeValue, CurrentAction, CurrentView);
    return data;
}

// Method to filter the appointments based on the date range
public List<Event> FilterAppointment(DateTime CurrentDate, String CurrentAction, String CurrentView)
{
    DateTime CurrDate = Convert.ToDateTime(CurrentDate);
    DateTime StartDate = FirstWeekDate(CurrDate.Date);
    DateTime EndDate = FirstWeekDate(CurrDate.Date);
    List<Event> appointmentList = new NORTHWNDEntities().Events.ToList();
    switch (CurrentView)
    {
        case "day":
            StartDate = CurrentDate;
            EndDate = CurrentDate;
            break;
        case "week":
            EndDate = EndDate.AddDays(7);
            break;
        case "workweek":
            EndDate = EndDate.AddDays(5);
            break;
        case "month":
            StartDate = CurrDate.Date.AddDays(-CurrDate.Day + 1);
            EndDate = StartDate.AddMonths(1);
            break;
    }
    appointmentList = new NORTHWNDEntities().Events.ToList().Where(app =>
    ((Convert.ToDateTime(app.StartTime).Date >= Convert.ToDateTime(StartDate.Date)) &&
    (Convert.ToDateTime(app.EndTime).Date <= Convert.ToDateTime(EndDate.Date)))).ToList();
    return appointmentList;
}

internal static DateTime FirstWeekDate(DateTime CurrentDate)
{
    try
    {
        DateTime FirstDayOfWeek = CurrentDate;
        DayOfWeek WeekDay = FirstDayOfWeek.DayOfWeek;
        switch (WeekDay)
        {
            case DayOfWeek.Sunday:
                break;
            case DayOfWeek.Monday:
                FirstDayOfWeek = FirstDayOfWeek.AddDays(-1);
                break;
            case DayOfWeek.Tuesday:
                FirstDayOfWeek = FirstDayOfWeek.AddDays(-2);
                break;
            case DayOfWeek.Wednesday:
                FirstDayOfWeek = FirstDayOfWeek.AddDays(-3);
                break;
            case DayOfWeek.Thursday:
                FirstDayOfWeek = FirstDayOfWeek.AddDays(-4);
                break;
            case DayOfWeek.Friday:
                FirstDayOfWeek = FirstDayOfWeek.AddDays(-5);
                break;
            case DayOfWeek.Saturday:
                FirstDayOfWeek = FirstDayOfWeek.AddDays(-6);
                break;
        }
        return (FirstDayOfWeek);
    }
    catch
    {
        return DateTime.Now;
    }
}

{% endhighlight %}
