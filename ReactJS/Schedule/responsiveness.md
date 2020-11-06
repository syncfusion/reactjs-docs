---
title: Schedule - Responsiveness
description: Display Scheduler with responsiveness
platform: ReactJS
control: schedule
documentation: ug
keywords: responsive, responsiveness, auto size
---
# Responsiveness

Scheduler is provided with default **responsive** support, so that it adjust or auto-resize it’s UI content based on the window or the container size on which it is placed.

## Auto-Resizing Scheduler

By default, setting 100% width to the Scheduler makes it adaptable to the window or its parent container, as and when the browser is resized. This will not allow the scheduler to adapt height-wise.

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
            <EJ.Schedule id="Schedule1" width="100%" currentDate={new Date(2017, 5, 5)} appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

To auto-resize the Scheduler height – set the **height** property of the Scheduler to **100%** and also set some specific height (either percentage or pixel values) to its parent container (or) to the HTML and body tag elements as shown below.

{% highlight html %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" style="height:100%">
    <head>
        <title>My first HTML page</title>
        <!-- required CSS REFERENCES -->
        <!-- required SCRIPT REFERENCES -->
    </head>
    <body style="height:100%">
        <!--Container for ejScheduler widget-->
        <div id="schedule-default"></div>
    </body>
</html>

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
            <EJ.Schedule id="Schedule1" height="100%" currentDate={new Date(2017, 5, 5)} appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

N> When the Scheduler width is set to have **less** **than** **600px**, then the View selection options will be displayed in a **navigation** **drawer**.

Also, whenever the Scheduler resizes - the width of the work cells adjusts automatically (if no **cellWidth** property is specified with pixel values), but the height of the cells are kept to remain as same as 20px until **cellHeight** property is set explicitly with some pixel values.

## Scheduler in Mobile/Tablets

The Scheduler layout adapts automatically in the mobile and tablet devices with the appropriate UI changes, as the [isResponsive](/api/js/ejschedule#members:isresponsive) property is set to **true** by default. In case, if the user wants to display the normal scheduler in mobile devices without any adaptive enhancements, then the `isResponsive` property can be set to false.

Some of the default changes done for adaptive Scheduler to render in mobile devices are as follows,

* Animation effect introduced between view/date navigation.
* Cell Height increased
* The header date display changes (displayed next to the navigation icons).
* View options displayed in Navigation drawer
* Time cell width decreased
* Quick window display blocked on cell/appointment single click.
* Appointment resizing action blocked.
* Multiple cell selection blocked.
* Delete appointment option made available within the appointment window.
* Week header display in month view hidden.
* With Multiple resources - only one resource is viewable initially on the screen and to further look onto other resources, user need to swipe the screen.

N> To make the Scheduler control to react as responsive in mobile/tablet devices, it is necessary to refer the additional [ej.responsive.css](http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/responsive-css/ej.responsive.css) file in the application.

The following code snippet depicts the Scheduler code with responsive set to true.

{% highlight html %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" style="height:100%">
    <head>
        <title>My first HTML page</title>
        <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
        <link href=" http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/responsive-css/ej.responsive.css" rel="stylesheet" />
        <!-- Other required SCRIPT REFERENCES -->
    </head>
    <body style="height:100%">
        <!--Container for ejScheduler widget-->
        <div id="schedule-default"></div>
    </body>
</html>

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
            <EJ.Schedule id="Schedule1" isResponsive={true} currentDate={new Date(2017, 5, 5)} appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}
