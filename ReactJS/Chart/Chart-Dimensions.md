---
layout: post
title: Chart size
description: Learn how to set Chart size and make it responsive. 
platform: js
control: Chart
documentation: ug
api : /api/js/ejchart
---

# Chart Dimensions

You can set the size of the chart directly on the chart or to the container of the chart. When you do not specify the size, it takes 450px as the height and window size as its width, by default. 

## Set size for the container

You can customize the chart dimension by setting the width and height for the container element. 

{% highlight javascript %}


    <body>
       <div id=”container” style=”width:820px; height:500px;”></div>         
    </body>

    "use strict";
    <EJ.Chart id="default_chart_sample_0">
    </EJ.Chart>,
{% endhighlight %}


## Set size in pixels

You can also set the chart dimension by using the [`size`](../api/ejchart#members:size) property of the chart. 

{% highlight javascript %}


    "use strict";
    var size = { width: '600', height: '450' };
    ReactDOM.render(
        <EJ.Chart id="chart1"  size = {size}></EJ.Chart>,
            document.getElementById('chart')
    );



{% endhighlight %}

![](/js/Chart/Chart-Dimensions_images/Chart-Dimensions_img1.png)


## Setting size relative to the container size

You can specify the chart size in percentage by using the [`size`](../api/ejchart#members:size) property. The chart gets its dimension with respect to its container.

{% highlight html %}

    <body>
        <div id="container" style="width:700px; height:500px"></div>
    </body>

    "use strict";
    var size = { width: '80%', height: '90%' };
    ReactDOM.render(
        <EJ.Chart id="chart1"  size = {size}></EJ.Chart>,
            document.getElementById('chart')
    );

{% endhighlight %}

![](/js/Chart/Chart-Dimensions_images/Chart-Dimensions_img2.png)


## Responsive chart

To resize the Chart when the browser or the chart container is resized, set the [`isResponsive`](../api/ejchart#members:isResponsive) property to **true**, where the chart adapts to the changes in size of the container.

{% highlight javascript %}

      "use strict";
    
ReactDOM.render(
    <EJ.Chart id="chart1"  isResponsive = 'true' ></EJ.Chart>,
          document.getElementById('chart')
);


{% endhighlight %} 
