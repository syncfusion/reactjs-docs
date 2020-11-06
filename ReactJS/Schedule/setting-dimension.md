---
title: Setting dimension
description: Setting dimension for Schedule control
platform: ReactJS
control: schedule
documentation: ug
keywords: dimension, cell dimension, cell width, cell height
---
# Setting Dimension

The dimension normally refers to the height and width of the element. With Scheduler, it is possible to set 2 kinds of dimensions.

* Scheduler dimension (Scheduler control height and width)
* Cell dimension (Scheduler cells height and width)

## Scheduler Dimension

The [height](/api/js/ejschedule#members:height) and [width](/api/js/ejschedule#members:width) properties can be defined to set the outer dimension of the Scheduler control.

{% highlight html %}

var dManager = [{
    Id: 100,
    Subject: "Research on Sky Miracles",
    StartTime: new Date(2015, 04, 05, 9, 00),
    EndTime: new Date(2015, 04, 05, 10, 30),
    OwnerId: 3,
    RoomId: 2
}];

var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" width="70%" height="500px" currentDate={new Date(2017, 5, 5)} appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

N> The height and width properties accepts both **pixel** and **percentage** values.

## Scheduler Cell Dimensions

### Cell Height

The [cellHeight](/api/js/ejschedule#members:cellheight) property allows the Scheduler to set the height of the cells in pixels. The appointment height in vertical mode changes accordingly as per the cell size within which it renders.

{% highlight html %}

var dManager = [{
    Id: 100,
    Subject: "Research on Sky Miracles",
    StartTime: new Date(2015, 04, 05, 9, 00),
    EndTime: new Date(2015, 04, 05, 10, 30)
}];

var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" cellHeight="40px" currentDate={new Date(2017, 5, 5)} appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

N> In **desktop** mode, the default height value of the cells is set to **20px**, whereas for **mobile** mode – the Scheduler cells are rendered with **40px** by default.

### Cell Auto-Height

The height of the cells specifically in timeline view can be made to adjust automatically based on its exceeding appointment count. It is controlled by an API named [showOverflowButton](/api/js/ejschedule#members:showOverflowButton) which accepts true or false value, denoting whether to enable/disable the cell auto-height adjusting option. To enable this option, set the value of `showOverflowButton` as `false` whereas its default value is `true`.

In **Vertical** view, the same functionality is made applicable only in the **Month View** whereas in **Horizontal** mode, it is applicable in all the views.

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
            <EJ.Schedule id="Schedule1" width="100%" height="525px" showOverflowButton={false} currentView={ej.Schedule.CurrentView.Month} currentDate={new Date(2017, 5, 5)} appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

### Cell Width

The [cellWidth](/api/js/ejschedule#members:cellwidth) property allows the Scheduler to set the width of the cells in pixels. The appointment width adjusts based on the cell width of the Scheduler.

{% highlight html %}

var dManager = [{
    Id: 100,
    Subject: "Research on Sky Miracles",
    StartTime: new Date(2015, 11, 2, 9, 00),
    EndTime: new Date(2015, 11, 2, 10, 30)
}];

var Scheduler = React.createClass({
    render: function () {
        return (
            <EJ.Schedule id="Schedule1" cellWidth="97px" showOverflowButton={false} currentView={ej.Schedule.CurrentView.Month} currentDate={new Date(2017, 5, 5)} appointmentSetings-dataSource={dManager}>
            </EJ.Schedule>
       );
    }
});

ReactDOM.render(<Scheduler />, document.getElementById('schedule-default'));

{% endhighlight %}

N> When the **cellHeight** and **cellWidth** properties are set with some specific pixel values, the cell size does not adapt to the responsive behavior of the Scheduler while resizing it in desktop/mobile mode.
