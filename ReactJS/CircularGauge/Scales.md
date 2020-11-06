---
layout: post
title: Scales
description: scales
platform: js
control: Circular Gauge
documentation: ug
api: /api/js/ejcirculargauge
---

# Scales

**Scales** are the basic functional block of the **Circular Gauge**. By customizing the scales, the appearance of the **Gauge** can be improved. The functional blocks of Circular Gauge are 

* Pointers

* Labels

* CustomLabels

* Indicators

* Ticks

* Ranges

* Sub gauges.

## Adding Scale Collection

**Scale collection** is directly added to the **Gauge** object. Refer the following code example to add scale collection in **Gauge** control.

{% highlight javascript %}

"use strict";
 var scales = [{
        radius: 150,
        ranges: ranges,
    }];
    var ranges = [
    {
        distanceFromScale: -30,
        startValue: 0,
        endValue: 70
    }];
ReactDOM.render(
            <ej.circulargauge id="circulargauge1" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );

{% endhighlight %}


Execute the above code to render the following output.

![](/js/CircularGauge/Scales_images/Scales_img1.png)

## Scale Customization

**Colors and Border**

The Scale border is modified with the object called **border**. It has two border property namely **color** and **width** which are used to customize the border color of the scale and border width of the scale. Setting the background color improves the look and feel of the **Circular Gauge**. You can customize the background color of the scale using **backgroundColor**. 


{% highlight javascript %}

"use strict";

var scales = [{
        showScaleBar: true,
        radius: 150,
        backgroundColor: "Red",
        border: {
            //For scale border color
            color: "Blue",
            //For scale border width
            width: 3
        },
        pointers: [{ length: 100 }]
    }];

ReactDOM.render(
            <ej.circulargauge id="circulargauge1" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );

{% endhighlight %}



Execute the above code to render the following output.

![](/js/CircularGauge/Scales_images/Scales_img2.png)

**Pointer Cap**

**Pointer cap** is a circular shape element that is located at the center of the **Circular Gauge**. The pointer cap is one of the cynosure of the **Circular Gauge**. By customizing the pointer cap, Gauge style is improved. The pointer cap is modified with the object **pointerCap**. It contains radius, borderColor, borderWidth, interiorGradient and backgroundColor properties. The property **radius** is used to set the radius for the pointer cap. **interiorGradient** is used to provide the gradient effects to the pointer cap.


{% highlight javascript %}

"use strict";

var scales = [{
        pointerCap: {
            // For setting pointer cap radius
            radius: 10,
            // For setting pointer cap border width
            borderWidth: 4,
            // For setting pointer cap border color
            borderColor: "Blue",
            // Fors etting pointer cap background color
            backgroundColor: "Red"
        }
    }];

ReactDOM.render(
            <ej.circulargauge id="circulargauge1" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );


{% endhighlight %}




Execute the above code to render the following output.

![](/js/CircularGauge/Scales_images/Scales_img3.png)

**Appearance**

**Circular Gauge** contains two types of scale direction such as clockwise and counter clockwise. You can set them by enumerable property called **direction**. And you can set the minimum and maximum values for the scale with the properties **minimum** and **maximum**. The two properties **minorIntervalValue** and **majorIntervalValue** are the values used to set interval value for the ticks and labels. The **radius** property is used to set the radius value for the circular scale and the **size** property is used to set the scale bar width. You can also adjust the Opacity of the scale with the property **opacity**. The value for opacity lies between 0 and 1. You can also give some shadow effects for the scale by using the property **shadowOffset.** The property **startAngle** is used to set starting position of the scale at certain angle and **sweepAngle** is used to shrink or expand the scale to certain angle. 



{% highlight javascript %}

"use strict";

var scales = [{
        // For setting scale bar size
        size: 30,
        // For setting scale radius
        scaleRadius: 130,
        // For setting scale minimum value
        minimum: 20,
        // For setting scale maximum value
        maximum: 120,
        // For setting scale major interval value
        majorIntervalValue: 20,
        // For setting scale minor interval
        minorIntervalValue: 5,
        // For setting scale direction
        direction: ej.datavisualization.CircularGauge.Directions.CounterClockwise,
        // For setting scale background color
        backgroundColor: "red",
        // For setting scale bar opacity
        opcity: 0.5,
        // For setting scale bar shadow offset
        shadowOffset: 20
    }];

ReactDOM.render(
            <ej.circulargauge id="circulargauge1" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );


{% endhighlight %}




Execute the above code to render the following output.

![](/js/CircularGauge/Scales_images/Scales_img4.png)

**Enable/Disable properties**

You can enable / disable properties in Circular Gauge using some properties in scale collection. The **showIndicators** property is used to enable/disable the indicators. **ShowLabels**, **showTicks**, **showRanges**, **showPointers** ans **showScaleBar** are used to enable/ disable labels, ticks, ranges, pointers and scale bar respectively. 

## Multiple Scales

You can set **Multiple scales** for a single **Circular Gauge** control by using an array of scale objects. Each scale object is independent of each other. The following code example refers to two scale objects in a **Gauge**.



{% highlight javascript %}
"use strict";
    var scales = [
    // For setting first scale
    {
        size: 10,
        showScaleBar: true,
        scaleRadius: 150,
        minimum: 20,
        maximum: 120,
        majorIntervalValue: 20,
        minorIntervalValue: 5,
        direction: ej.datavisualization.CircularGauge.Directions.Clockwise,
        shadowOffset: 20,
        pointers: [{ value: 50, length: 120 }]
    },
    // For setting second scale
    {
        size: 10,
        showScaleBar: false,
        scaleRadius: 80,
        majorIntervalValue: 10,
        direction: ej.datavisualization.CircularGauge.Directions.CounterClockwise,
        opcity: 0.5,
        shadowOffset: 5,
        pointers: [{ value: 40, length: 50 }],
        ticks: [{ color: "red", distanceFromScale: 80 }],
        labels: [{ distanceFromScale: 40, color: "red" }]

    }];
ReactDOM.render(
            <ej.circulargauge id="circulargauge1" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );


{% endhighlight %}

Execute the above code to render the following output.

![](/js/CircularGauge/Scales_images/Scales_img5.png)

