---
layout: post
title: Ranges-and-Frames
description: ranges and frames
platform: js
control: Circular Gauge
documentation: ug
api: /api/js/ejcirculargauge
---

# Ranges and Frames

Ranges are used to specify or group the scale values. By using ranges, you can describe the values in the pointers. 

## Adding Range Collection

Range collection is directly added to the scale object. Refer the following code example to add range collection in a **Gauge** control. 

{% highlight javascript %}

"use strict";

var scales = [{
        showRanges: true,
        ranges: [{
            startValue: 20,
            endValue: 80
        }]
    }];
ReactDOM.render(
            <ej.circulargauge id="circulargauge" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );


{% endhighlight %}

## Range Customization

**Appearance**

The API **size** is used to specify the width of the ranges.  The major attributes for ranges are **startValue** and **endValue**. **startValue** defines the start position of the ranges and **endValue** defines the end position of the ranges.

**StartWidth** and **endWidth** are used to specify the range width at the starting and ending position of the ranges. You can add the gradient effects to the ranges by using **gradient** object.

{% highlight javascript %}

"use strict";

var scales = [{
        showRanges: true,
        showScaleBar: true,
        radius: 150, size: 2,
        ranges: [{
            //For setting range start value
            startValue: 20,
            //For setting range end value
            endValue: 80,
            //For setting range background color
            backgroundColor: "Green",
        }]
    }];
ReactDOM.render(
            <ej.circulargauge id="circulargauge" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );


{% endhighlight %}

Execute the above code to render the following output.

![](/js/CircularGauge/Ranges-and-Frames_images/Ranges-and-Frames_img1.png)

## Colors and Border

By customizing the ranges, the appearance of the **Gauge** can be improved. The range border is modified with the object called **border**. It has two border property such as **color** and **width.** These are used to customize the border color of the ranges and border width of the ranges. 

You can set the background color to improve the look and feel of the **Circular Gauge**. For customizing the background color of the ranges, **backgroundColor** is used.

{% highlight javascript %}

"use strict";

var scales = [{
        showRanges: true,
        showScaleBar: true,
        radius: 150, size: 2,
        ranges: [{
            //For setting range start value
            startValue: 20,
            //For setting range end value
            endValue: 80,
            //For setting range background color
            backgroundColor: "yellow",
            //For setting range border
            border: { color: "green", width: 2 },
        }]
    }];
ReactDOM.render(
            <ej.circulargauge id="circulargauge" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );



{% endhighlight %}


Execute the above code to render the following output.

![](/js/CircularGauge/Ranges-and-Frames_images/Ranges-and-Frames_img2.png)

## Positioning the ranges

You can position ranges using two properties such as **distanceFromScale** and **placement**. **distanceFromScale** property defines the distance between the scale and range. **Placement** property is used to locate the pointer with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.

{% highlight javascript %}

"use strict";
var scales = [{
        showRanges: true,
        showScaleBar: true,
        radius: 150, size: 2,
        ranges: [{
            //For setting range start value
            startValue: 0,
            //For setting range end value
            endValue: 100,
            //For setting range background color
            backgroundColor: "Green",
            //For setting range placement
            placement: "far",
            //For setting distance between scale and ranges
            distanceFromScale: -30,
            //For setting range border
            border: { color: "Black", width: 2 },
        }]
    }];
ReactDOM.render(
            <ej.circulargauge id="circulargauge" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );



{% endhighlight %}
Execute the above code to render the following output.

![](/js/CircularGauge/Ranges-and-Frames_images/Ranges-and-Frames_img3.png)

## Multiple Ranges

You can set multiple ranges by adding an array of ranges objects. Refer the following code example for multiple ranges functionality.

{% highlight html %}

<div id="circulargauge"></div>

{% endhighlight %}

{% highlight javascript %}

 "use strict";
var scales = [{
        showRanges: true,
        showScaleBar: true,
        radius: 150, size: 2,
        pointers: [{
            value: 40,
            showBackNeedle: true,
            length: 100
        }],
        ranges: [
        //For setting range1
        {
            startValue: 0, endValue: 50,
            backgroundColor: "Green",
            placement: "far", distanceFromScale: -30
        },
        //For setting range2
        {
            startValue: 50, endValue: 80,
            backgroundColor: "yellow",
            placement: "far", distanceFromScale: -30
        },
        //For setting range3
        {
            startValue: 80, endValue: 100,
            backgroundColor: "red",
            placement: "far", distanceFromScale: -30
        }]
    }];
ReactDOM.render(
            <ej.circulargauge id="circulargauge" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );



{% endhighlight %}



Execute the above code to render the following output.

![](/js/CircularGauge/Ranges-and-Frames_images/Ranges-and-Frames_img4.png)

## Frames

Frame is the element that decides the appearance of the **Circular Gauge**. You can customize it using the object called **frame**.  It has the properties such as frameType, backGroundUrl, halfCircleFrameStartAngle and halfCircleFrameEndAngle.

**frameType** is used to specify whether frame is a half circle frame or full circle frame. **halfCircleFrameStartAngle** and **halfCircleFrameEndAngle** are used to specify the angle for **Gauge** with frame type as half circle. **backgroundUrl** is used to set the background image for the frame.

{% highlight javascript %}

"use strict";
  var scales = [{
        startAngle: 180, sweepAngle: 180,
        pointers: [{
            needleType: "rectangle",
            width: 1, length: 120, value: 40
        }],
        pointerCap: { radius: 50 },                
    }];
    var frame = {
        frameType: "halfcircle",
        //For setting half circle frame start angle
        halfCircleFrameStartAngle: 205,
        //For setting half circle frame end angle
        halfCircleFrameEndAngle: 335,
    };
ReactDOM.render(
            <ej.circulargauge id="circulargauge" frame={frame} backgroundColor="#FFCCCC" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );



{% endhighlight %}

Execute the above code to render the following output.

![](/js/CircularGauge/Ranges-and-Frames_images/Ranges-and-Frames_img5.png)

