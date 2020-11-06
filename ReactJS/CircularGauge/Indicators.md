---
layout: post
title: Indicators
description: indicators
platform: js
control: Circular Gauge
documentation: ug
api: /api/js/ejcirculargauge
---

# Indicators

Indicators simply indicates the current status of the pointer. Indicators are in several formats such as in shape format, textual format and image format.

## Adding Indicator Collection 

Indicators collection is directly added to the scale object. Refer the following code to add indicator collection in a **Gauge** control.

{% highlight javascript %}

"use strict";

var scales = [{
        showIndicators: true,
        indicators: [{
            // For setting indicator height
            height: 10,
            // For setting indicator width
            width: 10,
            // For setting indicator type
            type: "circle",
            // For setting indicator value
            value: 0,
            // For setting indicator position
            position: { x: 185, y: 300 },
        }]
    }];
ReactDOM.render(
            <ej.circulargauge id="circulargauge1" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );


{% endhighlight %}


Execute the above code to render the following output.

![](/js/CircularGauge/Indicators_images/Indicators_img1.png)

## Basic Customization

You can enable indicators by setting **showIndicators** to ‘true’. The **height** and **width** property for the indicators are used to specify the area allocated to the indicator for the width and height respectively. You can use the position collection to position the indicators along **x** and **y** axis. 

Indicators are of several types such as, circle, rectangle, rounded rectangle, text and image. By using the **type** property you can avail those shapes. For image type **imageUrl** property is used. 

{% highlight javascript %}

"use strict";

var scales = [{
        showIndicators: true, minorIntervalValue: 5,
        backgroundColor: "#5DF243",
        border: { width: 1.5, color: "black" },
        showScaleBar: true, radius: 150, size: 5,
        pointers: [{
            backgroundColor: "#5DF243",
            border: { width: 1.5, color: "black" },
            length: 110
        }],
        indicators: [{
            // For setting indicator height
            height: 10,
            // For setting indicator width
            width: 10,
            // For setting indicator type
            type: "circle",
            // For setting indicator value
            value: 0,
            // For setting indicator position
            position: { x: 185, y: 300 },
        }],
    }];
ReactDOM.render(
            <ej.circulargauge id="circulargauge1" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );



{% endhighlight %}

Execute the above code to render the following output.

![](/js/CircularGauge/Indicators_images/Indicators_img2.png)

## State Ranges

State ranges are used to specify the indicator behavior in the specified region. Use **startValue** and **endValue** to set the range bound for the pointer. Whenever the pointer cross the specified region, the indicator attributes are applied for ranges. 

The **backgroundColor** and **borderColor** sets the appearance behavior for the indicators. For text type indicators you can give value for text. And **text** can be changed whenever the pointer crosses its state range area. There are many basic font options available for the text in the state range such as size, fontStyle and fontFamily.

{% highlight javascript %}

"use strict";
  var scales = [{
        showIndicators: true, minorIntervalValue: 5,
        backgroundColor: "#5DF243",
        border: { width: 1.5, color: "black" },
        showScaleBar: true, radius: 150, size: 5,
        pointers: [{
            backgroundColor: "#5DF243",
            border: { width: 1.5, color: "black" },
            length: 110
        }],
        indicators: [{
            // For setting indicator height
            height: 10,
            // For setting indicator width
            width: 10,
            // For setting indicator type
            type: "circle",
            // For setting indicator value
            value: 0,
            // For setting indicator position
            position: { x: 185, y: 300 },
            // For setting indicator state range collection
            stateRanges: [{
                // For setting state range end value height
                endValue: 100,
                // For setting state range start value
                startValue: 0,
                // For setting indicator background color
                backgroundColor: "#5DF243",
                // For setting indicator border color
                borderColor: "Black",
                // For setting indicator text
                text: "",
                // For setting indicator text color
                textColor: "#870505"
            }]
        }],
    }];
ReactDOM.render(
            <ej.circulargauge id="circulargauge1" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );



{% endhighlight %}


Execute the above code to render the following output.

![](/js/CircularGauge/Indicators_images/Indicators_img3.png)

## Multiple Indicators

You can use multiple indicators for a single **Gauge**. Each indicator have a list of state ranges. Refer the following code example for multiple Indicators.

{% highlight javascript %}
"use strict";
  var scales = [{
        readOnly: false,
        showIndicators: true, showRanges: true,
        minorIntervalValue: 5,
        showScaleBar: true, radius: 150, size: 5,
        pointers: [{
            length: 110, value: 70
        }],
        ranges: [{
            startValue: 0, endValue: 50,
            backgroundColor: "Green",
            placement: "far", distanceFromScale: -30
        },
        {
            startValue: 50, endValue: 100,
            backgroundColor: "red",
            placement: "far", distanceFromScale: -30
        }],
        indicators: [
        //Indicator1
        {
            height: 10,
            width: 10,
            type: "circle",
            value: 0,
            position: { x: 165, y: 300 },
            stateRanges: [{
                endValue: 50,
                startValue: 0,
                backgroundColor: "#24F92F",
                borderColor: "Black"
            }, {
                endValue: 50,
                startValue: 100,
                backgroundColor: "#322C04",
                borderColor: "Black"
            }]
        },
        //Indicator2
        {
            height: 10,
            width: 10,
            type: "circle",
            value: 0,
            position: { x: 215, y: 300 },
            stateRanges: [{
                endValue: 50,
                startValue: 0,
                backgroundColor: "#600000",
                borderColor: "Black"
            }, {
                endValue: 100,
                startValue: 50,
                backgroundColor: "#FF4F2A",
                borderColor: "Black"
            }]
        }],
    }];
ReactDOM.render(
            <ej.circulargauge id="circulargauge1" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );


{% endhighlight %}


Execute the above code to render the following output.

![](/js/CircularGauge/Indicators_images/Indicators_img4.png)

