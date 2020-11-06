---
layout: post
title: Tooltip
description: Learn how to add Tooltip to Sunburstchart .
platform: ts
control: Sunburst Chart
documentation: ug
---

## Tooltip  

[`ToolTip`](../api/ejsunburstchart#members:tooltip) allows you to display any information over a sunburst segment. It appears when mouse hovered over or touch any chart segment. By default, it displays the corresponding segment category name and its value

{% highlight js %}

"use strict";
 var tooltip = {visible: true};
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    tooltip ={tooltip}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);



{% endhighlight %}

![](/js/SunburstChart/Tooltip_images/Tooltip_img1.png)

## Tooltip Template   

HTML elements can be displayed in the tooltip by using the [`template`](../api/ejsunburstchart#members:tooltip-template) property of the tooltip. The template property takes the value of the id attribute of the HTML element. You can use the **#point.x#** and **#point.y#** as place holders in the HTML element to display the x and y values of the corresponding point.

{% highlight js %}

<body>
    <div id="Tooltip" style="display: none;">
        <div id="value" style="background-color:red;padding-top:3px;padding-right:3px">
            <div>
                <label id="efpercentage" style="color:white">
                    &nbsp;&nbsp;Category:&nbsp;#point.x#
                   <br />&nbsp;&nbsp;Value:#point.y#
                </label>
            </div>
        </div>
    </div>
</body>

"use strict";
var tooltip = { visible: true,
    template:'Tooltip'};
ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"          
	tooltip = {tooltip}>                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);



{% endhighlight %}

![](/js/SunburstChart/Tooltip_images/Tooltip_img2.png)

## Customize the appearance of tooltip

The `fill` and `border` options are used to customize the `background color` and `border` of the tooltip respectively. The `font` option in the tooltip is used to customize the font of the tooltip text.


{% highlight js %}

"use strict";
 var tooltip = { visible: true,
    border:{
        color:'red',
        width:2
    },
font:{
    //..
}
    };
ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"          
	tooltip = {tooltip}>                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);


{% endhighlight %}

