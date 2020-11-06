---
layout: post
title: Axis Customize
description: Learn how to customize axis in Sparkline.
platform: ts
control: Sparkline
documentation: ug
---

## Axis Customize 

The Sparkline axis can be collapsed using visible property in [`axisLineSetting`](../api/ejsparkline#members:axisLineSettings) and this not applicable for win-loss. You can customize [`color`](../api/ejsparkline#members:axisLineSettings-color), [`width`](../api/ejsparkline#members:axisLineSettings-width) and [`dash array`](../api/ejsparkline#members:axisLineSettings-dashArray) of axis line.

 {% highlight html %}

"use strict";

var axisLineSettings = {
                visible: true,
                color:"#ff14ae",
            };

ReactDOM.render(
    <EJ.Sparkline id="sparkline1"  axisLineSettings = {axisLineSettings}
            fill = "#33ccff"></EJ.Sparkline>,

          document.getElementById('sparkline')
);



{% endhighlight %}

![](/js/Sparkline/Axis-Customize_images/Axis-Customize_img1.png)