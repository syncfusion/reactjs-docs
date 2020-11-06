---
layout: post
title: Tooltip
description: Learn how to add Tooltip to Sparkline .
platform: ts
control: Sparkline
documentation: ug
---

## Tooltip  

A tooltip follows the pointer movement and is used to indicate the value of a point. This feature is applicable for line, column, pie, and area Sparkline. You can customize the tooltip [`fill color`](../api/ejsparkline#members:tooltip-fill), [`border`](../api/ejsparkline#members:tooltip-border) and [`font`](../api/ejsparkline#members:tooltip-font).

{% highlight html %}

"use strict";

var tooltip = {
                visible: true,
};

ReactDOM.render(
    <EJ.Sparkline id="sparkline1"  tooltip = {tooltip}></EJ.Sparkline>,

          document.getElementById('sparkline')
);


{% endhighlight %}

![](/js/Sparkline/Tooltip_images/Tooltip_img1.png)

## Tooltip Template   

HTML elements can be displayed in the tooltip by using the [`template`](../api/ejsparkline#members:tooltip-template) option of the tooltip. The template option takes the value of the id attribute of the HTML element. You can use the **#point.x#** and **#point.y#** as place holders in the HTML element to display the x and y values of the corresponding point.

{% highlight js %}

<div id="item" style="display: none;">
    <div>
        <div>#point.x#</div>
        <div>#point.y#</div>
    </div>
</div>

"use strict";

var tooltip = {
                visible: true,template: 'item',
};

ReactDOM.render(
    <EJ.Sparkline id="sparkline1"  tooltip = {tooltip}></EJ.Sparkline>,

          document.getElementById('sparkline')
);


{% endhighlight %}

![](/js/Sparkline/Tooltip_images/Tooltip_img2.png)