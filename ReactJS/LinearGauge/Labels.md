---
layout: post
title: Labels
description: labels
platform: js
control: Linear Gauge
documentation: ug
api: /api/js/ejlineargauge
---

# Labels

Labels are units that are used to display the values in the scales. You can customize Labels with the properties like angle, color, font, opacity, etc.

## Label Customization

**Appearance**

* The attribute **angle** is used to display the labels in the specified angles and **color** attribute is used to display the labels in specified color. You can adjust the opacity of the label with the property **opacity** and the values of it lies between 0 and 1.The **includeFirstValue** is a special property by enabling this property, the first value of the label is not rendered.

* Font option is also available on the labels. The basic three properties of fonts such as size, family and style can be achieved by **size**, **fontStyle** and **fontFamily**. Labels are two types such as major and minor.Major type labels are for major interval values and minor type labels are for minor interval values.


{% highlight html %}

<div id="LinearGauge1"></div>

{% endhighlight %}

{% highlight javascript %}

  "use strict";
var scales = [  
            {
   backgroundColor: "transparent",
                border: { color: "transparent", width: 0 },
                showBarPointers: true, showCustomLabels: true, showMarkerPointers: false,
                //Adding bar pointer collection
                barPointers: [{ width: 10 }],
                //Adding label collection
                labels: [{
                    font: { size: "12px", fontFamily: "Arial", fontStyle: "Bold" },
                    textColor: "Red",
                    angle: 10,
                    opacity: 0.5,
                    includeFirstValue: false
                }],
                //Adding ticks collection
                ticks: [{
                    type: "majorinterval", width: 2,
                    color: "#8c8c8c", distanceFromScale: { x: 7, y: 0 }
                },
                {
                    type: "minorinterval", width: 1, height: 6,
                    color: "#8c8c8c", distanceFromScale: { x: 7, y: 0 }
                }]
            }];
var frame = {
                innerWidth: 8,
                outerWidth: 10,
                // For setting back ground Image URL
                backgroundImageUrl: "Gauge_linear_light.png"
            };
ReactDOM.render(
    <EJ.LinearGauge id="lineargauge"
    labelColor= "#8c8c8c"
    load="loadGaugeTheme" frame = {frame} scales = {scales}  enableAnimation = {false} value = {40}>             </EJ.LinearGauge>,
          document.getElementById('LinearGauge1')
);

{% endhighlight %}



Execute the above code to render the following output.


![](/js/LinearGauge/Labels_images/Labels_img1.png)

## Unit text and Positioning

* The **unitText** property is used to add some text along with the labels. For example, in speedometer, you need to mention the units in kph. You can also add the unit text in front of the labels. To achieve this use the enumerable property **unitTextPosition**. 

* Labels can be positioned with the help of two properties such as **distanceFromScale** and **placement**. **distanceFromScale** property defines the distance between the scale and labels. **Placement** property is used to locate the labels with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.


{% highlight html %}

<div id="LinearGauge1"></div>

{% endhighlight %}

{% highlight javascript %}

"use strict";
var scales = [  
            {
    width: 5, majorIntervalValue: 25, minorIntervalValue: 5,
               backgroundColor: "White", showCustomLabels: true,
               showMarkerPointers: false, showBarPointers: true,
               direction: ej.datavisualization.LinearGauge.Directions.Clockwise,
               type: "roundedrectangle",
               border: { color: "#AEC75F", width: 2 },
               // Adding bar pointer collection
               barPointers: [{ width: 4, backgroundColor: "Red" }],
               // Adding label collection
               labels: [{
                   angle: 90,
                   distanceFromScale: { x: 0, y: 60 },
                   unitText: "%"
               }],
               // Adding tick collection
               ticks: [{
                   type: "majorinterval", width: 2,
                   color: "#8c8c8c", distanceFromScale: { x: 0, y: 25 }
               },
               {
                   type: "minorinterval", width: 1, height: 6,
                   color: "#8c8c8c", distanceFromScale: { x: 0, y: 25 }
               }],
               customLabels: [{
                   value: "Download in Progress", position: { x: 50, y: 20 },
               }]
            }];
             var frame = {           
                // For setting back ground Image URL
                backgroundImageUrl: "Gauge_linear_light1.png"
            };
ReactDOM.render(
    <EJ.LinearGauge id="lineargauge"
    labelColor= "#8c8c8c"
    load="loadGaugeTheme" frame = {frame} orientation = "Horizontal" scales = {scales}  width = {600} height = {250} value = {31} labelColor = "Black" enableResize = {true}  enableAnimation = {false}>
    </EJ.LinearGauge>,
          document.getElementById('LinearGauge1')
);


{% endhighlight %}



Execute the above code to render the following output.


![](/js/LinearGauge/Labels_images/Labels_img2.png)



