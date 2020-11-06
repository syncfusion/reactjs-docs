---
layout: post
title: Markers Customization
description: Learn how to add markers to Sparkline.
platform: ts
control: Sparkline
documentation: ug
---

## Marker Customization

You can customize markers by initializing the [`markerSettings`](../api/ejsparkline#members:markersettings) property. The customization options allow you to change the [`fill`](../api/ejsparkline#members:markersettings-fill), [`width`](../api/ejsparkline#members:markersettings-width), [`opacity`](../api/ejsparkline#members:markersettings-opacity)and [`border`](../api/ejsparkline#members:markersettings-border) for marker. This customization only applicable for line, column and area type Sparkline.

{% highlight html %}

"use strict";

var axisLineSettings = {
                visible: true,
                color:"#ff14ae",
            };
            
             var markerSettings = {
                visible: true,
                width: 4,
                fill: "#ff14ae",
                border: {
                    width: 1
                }
            };

ReactDOM.render(
    <EJ.Sparkline id="sparkline1"  markerSettings = {markerSettings}></EJ.Sparkline>,

          document.getElementById('sparkline')
);


{% endhighlight %}

![](/js/Sparkline/Marker-Customization_images/Marker-Customization_img1.png)
