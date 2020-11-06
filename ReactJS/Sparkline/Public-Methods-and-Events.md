---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: react js
control: Sparkline
documentation: ug
---

## Methods


### redraw()


Redraws the entire sparkline. You can call this method whenever you update, add or remove points from the data source or whenever you want to refresh the UI.



{% highlight html %}

<div id="line"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Sparkline id="default"></EJ.Sparkline>,
	document.getElementById('line')
);

function SparkLineMethod(){
    var sparkObj = $("#default").data("ejSparkLine");
    sparkObj.redraw();
};

{% endhighlight %}








## Events



### load


Fires before loading the sparkline.



{% highlight html %}

<div id="line"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Sparkline id="default" load = {Load}></EJ.Sparkline>,
	document.getElementById('line')
);

function Load(){
    // Do Something
};

{% endhighlight %}




### loaded


Fires after loaded the sparkline.



{% highlight html %}

<div id="line"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Sparkline id="default" loaded = {Loaded}></EJ.Sparkline>,
	document.getElementById('line')
);

function Loaded(){
    // Do Something
};

{% endhighlight %}




### tooltipInitialize


Fires before rendering trackball tooltip. You can use this event to customize the text displayed in trackball tooltip.



{% highlight html %}

<div id="line"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Sparkline id="default" tooltipInitialize ={TooltipInitialize}></EJ.Sparkline>,
	document.getElementById('line')
);

function TooltipInitialize(){
    // Do Something
};

{% endhighlight %}





### seriesRendering





Fires before rendering a series. This event is fired for each series in Sparkline.



{% highlight html %}

<div id="line"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Sparkline id="default" seriesRendering = {SeriesRendering}></EJ.Sparkline>,
	document.getElementById('line')
);

function SeriesRendering(){
   // Do Something
};

{% endhighlight %}







### pointRegionMouseMove


Fires when mouse is moved over a point. 



{% highlight html %}

<div id="line"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Sparkline id="default" pointRegionMouseMove = {PointRegionMouseMove}></EJ.Sparkline>,
	document.getElementById('line')
);

function PointRegionMouseMove(){
    // Do Something
};

{% endhighlight %}




### pointRegionMouseClick


Fires on clicking a point in sparkline. You can use this event to handle clicks made on points.



{% highlight html %}

<div id="line"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Sparkline id="default" pointRegionMouseClick = {PointRegionMouseClick}></EJ.Sparkline>,
	document.getElementById('line')
);

function PointRegionMouseClick(){
   // Do Something
};

{% endhighlight %}






### sparklineMouseMove


Fires on moving mouse over the sparkline.



{% highlight html %}

<div id="line"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Sparkline id="default" sparklineMouseMove = {SparklineMouseMove}></EJ.Sparkline>,
	document.getElementById('line')
);

function SparklineMouseMove(){
    // Do Something
};

{% endhighlight %}





### sparklineMouseLeave


Fires on moving mouse outside the sparkline.



{% highlight html %}

<div id="line"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Sparkline id="default" sparklineMouseLeave = {SparklineMouseLeave}></EJ.Sparkline>,
	document.getElementById('line')
);

function SparklineMouseLeave(){
    // Do Something
};

{% endhighlight %}



