---
layout: post
title: User-Interaction
description: user interaction
platform: js
control: BulletGraph	
documentation: ug
api: /api/js/ejbulletgraph
---

# User Interaction

## Animation

**Bullet Graph** supports animation that makes the performance measure bar to animate when rendering the **Bullet Graph**. **Animation** is enabled or disabled using **enableAnimation** property. By default, **Animation** is enabled in **Bullet Graph**.

{% highlight javascript %}

"use strict";

 ReactDOM.render(
            <ej.bulletgraph id="bulletGraph1"
                            value = {8}					
                            comparativeMeasureValue = {5}
                            enableAnimation = {true}>
            </ej.bulletgraph>,
            document.getElementById('bulletGraph')
            );



{% endhighlight %}

## Responsiveness during browser resize

**Bullet Graph** is made responsive when resizing the browser by using **isResponsive** property. By default the value of this property is **true** in **Bullet Graph**.

{% highlight javascript %}

"use strict";

ReactDOM.render(
            <ej.bulletgraph id="bulletGraph1" isResponsive = {true} value ={8}
                comparativeMeasureValue ={5} >
            </ej.bulletgraph>,
            document.getElementById('bulletGraph')
            );



{% endhighlight %}


Responsiveness of the linear gauge is controlled by using enableResize property.


{% highlight javascript %}

"use strict";

ReactDOM.render(
            <ej.bulletgraph id="bulletGraph1" enableResize = {true}>
            </ej.bulletgraph>,
            document.getElementById('bulletGraph')
);

{% endhighlight %}




## Applying same color to all ticks and labels in a range

Background color for qualitative range is applied to major ticks and minor ticks of the **Bullet Graph** using **applyRangeStrokeToTicks** property. The range colors are applied to labels using **applyRangeStrokeToLabels** property. By default same colors are not applied to a qualitative range and its corresponding ticks or labels.

{% highlight javascript %}

"use strict";

var qualitativeRanges = [
                       { rangeEnd: 3.5, rangeStroke: 'yellow', rangeOpacity: 0.5 },
                       { rangeEnd: 5.0, rangeStroke: 'red', rangeOpacity: 1 },
                       { rangeEnd: 7.5, rangeStroke: 'blue', rangeOpacity: 0.7 },
                       { rangeEnd: 9.0, rangeStroke: 'pink', rangeOpacity: 1 },
                       { rangeEnd: 10.0, rangeStroke: 'green', rangeOpacity: 1 }
    ];
ReactDOM.render(
            <ej.bulletgraph id="bulletGraph1"		                                
                 qualitativeRanges={qualitativeRanges}
                 value ={8}	applyRangeStrokeToTicks ={true}	applyRangeStrokeToLabels ={true}
                 comparativeMeasureValue ={5} >
            </ej.bulletgraph>,
            document.getElementById('bulletGraph')
            );



{% endhighlight %}

![](/js/BulletGraph/User-Interaction_images/User-Interaction_img1.png) 

## Tooltip

By default **Bullet Graph** displays **Tooltip** when mouse is hovered over feature measure bar. **Tooltip** is enabled or disabled using visible property in **tooltipSettings**.

![](/js/BulletGraph/User-Interaction_images/User-Interaction_img2.png) 

Bullet Graph supports Tooltip template instead of default Tooltip to customize the appearance and contents of Tooltip. The Tooltip template should be a &lt;div&gt; element with display set to ‘none’, so it is displayed only when mouse is placed on feature measure bar. The id value of the &lt;div&gt; element should be provided as value to the template property in tooltipSettings of Bullet Graph to display the customized &lt;div&gt; element as Tooltip instead of default Tooltip. The values displayed in default Tooltip such as current value, target value and category are accessed in template &lt;div&gt; element by using {{currentValue}}, {{targetValue}} and {{category}} respectively.

{% highlight html %}

<div id="BulletGraphTooltip" style="display:none; width:125px; padding-top: 10px; padding-bottom:10px; color: blue"> 
    <div align="center" style="color:blue; font-weight:bold"> Sales </div> 
    <table style="color:green"> <tr> <td> Current </td> <td> : </td> </tr> <tr> <td> Target </td> <td> : </td> </tr> </table> 
</div>

{% endhighlight %}

{% highlight javascript %}

"use strict";

var tooltipSettings = { template: 'BulletGraphTooltip' };

ReactDOM.render(
            <ej.bulletgraph id="bulletGraph1" tooltipSettings = {tooltipSettings}	                value ={8}	comparativeMeasureValue ={6} height = {150} >
            </ej.bulletgraph>,
            document.getElementById('bulletGraph')
);  

{% endhighlight %}

The following screenshot displays **Bullet Graph** with a customized **Tooltip** including a header and contents such as current value and target value in different colors.

![](/js/BulletGraph/User-Interaction_images/User-Interaction_img3.png) 

