---
layout: post
title: Sparkline size
description: Learn how to set Sparkline size and make it responsive. 
platform: ts
control: Sparkline
documentation: ug
---

##Sparkline Dimensions

You can set the size directly on the Sparkline or to the container of the sparkline. When you do not specify the size, it takes 30px as the height and 50px as its width, by default.

## Set size for the container

You can customize the Sparkline dimension by setting the width and height for the container element.

{% highlight html %}

<body>
    <div id="container" style="width:820px;height:500px;"></div>
    <script type="text/javascript" language="javascript ">       
    </script>
</body>

{% endhighlight %} 

![](/js/Sparkline/Sparkline-Dimensions_images/Sparkline-Dimensions_img1.png)

## Set size in pixels 

You can also set the Sparkline dimension by using the [`size`](../api/ejsparkline#members:size) property of the Sparkline.

{% highlight html %}

"use strict";

var size = { width: '60', height: '40' };

ReactDOM.render(
    <EJ.Sparkline id="sparkline1"  size = {size} ></EJ.Sparkline>,

          document.getElementById('sparkline')
);



{% endhighlight %}

## Responsive Sparkline

To resize the Sparkline when the browser or the sparkline container is resized, set the [`isResponsive`](../api/ejsparkline#members:isresponsive) property to **true**, where the sparkline adapts to the changes in size of the container. 

{% highlight javascript %}

"use strict";

ReactDOM.render(
    <EJ.Sparkline id="sparkline1"  isResponsive = {true}></EJ.Sparkline>,

          document.getElementById('sparkline')
);


{% endhighlight %} 
