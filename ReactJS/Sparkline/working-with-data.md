---
layout: post
title: Data binding
description: Learn how to bind Sparkline with local data.
platform: ts
control: Sparkline
documentation: ug
---

# Working with Data

## Local Data

1. You can bind the data to the Sparkline by using [`dataSource`](../api/ejsparkline#members:datasource) property and then you need to map the **X** and **Y** value with **xName** and **yName** properties respectively.

{% highlight javascript %}

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
    <EJ.Sparkline id="sparkline1"  dataSource = {sparklinedata} xName = "employeeId" 
    yName = "sales"></EJ.Sparkline>,

    document.getElementById('sparkline')
);


{% endhighlight %}


![](/js/Sparkline/Working-with-Data_images/Working-with-Data_img1.png); 

2. You can also bind an array of data to Sparkline by using [`dataSource`](../api/ejsparkline#members:datasource) property.  

{% highlight javascript %}

"use strict";

ReactDOM.render(
    <EJ.Sparkline id="sparkline1"  dataSource = [ 2, 6, -1, 1, 12, 5, -2, 7, -3, 5, 8, 10]
     ></EJ.Sparkline>,

          document.getElementById('sparkline')
);



{% endhighlight %}

![](/js/Sparkline/Working-with-Data_images/Working-with-Data_img2.png); 

