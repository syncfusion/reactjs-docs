---
layout: post
title: Digital-Elements
description: digital elements
platform: js
control: Digital Gauge
documentation: ug
---

# Digital Elements

**Text Customization**

* The attribute **value** refers the text displayed in the **Digital Gauge**. This text is applicable only for that item instead of all items. Text color is changed by using the property **textColor.**

* It is possible to align the text inside the **Digital Gauge** control by using the property **textAlign**. Two possible values for text align are as follows

  * left

  * right

{% highlight html %}

<div id="DigitalGauge1"></div>

{% endhighlight %}

{% highlight html %}

"use strict";

 var items = [{
                // For setting alingment
                textAlign: "right",
                // For setting text
                value: "STOP",
}];       
        
ReactDOM.render(
                  <ej.digitalgauge id="digitalgauge1" items = {items} ></ej.digitalgauge >,
                 document.getElementById('DigitalGauge1')
             );
                      


{% endhighlight %}

Execute the above code examples to render the **Digital****Gauge** as follows.

![](/js/DigitalGauge/Digital-Elements_images/Digital-Elements_img1.png)

