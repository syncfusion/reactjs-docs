---
layout: post
title: Public Methods and Events
description: Public Methods and Events in the Sunburst Chart
platform: react js
control: SunburstChart
documentation: ug
---

## Methods


### redraw()

Redraws the entire sunburst. You can call this method whenever you update, add or remove points from the data source or whenever you want to refresh the UI.



{% highlight html %}

<div id="sun"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.SunburstChart id="default"></EJ.SunburstChart>,
	document.getElementById('sun')
);

function SunburstChartMethod(){
    var sunObj = $("#default").data("ejSunburstChart");
    sunObj.redraw();
};

{% endhighlight %}




### _destroy ()


destroy the sunburst


{% highlight html %}

<div id="sun"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.SunburstChart id="default"></EJ.SunburstChart>,
	document.getElementById('sun')
);

function SunburstChartMethod(){
    var sunObj = $("#default").data("ejSunburstChart");
    sunObj.destroy();
};

{% endhighlight %}




## Events

### load

Fires before loading.



{% highlight html %}

<div id="sun"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.SunburstChart id="default" load = {Load}></EJ.SunburstChart>,
	document.getElementById('sun')
);

function Load(){
    // Do Something
};

{% endhighlight %}





### preRender


Fires before rendering sunburst. 


{% highlight html %}

<div id="sun"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.SunburstChart id="default" preRender = {PreRender}></EJ.SunburstChart>,
	document.getElementById('sun')
);

function PreRender(){
    // Do Something
};

{% endhighlight %}



### loaded

Fires after rendering sunburst. 


{% highlight html %}

<div id="sun"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.SunburstChart id="default" loaded = {Loaded}></EJ.SunburstChart>,
	document.getElementById('sun')
);

function Loaded(){
    // Do Something
};

{% endhighlight %}



### dataLabelRendering

Fires before rendering the data label 


{% highlight html %}

<div id="sun"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.SunburstChart id="default" dataLabelRendering = {DataLabelRendering}></EJ.SunburstChart>,
	document.getElementById('sun')
);

function DataLabelRendering(){
    // Do Something
};

{% endhighlight %}



### segmentRendering


Fires before rendering each segment


{% highlight html %}

<div id="sun"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.SunburstChart id="default" segmentRendering = {SegmentRendering}></EJ.SunburstChart>,
	document.getElementById('sun')
);

function SegmentRendering(){
    // Do Something
};

{% endhighlight %}



### titleRendering


Fires before rendering sunburst title. 


{% highlight html %}

<div id="sun"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.SunburstChart id="default" titleRendering = {TitleRendering}></EJ.SunburstChart>,
	document.getElementById('sun')
);

function TitleRendering(){
    // Do Something
};

{% endhighlight %}



### tooltipInitialize


Fires during initialization of tooltip. 


{% highlight html %}

<div id="sun"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.SunburstChart id="default" tooltipInitialize = {TooltipInitialize}></EJ.SunburstChart>,
	document.getElementById('sun')
);

function TooltipInitialize(){
   // Do Something
};

{% endhighlight %}



### pointRegionClick


Fires after clicking the point in sunburst



{% highlight html %}

<div id="sun"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.SunburstChart id="default" pointRegionClick = {PointRegionClick}></EJ.SunburstChart>,
	document.getElementById('sun')
);

function PointRegionClick(){
    // Do Something
};

{% endhighlight %}



### pointRegionMouseMove

Fires while moving the mouse over sunburst points


{% highlight html %}

<div id="sun"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.SunburstChart id="default" pointRegionMouseMove = {PointRegionMouseMove}></EJ.SunburstChart>,
	document.getElementById('sun')
);

function PointRegionMouseMove(){
   // Do Something
};

{% endhighlight %}



### drillDownClick

Fires when clicking the point to perform drilldown. 


{% highlight html %}

<div id="sun"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.SunburstChart id="default" drillDownClick = {DrillDownClick}></EJ.SunburstChart>,
	document.getElementById('sun')
);

function DrillDownClick(){
    // Do Something
};

{% endhighlight %}



### drillDownBack


Fires when resetting drilldown points. 


{% highlight html %}

<div id="sun"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.SunburstChart id="default" drillDownBack = {DrillDownBack}></EJ.SunburstChart>,
	document.getElementById('sun')
);

function DrillDownBack(){
    // Do Something
};

{% endhighlight %}



### drillDownReset


Fires after resetting the sunburst points 


{% highlight html %}

<div id="sun"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.SunburstChart id="default" drillDownReset = {DrillDownReset}></EJ.SunburstChart>,
	document.getElementById('sun')
);

function DrillDownReset(){
    // Do Something
};

{% endhighlight %}



