---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: react js
control: Circular Gauge
documentation: ug
api: /api/js/ejcirculargauge
---


## Methods




### destroy()


destroy the circular gauge widget. all events bound using this._on will be unbind automatically and bring the control to pre-init state.



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.destroy();
};

{% endhighlight %}




### exportImage()


To export Image


{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.exportImage();
};

{% endhighlight %}





### getBackNeedleLength()


To get BackNeedleLength


{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getBackNeedleLength();
};

{% endhighlight %}




### getCustomLabelAngle()


To get CustomLabelAngle


{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getCustomLabelAngle();
};

{% endhighlight %}



### getCustomLabelValue()

To get CustomLabelValue




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getCustomLabelValue();
};

{% endhighlight %}



### getLabelAngle()

To get LabelAngle




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getLabelAngle();
};

{% endhighlight %}




### getLabelDistanceFromScale()

To get LabelDistanceFromScale




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getLabelDistanceFromScale();
};

{% endhighlight %}



### getLabelPlacement()

To get LabelPlacement




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getLabelPlacement();
};

{% endhighlight %}



### getLabelStyle()


To get LabelStyle




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getLabelStyle();
};

{% endhighlight %}




### getMajorIntervalValue()

To get MajorIntervalValue



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getMajorIntervalValue();
};

{% endhighlight %}




### getMarkerDistanceFromScale()

To get MarkerDistanceFromScale




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getMarkerDistanceFromScale();
};

{% endhighlight %}




### getMarkerStyle()


To get MarkerStyle



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getMarkerStyle();
};

{% endhighlight %}




### getMaximumValue()

To get MaximumValue



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getMaximumValue();
};

{% endhighlight %}




### getMinimumValue()

To get MinimumValue



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getMinimumValue();
};

{% endhighlight %}




### getMinorIntervalValue()

To get MinorIntervalValue



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getMinorIntervalValue();
};

{% endhighlight %}




### getNeedleStyle()


To get NeedleStyle



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getNeedleStyle();
};

{% endhighlight %}




### getPointerCapBorderWidth()


To get PointerCapBorderWidth



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getPointerCapBorderWidth();
};

{% endhighlight %}




### getPointerCapRadius()

To get PointerCapRadius



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getPointerCapRadius();
};

{% endhighlight %}




### getPointerLength()


To get PointerLength




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getPointerLength();
};

{% endhighlight %}




### getPointerNeedleType()


To get PointerNeedleType




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getPointerNeedleType();
};

{% endhighlight %}




### getPointerPlacement()

To get PointerPlacement



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getPointerPlacement();
};

{% endhighlight %}




### getPointerValue()

To get PointerValue




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getPointerValue();
};

{% endhighlight %}




### getPointerWidth()

To get PointerWidth


{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getPointerWidth();
};

{% endhighlight %}




### getRangeBorderWidth()


To get RangeBorderWidth


{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getRangeBorderWidth();
};

{% endhighlight %}




### getRangeDistanceFromScale()

To get RangeDistanceFromScale



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getRangeDistanceFromScale();
};

{% endhighlight %}




### getRangeEndValue()


To get RangeEndValue




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getRangeEndValue();
};

{% endhighlight %}




### getRangePosition()

To get RangePosition



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getRangePosition();
};

{% endhighlight %}




### getRangeSize()


To get RangeSize




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getRangeSize();
};

{% endhighlight %}




### getRangeStartValue()


To get RangeStartValue



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getRangeStartValue();
};

{% endhighlight %}




### getScaleBarSize()

To get ScaleBarSize



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getScaleBarSize();
};

{% endhighlight %}




### getScaleBorderWidth()


To get ScaleBorderWidth



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getScaleBorderWidth();
};

{% endhighlight %}




### getScaleDirection()


To get ScaleDirection




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getScaleDirection();
};

{% endhighlight %}




### getScaleRadius()

To get ScaleRadius




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getScaleRadius();
};

{% endhighlight %}




### getStartAngle()

To get StartAngle



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getStartAngle();
};

{% endhighlight %}




### getSubGaugeLocation()

To get SubGaugeLocation



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getSubGaugeLocation();
};

{% endhighlight %}




### getSweepAngle()

To get SweepAngle



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getSweepAngle();
};

{% endhighlight %}



### getTickAngle()


To get TickAngle


{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getTickAngle();
};

{% endhighlight %}




### getTickDistanceFromScale()


To get TickDistanceFromScale




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getTickDistanceFromScale();
};

{% endhighlight %}




### getTickHeight()


To get TickHeight



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getTickHeight();
};

{% endhighlight %}




### getTickPlacement()

To get TickPlacement




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getTickPlacement();
};

{% endhighlight %}




### getTickStyle()



To get TickStyle



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getTickStyle();
};

{% endhighlight %}




### getTickWidth()



To get TickWidth




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.getTickWidth();
};

{% endhighlight %}




### includeFirstValue()


To set includeFirstValue


{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.includeFirstValue();
};

{% endhighlight %}



### redraw()

Switching the redraw option for the gauge



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.redraw();
};

{% endhighlight %}




### setBackNeedleLength()

To set BackNeedleLength




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setBackNeedleLength();
};

{% endhighlight %}



### setCustomLabelAngle()


To set CustomLabelAngle




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setCustomLabelAngle();
};

{% endhighlight %}




### setCustomLabelValue()


To set CustomLabelValue




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setCustomLabelValue();
};

{% endhighlight %}




### setLabelAngle()


To set LabelAngle



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setLabelAngle();
};

{% endhighlight %}




### setLabelDistanceFromScale()

To set LabelDistanceFromScale




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setLabelDistanceFromScale();
};

{% endhighlight %}




### setLabelPlacement()


To set LabelPlacement


{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setLabelPlacement();
};

{% endhighlight %}




### setLabelStyle()

To set LabelStyle



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setLabelStyle();
};

{% endhighlight %}




### setMajorIntervalValue()


To set MajorIntervalValue




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setMajorIntervalValue();
};

{% endhighlight %}




### setMarkerDistanceFromScale()

To set MarkerDistanceFromScale



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setMarkerDistanceFromScale();
};

{% endhighlight %}




### setMarkerStyle()


To set MarkerStyle



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setMarkerStyle();
};

{% endhighlight %}




### setMaximumValue()


To set MaximumValue



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setMaximumValue();
};

{% endhighlight %}




### setMinimumValue()

To set MinimumValue



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setMinimumValue();
};

{% endhighlight %}




### setMinorIntervalValue()

To set MinorIntervalValue



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setMinorIntervalValue();
};

{% endhighlight %}




### setNeedleStyle()

To set NeedleStyle




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setNeedleStyle();
};

{% endhighlight %}




### setPointerCapBorderWidth()


To set PointerCapBorderWidth



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setPointerCapBorderWidth();
};

{% endhighlight %}




### setPointerCapRadius()


To set PointerCapRadius




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setPointerCapRadius();
};

{% endhighlight %}




### setPointerLength()

To set PointerLength




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setPointerLength();
};

{% endhighlight %}



### setPointerNeedleType()


To set PointerNeedleType




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setPointerNeedleType();
};

{% endhighlight %}




### setPointerPlacement()

To set PointerPlacement



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setPointerPlacement();
};

{% endhighlight %}




### setPointerValue()

To set PointerValue




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setPointerValue();
};

{% endhighlight %}




### setPointerWidth()

To set PointerWidth



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setPointerWidth();
};

{% endhighlight %}




### setRangeBorderWidth()


To set RangeBorderWidth



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setRangeBorderWidth();
};

{% endhighlight %}




### setRangeDistanceFromScale()


To set RangeDistanceFromScale



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setRangeDistanceFromScale();
};

{% endhighlight %}




### setRangeEndValue()


To set RangeEndValue




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setRangeEndValue();
};

{% endhighlight %}




### setRangePosition()


To set RangePosition




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setRangePosition();
};

{% endhighlight %}




### setRangeSize()

To set RangeSize




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setRangeSize();
};

{% endhighlight %}




### setRangeStartValue()

To set RangeStartValue



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setRangeStartValue();
};

{% endhighlight %}




### setScaleBarSize()

To set ScaleBarSize



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setScaleBarSize();
};

{% endhighlight %}




### setScaleBorderWidth()



To set ScaleBorderWidth



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setScaleBorderWidth();
};

{% endhighlight %}




### setScaleDirection()





To set ScaleDirection



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setScaleDirection();
};

{% endhighlight %}




### setScaleRadius()





To set ScaleRadius



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setScaleRadius();
};

{% endhighlight %}




### setStartAngle()





To set StartAngle



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setStartAngle();
};

{% endhighlight %}




### setSubGaugeLocation()





To set SubGaugeLocation



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setSubGaugeLocation();
};

{% endhighlight %}




### setSweepAngle()





To set SweepAngle



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setSweepAngle();
};

{% endhighlight %}




### setTickAngle()


To set TickAngle


{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setTickAngle();
};

{% endhighlight %}




### setTickDistanceFromScale()


To set TickDistanceFromScale




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setTickDistanceFromScale();
};

{% endhighlight %}




### setTickHeight()


To set TickHeight




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setTickHeight();
};

{% endhighlight %}




### setTickPlacement()





To set TickPlacement



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setTickPlacement();
};

{% endhighlight %}




### setTickStyle()


To set TickStyle



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setTickStyle();
};

{% endhighlight %}




### setTickWidth()

To set TickWidth



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default"></EJ.CircularGauge>,
	document.getElementById('circular')
);

function CircularGaugeMethod(){
    var circularObj = $("#default").data("ejCircularGauge");
    circularObj.setTickWidth();
};

{% endhighlight %}



## Events




### drawCustomLabel





Triggers while the custom labels are being drawn on the gauge.



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default" drawCustomLabel = {DrawCustomLabel} ></EJ.CircularGauge>,
	document.getElementById('circular')
);

function DrawCustomLabel(){
    // Do Something
};

{% endhighlight %}






### drawIndicators





Triggers while the indicators are being started to drawn on the gauge.




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default" drawIndicators = {DrawIndicators} ></EJ.CircularGauge>,
	document.getElementById('circular')
);

function DrawIndicators(){
    // Do Something
};

{% endhighlight %}







### drawLabels





Triggers while the labels are being drawn on the gauge.



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default" drawLabels = {DrawLabels} ></EJ.CircularGauge>,
	document.getElementById('circular')
);

function DrawLabels(){
    // Do Something
};

{% endhighlight %}







### drawPointerCap





Triggers while the pointer cap is being drawn on the gauge.



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default" drawPointerCap = {DrawPointerCap} ></EJ.CircularGauge>,
	document.getElementById('circular')
);

function DrawPointerCap(){
    // Do Something
};

{% endhighlight %}







### drawPointers





Triggers while the pointers are being drawn on the gauge.



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default" drawPointers = {DrawPointers} ></EJ.CircularGauge>,
	document.getElementById('circular')
);

function DrawPointers(){
    // Do Something
};

{% endhighlight %}







### drawRange





Triggers when the ranges begin to be getting drawn on the gauge.




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default" drawRange = {DrawRange} ></EJ.CircularGauge>,
	document.getElementById('circular')
);

function DrawRange(){
    // Do Something
};

{% endhighlight %}







### drawTicks





Triggers while the ticks are being drawn on the gauge.




{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default" drawTicks = {DrawTicks} ></EJ.CircularGauge>,
	document.getElementById('circular')
);

function DrawTicks(){
    // Do Something
};

{% endhighlight %}







### load





Triggers while the gauge start to Load.



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default" load = {Load} ></EJ.CircularGauge>,
	document.getElementById('circular')
);

function Load(){
    // Do Something
};

{% endhighlight %}







### mouseClick





Triggers when the left mouse button is clicked.


{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default" mouseClick = {MouseClick} ></EJ.CircularGauge>,
	document.getElementById('circular')
);

function MouseClick(){
    // Do Something
};

{% endhighlight %}






### mouseClickMove





Triggers when clicking and dragging the mouse pointer over the gauge pointer.



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default" drawCustomLabel = {MouseClickMove} ></EJ.CircularGauge>,
	document.getElementById('circular')
);

function MouseClickMove(){
    // Do Something
};

{% endhighlight %}







### mouseClickUp





Triggers when the mouse click is released.



{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default" mouseClickUp = {MouseClickUp} ></EJ.CircularGauge>,
	document.getElementById('circular')
);

function MouseClickUp(){
    // Do Something
};

{% endhighlight %}







### renderComplete





Triggers when the rendering of the gauge is completed.


{% highlight html %}

<div id="circular"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.CircularGauge id="default" renderComplete = {RenderComplete} ></EJ.CircularGauge>,
	document.getElementById('circular')
);

function RenderComplete(){
    // Do Something
};

{% endhighlight %}




