---
layout: post
title: Basic-Settings
description: basic settings
platform: js
control: Linear Gauge
documentation: ug
api: /api/js/ejlineargauge
---

# Basic Settings

## Adding Dimension

* The basic customization for any control is setting the dimension. Here dimension refers the two major attributes, height and width. The height and width assigned in the control will render the canvas element in the given size. 

* The value attribute is used to set all pointer value in the Linear Gauge control. The attributes, minimum and maximum value are used to set the minimum value and maximum value for all the scales exist in the Linear Gauge control.


{% highlight html %}

<div id="LinearGauge1"></div>

{% endhighlight %}

{% highlight javascript %}

  "use strict";

  var scales = [{
  border: { color: "transparent", width: 0 },
                showMarkerPointers: false, showBarPointers: true,
                // Adding bar pointer collection
                barPointers: [{ width: 5, backgroundColor: "Grey" }],
                // Adding ticks collection
                ticks: [{
                    type: "majorinterval", width: 2,
                    color: "#8c8c8c", distanceFromScale: { x: 7, y: 0 }
                },
                {
                    type: "minorinterval", width: 1, height: 6,
                    color: "#8c8c8c", distanceFromScale: { x: 7, y: 0 }
                }]
            }];
        
ReactDOM.render(                    
              <EJ.LinearGauge id="lineargauge1" scales = {scales} height= {500} width= {300}  minimum= {10} maximum ={110} value={78}></EJ.LinearGauge>,                    
                     document.getElementById('LinearGauge1')
                     );



{% endhighlight %}



Execute the above code to render the following output.



![](/js/LinearGauge/Basic-Settings_images/Basic-Settings_img1.png)



## Adding frame

* Frame is the element that decides the appearance of the **Linear Gauge**. You can customize it by using the object called **frame.** It contains frame inner width, frame outer width and frame background image URL properties. 

* The **innerWidth** of the frame defines the distance between the canvas element and the frame and the **outerWidth** refers to distance from the frame. **backgroundUrl** is used to set the background image for the frame.


{% highlight html %}

<div id="LinearGauge1"></div>

{% endhighlight %}

{% highlight javascript %}

"use strict";
var scales = [{
                backgroundColor: "transparent",
                border: { color: "transparent", width: 0 },
                showMarkerPointers: false, showBarPointers: true,
                // Adding bar pointer collection
                barPointers: [{ width: 5, backgroundColor: "Grey" }],
                // Adding ticks collection
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
                // For setting frame inner width
                innerWidth: 8,
                // For setting frame outer width
                outerWidth: 10,
                // For setting back ground Image URL
                backgroundImageUrl: "Gauge_linear_light.png"
            };
ReactDOM.render(
    <EJ.LinearGauge id="lineargauge"
    labelColor= "#8c8c8c"
    load="loadGaugeTheme"  frame = {frame} scales = {scales} value={80}>                    
    </EJ.LinearGauge>,
          document.getElementById('LinearGauge1')
);


{% endhighlight %}



Execute the above code to render the following output.



![](/js/LinearGauge/Basic-Settings_images/Basic-Settings_img2.png)



## Appearance

* The attribute orientation is used to render the Linear Gauges either in horizontal position or vertical position.You can set the background color for the Linear Gauge for better appearance using the backgroundColor property. borderColor specifies the border color of the Linear Gauge. You can also add gradient effects to Linear Gauge with the help of pointerGradient1 and pointerGradient2 attribute.

* Theme is the basic property of any control. It is used to set the theme for Linear Gauge. There are two types of themes used for Linear Gauge such as

 * flatlight

 * flatdark


{% highlight html %}

<div id="LinearGauge1"></div>

{% endhighlight %}

{% highlight javascript %}

 
"use strict";
var scales = [{
                backgroundColor: "transparent",
                border: { color: "transparent", width: 0 },
                showMarkerPointers: false, showBarPointers: true,
                // Adding bar pointer collection
                barPointers: [{ width: 5, backgroundColor: "Grey" }],
                // Adding ticks collection
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
                // For setting frame inner width
                innerWidth: 8,
                // For setting frame outer width
                outerWidth: 10,
                // For setting back ground Image URL
                backgroundImageUrl: "Gauge_linear_light1.png"
            };
ReactDOM.render(
    <EJ.LinearGauge id="lineargauge"
    labelColor= "#8c8c8c"
    load="loadGaugeTheme"  frame = {frame} orientation = "Horizontal" scales = {scales} value={80}>
    </EJ.LinearGauge>,
          document.getElementById('LinearGauge1')
);



{% endhighlight %}



Execute the above code to render the following output.

![](/js/LinearGauge/Basic-Settings_images/Basic-Settings_img3.png)



## Responsive 

* For any display devices, the control is to be rendered based on the space in that device. The control must be responsive. For this purpose resizing property is present in **Linear Gauge** control. 

* The **Linear Gauge** renders with the specified value. When the browser changes its size, the canvas element checks the dimension with its parent element and if there are any changes in parent dimension, gauge control also changes the dimension based on its parent changes. You can enable this feature using **isResponsive** property**.**


{% highlight html %}

<div id="LinearGauge1"></div>

{% endhighlight %}

{% highlight javascript %}

"use strict";
var scales = [{
                backgroundColor: "transparent",
                border: { color: "transparent", width: 0 },
                showMarkerPointers: false, showBarPointers: true,
                // Adding bar pointer collection
                barPointers: [{ width: 5, backgroundColor: "Grey" }],
                // Adding ticks collection
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
                // For setting frame inner width
                innerWidth: 8,
                // For setting frame outer width
                outerWidth: 10,
                // For setting back ground Image URL
                backgroundImageUrl: "Gauge_linear_light1.png"
            };
ReactDOM.render(
    <EJ.LinearGauge id="lineargauge"
    labelColor= "#8c8c8c"
    load="loadGaugeTheme"  frame = {frame} orientation = "Horizontal" isResponsive = {true} scales = {scales} value={80}>                    
    </EJ.LinearGauge>,
          document.getElementById('LinearGauge1')
);


{% endhighlight %}



Execute the above code to render the following output.


![](/js/LinearGauge/Basic-Settings_images/Basic-Settings_img4.png)

Responsiveness of the linear gauge is controlled by using `enableResize` property.


{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="lineargauge"
    width={100} height={100} enableResize={true}>                    
    </EJ.LinearGauge>,
          document.getElementById('LinearGauge1')
);

{% endhighlight %}


## Localization

**LinearGauge** supports localization for its axis labels and tooltip. To render the gauge with specific culture you have to refer the corresponding globalize culture script and need to specify the culture name in `locale` property of gauge.

**Enable Group Separator** is used to Convert the date object to string while using the locale settings, you can set `enableGroupSeparator` property as **true**.



{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="lineargauge"
    locale="en-fr" enableGroupSeparator={true}>                    
    </EJ.LinearGauge>,
          document.getElementById('LinearGauge1')
);

{% endhighlight %}




