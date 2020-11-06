---
layout: post
title: Sunburst elements 
description: Learn how to customize the sunburst segments 
platform: ts
control: SunburstChart
documentation: ug
---
 
# Sunburst Elements

The Sunburst region represents the entire chart and all its elements. It includes all the chart elements like Legend, DataLabel, Levels etc. The major properties of the Sunburst Chart are as follows

* [`datasource`](../api/ejsunburstchart#members:datasource) – Provides the data that are used to generate the chart.
* [`valueMemberPath`](../api/ejsunburstchart#members:valueMemberPath)- Property based on the which the data segments are rendered in the  Sunburst chart 
* [`legend`](../api/ejsunburstchart#members:legend) – displays the legend of the Sunburst Chart
* [`levels`](../api/ejsunburstchart#members:levels)- displays the hierarchical levels for the chart 
* [`datalabel`](../api/ejsunburstchart#members:datalabelSettings) – displays the datalabel for the Sunburst Chart

## Start and End Angle
Start and End Angle

You can change the start and end angle of Sunburst chart using [`startAngle`](../api/ejsunburstchart#members:startAngle) and [`endAngle`](../api/ejsunburstchart#members:endAngle) property as shown in below code

{% highlight js %}

"use strict";

//Set startAngle and endAngle to draw the sunburst chart

ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1" 
    startAngle = {-90} 
    endAngle = {90}
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);

{% endhighlight %}

## Sunburst Radius

 The Radius of the Sunburst chart can be customized by using the [`radius`](../api/ejsunburstchart#members:radius) property. The default value of radius is 1 and its value ranges between 0 and 1 

{% highlight js %}

"use strict";

//Set radius to the sunburst chart

ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1" 
    radius = {0.8}>                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);


{% endhighlight %}

![](/js/SunburstChart/Regions_images/Regions_img1.png);

 ## Sunburst Inner Radius
 
 The Inner Radius of the Sunburst chart can be customized by using the [`innerRadius`](../api/ejsunburstchart#members:innerradius) property. The default value of innerRadius is 0.4 and its value ranges between 0 and 1 

{% highlight js %}

"use strict";

//Set inner radius to the sunburst chart

ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1" 
    innerRadius = {0.5}
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')

);


{% endhighlight %}

![](/js/SunburstChart/Regions_images/Regions_img2.png);




