---
layout: post
title: Interaction-and-Animation
description: interaction and animation
platform: js
control: Circular Gauge
documentation: ug
api: /api/js/ejcirculargauge
---

# Interaction and Animation

**Interaction**

**Circular Gauge** control contains **Interaction** feature. You can use this interaction feature to change the pointer values manually. You can achieve this by clicking and dragging the pointer over the **Gauge** and you can see the value of pointer changes dynamically while dragging. To Enable/Disable the user interaction you can use the Boolean property called **readOnly**. The user interaction option is enabled when you set the value as false for the property **readOnly**.By default it holds the true value.That is by default it does not support interaction. 

{% highlight javascript %}

"use strict";

ReactDOM.render(
    <EJ.CircularGauge id="default" readonly="false"
    >       
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);

{% endhighlight %}



Execute the above code to render the following output.

![](/js/CircularGauge/Interaction-and-Animation_images/Interaction-and-Animation_img1.png)

**Animations**

**Circular Gauge** contains an attractive concept called **Animation**. The animation option enables the pointer to rotate from the minimum value to the current value with animation effects. By using this animation you can change the pointer value dynamically.You can apply the animation on  pointer either by clockwise or counterclockwise based on the scale direction. You can enable / disable it using the property **enableAnimation.** Animation is enabled when you set **enableAnimation** as ‘true’. By default it holds the true value. You can control the speed of the pointer during animating by using the property **animationSpeed**. It is a numerical value that holds the time in milliseconds. That is when the value is given as 1000, it is considered as 1 second.

{% highlight javascript %}

"use strict";
ReactDOM.render(
    <EJ.CircularGauge id="default" 
    //For enabling animation 
    enableAnimation={true}
    //For setting animation speed
    animationSpeed={1000}
    >       
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}


Execute the above code to render the following output.

![](/js/CircularGauge/Interaction-and-Animation_images/Interaction-and-Animation_img2.png)

## Gradient

You can change the interior gradient of **Circular Gauge** by using `InteriorGradient` property. The `isRadialGradient` property is used to check whether the gradient is circular or not.  

{% highlight javascript %}

"use strict";
ReactDOM.render(
    <EJ.CircularGauge id="default" 
    isRadialGradient={true}    
    >       
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}


## Distance From Corner

You can display the circular gauge from distance apart from the corner by specifying value for `distanceFromCorner` property. 

{% highlight javascript %}

"use strict";
ReactDOM.render(
    <EJ.CircularGauge id="default" 
    distanceFromCorner={5}    
    >       
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}

## Resize

Circular gauge can be responsive while resizing by specifying `enableResize` property as true. 

{% highlight javascript %}

"use strict";
ReactDOM.render(
    <EJ.CircularGauge id="default" 
    enableResize={true}    
    >       
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}

## Localization

The circular gauge can be localized based on name of culture specified in `Locale` property.

{% highlight javascript %}

"use strict";
ReactDOM.render(
    <EJ.CircularGauge id="default" 
    locale="en-fr"    
    >       
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}

## Themes

**CircularGauge** `Theme` is a set of pre-defined options that are applied to the control before **CircularGauge** is instantiated. Following predefined themes are available in JavaScript **CircularGauge**.

1. flat light
2. flat dark
3. gradient light 
4. gradient dark 
5. azure                      
6. azure dark               
7. lime 
8. lime dark
9. saffron
10. saffron dark
11. gradient azure
12. gradient azure dark
13. gradient lime
14. gradient lime dark
15. gradient saffron
16. gradient saffron dark

The theme for circular gauge can be specified using `Theme` property.

{% highlight javascript %}

"use strict";
ReactDOM.render(
    <EJ.CircularGauge id="default" 
    theme="saffron"    
    >       
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}

## Circular Gauge Values 

The `minimum`, `maximum`, `radius` and `value` attributes of circular gauge are used to render the circular gauge with specified location. 

{% highlight javascript %}

"use strict";
ReactDOM.render(
    <EJ.CircularGauge id="default" 
    minimum={10}   
    maximum={100}
    radius={50}
    value={20}
    >       
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}



