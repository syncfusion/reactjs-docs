---
title: Getting started with Schedule component in React JS	
description: Rendering a basic Scheduler with local data
platform: ReactJS
control: schedule
documentation: ug
keywords: ejschedule, schedule, schedule widget, js schedule 
---

# Getting Started

An introduction to start with ReactJS can be referred from [here](/reactjs/overview#getting-started-with-react). To get start with the usage of Schedule control in ReactJS platform, create a React application layout and refer the following dependencies to it. Refer the individual script references required to render the Schedule control from [here](/reactjs/schedule/dependencies).

{% highlight html %}

<head>
    <meta charset="utf-8" />
    <title>Getting Started - Schedule</title>
    <!-- CSS reference -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />

    <!-- Script references -->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/react.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/react-dom.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.34/browser.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.web.react.min.js"></script>
</head>

{% endhighlight %}

N> Uncompressed version of the library files are also available which is used for development or debugging purpose and can be generated from the custom script [here](http://csg.syncfusion.com).

## Control Initialization

Scheduler can be initialized in either of the 2 ways by making use of the jsx template or without it.

### Using jsx Template

While making use of jsx template, we have to create both the HTML and jsx files. The `.jsx` file should be converted into `.js` file using [gulp](/reactjs/overview#converting-jsx-to-javascript-with-react) command and then needs to be added as a reference in the HTML page.

#### HTML file

{% highlight html %}

<div id="schedule-default"></div>
<script src="scripts/default.js"></script>

{% endhighlight %}

#### JSX file

{% highlight html %}

var dManager = [{
    Id: 1,
    Subject: "Bering Sea Gold",
    StartTime: new Date(2014, 4, 5, 5, 30),
    EndTime: new Date(2014, 4, 5, 7, 30),
    Description:"",
    AllDay: false,
    Recurrence: false
}];

ReactDOM.render(
      <EJ.Schedule id="Schedule1"
                   width="100%"
                   height="525px"
                   currentDate={new Date(2014, 4, 5)}
                   appointmentSettings-dataSource={dManager}
                   appointmentSettings-id="Id"
                   appointmentSettings-subject="Subject"
                   appointmentSettings-startTime="StartTime"
                   appointmentSettings-endTime="EndTime"
                   appointmentSettings-description="Description"
                   appointmentSettings-allDay="AllDay"
                   appointmentSettings-recurrence="Recurrence"
                   appointmentSettings-recurrenceRule="RecurrenceRule">
      </EJ.Schedule>, document.getElementById('schedule-default')
);

{% endhighlight %}

N> The above jsx template needs to be converted from `.jsx` to `.js` extension by using `gulp` NuGet package (refer [here](/reactjs/overview#converting-jsx-to-javascript-with-react)) and then it must be referred in the HTML page.


![](Getting-started_images/Getting-started_img1.png)

### Using without jsx Template

Create a Div element within the body section of the HTML document, where the Scheduler needs to be rendered.

{% highlight html %}

<body>
	<div id="schedule"></div>
</body>

{% endhighlight %}

Initialize the Schedule control by adding the following script code to the body section of the HTML document.

{% highlight html %}

<body> 
    <div id="schedule"></div>

    <script>
        var dManager = [{
            Id: 1,
            Subject: "Bering Sea Gold",
            StartTime: new Date(2014, 4, 5, 5, 30),
            EndTime: new Date(2014, 4, 5, 7, 30),
            Description:"",
            AllDay: false,
            Recurrence: false
        }];
        ReactDOM.render(
            React.createElement(EJ.Schedule, {
                "id": "Schedule1",
                "width": "100%",
                "height": "525px",
                "currentDate": new Date(2014, 4, 5),
                "appointmentSettings-dataSource": dManager,
                "appointmentSettings-id": "Id",
                "appointmentSettings-subject": "Subject",
                "appointmentSettings-startTime": "StartTime",
                "appointmentSettings-endTime": "EndTime",
                "appointmentSettings-description": "Description",
                "appointmentSettings-allDay": "AllDay",
                "appointmentSettings-recurrence": "Recurrence",
                "appointmentSettings-recurrenceRule": "RecurrenceRule"
            }),document.getElementById('schedule')
        );
    </script>
</body>

{% endhighlight %}

## Working with timeZone Settings

Initially, the system timezone is preferred as the Schedule's default timezone. When some specific timezone is explicitly defined to the Schedule, it will be set to it.

Likewise, we can also set different timezones for the appointments. Usually, the system timezone is assigned as the appointment's default timezone and it will be positioned on the Scheduler based on the start/end time range and timezone assigned to it.

To set Scheduler timeZone and its appointment timeZone values, refer the below code example -

{% highlight html %}

<body> 
    <div id="schedule"></div>

    <script>
        var dManager = [{
            Id: 1,
            Subject: "Bering Sea Gold",
            StartTime: new Date(2014, 4, 5, 5, 30),
            StartTimeZone: "UTC +02:00",
            EndTime: new Date(2014, 4, 5, 7, 30),
            EndTimeZone: "UTC +02:00",
            Description:"",
            AllDay: false,
            Recurrence: false
        }];
        ReactDOM.render(
            React.createElement(EJ.Schedule, {
                "id": "Schedule1",
                "width": "100%",
                "height": "525px",
                "currentDate": new Date(2014, 4, 5),
                "timeZone": "UTC +05:30", // timeZone set to Scheduler
                "appointmentSettings-dataSource": dManager,
                "appointmentSettings-id": "Id",
                "appointmentSettings-subject": "Subject",
                "appointmentSettings-startTime": "StartTime",
                "appointmentSettings-startTimeZone": "StartTimeZone",
                "appointmentSettings-endTime": "EndTime",
                "appointmentSettings-endTimeZone": "EndTimeZone",
                "appointmentSettings-description": "Description",
                "appointmentSettings-allDay": "AllDay",
                "appointmentSettings-recurrence": "Recurrence",
                "appointmentSettings-recurrenceRule": "RecurrenceRule"
            }),document.getElementById('schedule')
        );
    </script>
</body>

{% endhighlight %}
