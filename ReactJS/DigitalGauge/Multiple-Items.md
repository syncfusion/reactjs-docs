---
layout: post
title: Multiple-Items
description: multiple items 
platform: js
control: Digital Gauge
documentation: ug
---

# Multiple Items 

The text in the **Digital Gauge** is positioned with position object. This object contains two attributes such as **x** and **y.** The **x** variable positions the text in the horizontal axis and **y** variable positions the text in the vertical axis.

{% highlight html %}

<div id="DigitalGauge1"></div>

{% endhighlight %}

{% highlight javascript %}

"use strict";

 var items = [
 // For Item 1
            {
                // For setting text
                value: "BLUE",
                segmentSettings: {
                    color: "blue"
                },
                position: {
                    x: 90,
                    y: 0
                }
            },
            // For Item 2
            {
                // For setting text
                value: "RED",
                segmentSettings: {
                    color: "red"
                },
                position: {
                    x: 90,
                    y: 50
                }
            },
            // For Item 3
            {
                // For setting text
                value: "PINK",
                segmentSettings: {
                    color: "pink"
                },
                position: {
                    x: 90,
                    y: 100
                }	
            }
            ];   
var frame = {
                backgroundImageUrl: "Board1.jpg"
            };          
        
ReactDOM.render(
                <ej.digitalgauge id="digitalgauge1" width={1350} height={400} items = {items} frame = {frame} >
                </ej.digitalgauge >,
                    
                 document.getElementById('DigitalGauge1')
             );


{% endhighlight %}

Execute the above code example to render the **Digital****Gauge** as follows.

![](/js/DigitalGauge/Multiple-Items_images/Multiple-Items_img1.png)

