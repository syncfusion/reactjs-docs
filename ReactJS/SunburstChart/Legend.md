---
layout: post
title: legend
description: Learn how to add and customize the legnds in Sunburst Chart.
platform: ts
control: SunburstChart
documentation: ug
---

## Legend
The legend is used to represent the first level of items in the Sunburst Chart.The [`legend`](../api/ejsunburstchart#members:legend) can be initialized using the below code snippet

{% highlight js %}

"use strict";
 var legend = { visible: true };
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    legend ={legend}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);

 {% endhighlight %}

![](/js/SunburstChart/Legend_images/Legend_img1.png)

## Legend Icon 

You can specify different shapes of legend icon by using the [`shape`](../api/ejsunburstchart#members:legend-shape) property of the legend. By default, legend shape is **Circle**. The Sunburst chart has some predefined shapes such as:
* Circle
* Cross
* Diamond
* Pentagon
* Rectangle
* Triangle

{% highlight js %}

"use strict";
 var legend = { shape:"pentagon"};
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    legend ={legend}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);

{% endhighlight %}

![](/js/SunburstChart/Legend_images/Legend_img2.png)
 
## Positioning the Legend

By using the [`position`](../api/ejsunburstchart#members:legend-position) property, you can position the legend at left, right, top or bottom of the chart. 

{% highlight js %}

"use strict";
 var legend = { position:"top"};
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    legend ={legend}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);


{% endhighlight %}

![](/js/SunburstChart/Legend_images/Legend_img3.png)
 
### Customization

## Legend Item Size and border
You can change the size of the legend items by using the [`itemStyle.width`](../api/ejsunburstchart#members:legend-itemstyle-width) and [`itemStyle.height`](../api/ejsunburstchart#members:legend-itemstyle-height) properties. To change the legend item border, use [`border`](../api/ejsunburstchart#members:legend-border) property of the legend .

{% highlight js %}

"use strict";
 var legend = {position:"top",itemStyle:{height:13,width:13},border: { color: "#FF0000", width: 1 }};
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    legend ={legend}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);


{% endhighlight %}

![](/js/SunburstChart/Legend_images/Legend_img4.png)

## Legend Alignment

You can align the legend to the `center`, `far` or `near` based on its position by using the `legend-alignment` option.

{% highlight js %}

"use strict";
 var legend = {alignment:"near"};
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    legend ={legend}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);

{% endhighlight %}


## Legend Size

By default, legend takes 20% of the height horizontally when it was placed on the top or bottom position and 20% of the width vertically while placing on the left or right position of the chart. You can change this default legend size by using the [`size`](../api/ejsunburstchart#members:legend-size) property of the legend.

{% highlight js %}

"use strict";
 var legend = {position:"top",size:{ height:"75",width:"200"}};
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    legend ={legend}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);


{% endhighlight %}

 ![](/js/SunburstChart/Legend_images/Legend_img5.png)

## Legend title

To add the title to the legend, you have to specify the `legend.title`  option.

{% highlight js %}

"use strict";
 var legend = {title:{
       //..
 }};
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    legend ={legend}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);

{% endhighlight %}

## Customize the legend text

To customize the legend item text and title you can use the `legend-title-font` and `legend-title` options. You can change the legend title alignment by using the `legend-title-textAlignment` option of the legend title.

{% highlight js %}

"use strict";
 var legend = {title:{
       //..
       font:{
             //..
       }
 }};
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    legend ={legend}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);

{% endhighlight %}



## Legend Row and Column

You can arrange the legend items horizontally and vertically by using the [`rowCount`](../api/ejsunburstchart#members:legend-rowCount) and [`columnCount`](../api/ejsunburstchart#members:legend-clumnCount) properties of the legend.
•	When only the rowCount is specified, the legend items are arranged according to the rowCount and number of columns may vary based on the number of legend items.
•	When only the columnCount is specified, the legend items are arranged according to the columnCount and number of rows may vary based on the number of legend items.
•	When both the properties are specified, then the one which has higher value is given preference. For example, when the rowCount is 4 and columnCount is 3, legend items are arranged in 4 rows.
•	When both the properties are specified and have the same value, the preference is given to the columnCount when it is positioned at the top/bottom position. The preference is given to the rowCount when it is positioned at the left/right position.
 
{% highlight js %}

"use strict";
 var legend = {position:"top",rowCount:"2",columnCount:"3"};
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    legend ={legend}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);

{% endhighlight %}

![](/js/SunburstChart/Legend_images/Legend_img6.png)
 
## LegendInteractivity

You can select a specific category while clicking on corresponding legend item through [`clickAction'](../api/ejsunburstchart#members:legend-clickAction) property. 

It has three types of action
*	ToggleSegmentSelection
*	ToggleSegmentVisibility
*	None

## ToggleSegmentSelection

Used to highlight specific category while clicking on legend item

{% highlight js %}

"use strict";
 var legend = {clickAction:"toggleSegmentSelection"};
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    legend ={legend}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);

{% endhighlight %}

![](/js/SunburstChart/Legend_images/Legend_img7.png)
 
## Toggle Segment Visibility

Used to disable the specific category while clicking on legend item.

{% highlight js %}

"use strict";
 var legend = {clickAction:"toggleSegmentVisibility"};
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    legend ={legend}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);



{% endhighlight %}


![](/js/SunburstChart/Legend_images/Legend_img8.png)


