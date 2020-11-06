---
layout: post
title: Frames
description: frames
platform: js
control: Digital Gauge
documentation: ug
---

# Frames

## Inner and Outer Width Customization

**Frames** are space that enclose the **Digital Gauge**. The inner width of the **Frame** is the distance between the canvas element and the frame. The outer width is the distance from the frame. The code example to set frame’s **innerWidth** and **outerWidth** is as follow.

{% highlight javascript %}
"use strict";

var frame = {
                // For setting inner width
                innerWidth: 6,
                // For setting outer width
                outerWidth: 10,
            };      
        
 ReactDOM.render(
              <ej.digitalgauge id="digitalgauge1" value = "WELCOME" frame = {frame}></ej.digitalgauge >,        
                document.getElementById('digitalgauge')
             );
                      

{% endhighlight %}




Execute the above code examples to render the **Digital****Gauge** as follows.

![](/js/DigitalGauge/Frames_images/Frames_img1.png)



## Setting Background Image

For a better appearance, you can set the **background****image** for the **Digital Gauge** using the property **backgroundImageUrl.** 

{% highlight javascript %}

"use strict";
var frame= {
    // For setting backgroung image
    backgroundImageUrl: "board3.jpg"
};
var items= [{
    position: {
        x: 95,
        y: 10
    }
}];
//For Digital Gauge rendering
ReactDOM.render(
    <EJ.DigitalGauge id="digitalgauge"
	//For setting text
    value="RADAR" frame={frame} height={300} items={items}
    >
                    
    </EJ.DigitalGauge>,
		  document.getElementById('digitalgauge')
);

{% endhighlight %}



Execute the above code examples to render the **Digital****Gauge** as follows.

![](/js/DigitalGauge/Frames_images/Frames_img2.png)

