---
layout: post
title: Change-series-type
description: change series type
platform: js
control: RangeNavigator
documentation: ug
---

### Change the default type of the series

The **type** property in **series** is used to change the type of the series rendered within **RangeNavigator**. By default line series will be rendered to represent the data in **RangeNavigator**.



{% highlight javascript %}


$("#rangecontainer").ejRangeNavigator({
               {   
                   // ...              
                   series: [{
                        type: 'column',
                        // ...              
                      },
                  // ...             
               });


{% endhighlight %}



![](/js/RangeNavigator/How-to/Change-series-type_images/Change-series-type_img1.png) 


When using multiple series in **RangeNavigator**, **type** property in **seriesSettings** is used to set a type common for all the series.



{% highlight javascript %}


$("#rangecontainer").ejRangeNavigator({
               {   
                   // Using a common series type for all the series              
                   seriesSettings: {
                        type: 'stackingcolumn',
                        // ...              
                      },
                  // ...             
               });


{% endhighlight %}

![](/js/RangeNavigator/How-to/Change-series-type_images/Change-series-type_img2.png) 


