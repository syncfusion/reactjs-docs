---
layout: post
title: Sparkline types
description: What are the different types of Sparkline available in Essential JavaScript Chart.
platform: ts
control: Sparkline
documentation: ug
---

# Sparkline Types

## Line Type

To render a Line type Sparkline, set the [`type`](../api/ejsparkline.html#members:type) as **line**. To change the color and width of the line, you can use the [`fill`](../api/ejsparkline.html#members:fill) and [`width`](../api/ejsparkline.html#members:width) property.	

{% highlight html %}

"use strict";

var sparklinedata = [
{ employeeId: 1, sales: 25 },
{ employeeId: 2, sales: 28 },
{ employeeId: 3, sales: 34 },
{ employeeId: 4, sales: 32 },
{ employeeId: 5, sales: 40 },
{ employeeId: 6, sales: 32 },
{ employeeId: 7, sales: 35 },
{ employeeId: 8, sales: 55 },
{ employeeId: 9, sales: 38 },
{ employeeId: 10, sales: 30 }];

ReactDOM.render(
        <EJ.Sparkline id="sparkline1"  dataSource = {sparklinedata}  type = 'line' fill = "#33ccff"
        xName = "employeeId" yName = "sales" ></EJ.Sparkline>,
        document.getElementById('sparkline')
);

{% endhighlight %}

![](/js/Sparkline/Sparkline-Types_images/Sparkline-Types_img1.png)

## Column Type

To render a Column Sparkline, set the type as **column** To change the color of the column, you can use the [`fill`](../api/ejsparkline.html#members:fill) property.

{% highlight html %}

"use strict";

ReactDOM.render(
        <EJ.Sparkline id="sparkline1"  dataSource = {sparklinedata}  type = 'column' fill = "#33ccff"
        xName = "employeeId" yName = "sales" ></EJ.Sparkline>,
        document.getElementById('sparkline')
);

{% endhighlight %}

![](/js/Sparkline/Sparkline-Types_images/Sparkline-Types_img2.png)

## Area Type

To render an Area Sparkline, you can specify the type as **area**. To change the Area color, you can use the [`fill`](../api/ejsparkline.html#members:fill) property

{% highlight html %}

"use strict";

ReactDOM.render(
            <EJ.Sparkline id="sparkline1"  dataSource = {sparklinedata}  type = 'area'
            fill = "#33ccff" xName = "employeeId" yName = "sales" ></EJ.Sparkline>,
            document.getElementById('sparkline')
);


{% endhighlight %}

![](/js/Sparkline/Sparkline-Types_images/Sparkline-Types_img3.png)

## WinLoss Type

WinLoss Sparkline render as a column segment and it show the positive, negative and neutral values. You can customize the positive and negative color of the win-loss type.

{% highlight html %}

"use strict";

ReactDOM.render(
            <EJ.Sparkline id="sparkline1"  dataSource = {sparklinedata}  type = 'winloss'
            fill = "#33ccff" xName = "employeeId" yName = "sales" ></EJ.Sparkline>,
            document.getElementById('sparkline')
);


{% endhighlight %}

![](/js/Sparkline/Sparkline-Types_images/Sparkline-Types_img4.png)

## Pie Type

You can create a pie type sparkline by setting the type as **pie**. Colors for the pie can be customize using [`palette`](../api/ejsparkline.html#members:palette) property.

{% highlight html %}

"use strict";

ReactDOM.render(
    <EJ.Sparkline id="sparkline1"  dataSource = {sparklinedata}  type = 'pie' fill = "#33ccff"
     xName = "employeeId" yName = "sales" ></EJ.Sparkline>,
    document.getElementById('sparkline')
);


{% endhighlight %}

![](/js/Sparkline/Sparkline-Types_images/Sparkline-Types_img5.png)
