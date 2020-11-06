---
layout: post
title: Rendering modes available in Essential JavaScript Chart
description: How Essential Chart renders in IE7 and IE8. How to render Essential Chart in a HTML5 Canvas.                    
platform: js
control: Chart
documentation: ug
api : /api/js/ejchart
---

# Rendering Modes

Chart uses following three rendering technologies

   * VML
   * SVG
   * HTML5 Canvas

## VML

VML is used to render chart in IE lower versions such as IE7 and IE8. VML is used by default in these two browsers, as SVG and Canvas are not supported in these browsers.

**Limitations:**

* Label rotation is not supported.
* Animation is not supported.
* Patterns are not supported.
* Zooming and panning features are not supported.

## SVG

SVG is used to render Chart by default for all browsers other than IE7 and IE8.

## Canvas

You can switch between SVG and Canvas rendering by using the [`enableCanvasRendering`](../api/ejchart#members:enablecanvasrendering) option. The canvas mode rendering is used in the following scenarios,

* Plotting large number of data points.
* Performing high frequency live updates.
 
The following code example shows how to enable HTML5 Canvas rendering in chart.


{% highlight javascript %}

"use strict";
        //Rendering chart in canvas mode
        var canvas= true;
        
        // ...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			enableCanvasRendering={canvas}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Rendering-Modes_images/Rendering-Modes_img1.png)


**Limitations:**
  
* Animation is not supported.
* 3D charts are not supported.


