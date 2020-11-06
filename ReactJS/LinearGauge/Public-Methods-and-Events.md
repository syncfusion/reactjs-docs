---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: react js
control: Linear Gauge
documentation: ug
api: /api/js/ejlineargauge
---


## Methods








### destroy()


destroy the linear gauge all events bound using this._on will be unbind automatically and bring the control to pre-init state.

{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.destroy();
};

{% endhighlight %}







### exportImage()



To export Image


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.exportImage();
};

{% endhighlight %}







### getBarDistanceFromScale()

To get Bar Distance From Scale in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getBarDistanceFromScale();
};

{% endhighlight %}







### getBarPointerValue()


To get Bar Pointer Value in number



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getBarPointerValue();
};

{% endhighlight %}







### getBarWidth()









To get Bar Width in number



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getBarWidth();
};

{% endhighlight %}







### getCustomLabelAngle()









To get CustomLabel Angle in number



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getCustomLabelAngle();
};

{% endhighlight %}







### getCustomLabelValue()









To get CustomLabel Value in string



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getCustomLabelValue();
};

{% endhighlight %}







### getLabelAngle()









To get Label Angle in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getLabelAngle();
};

{% endhighlight %}







### getLabelPlacement()






To get LabelPlacement in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getLabelPlacement();
};

{% endhighlight %}







### getLabelStyle()





To get LabelStyle in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getLabelStyle();
};

{% endhighlight %}







### getLabelXDistanceFromScale()









To get Label XDistance From Scale in number



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getLabelXDistanceFromScale();
};

{% endhighlight %}






### getLabelYDistanceFromScale()









To get PointerValue in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getLabelYDistanceFromScale();
};

{% endhighlight %}






### getMajorIntervalValue()









To get Major Interval Value in number



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getMajorIntervalValue();
};

{% endhighlight %}







### getMarkerStyle()









To get MarkerStyle in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getMarkerStyle();
};

{% endhighlight %}







### getMaximumValue()









To get Maximum Value in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getMaximumValue();
};

{% endhighlight %}






### getMinimumValue()









To get PointerValue in number



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getMinimumValue();
};

{% endhighlight %}







### getMinorIntervalValue()









To get Minor Interval Value in number

{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getMinorIntervalValue();
};

{% endhighlight %}







### getPointerDistanceFromScale()









To get Pointer Distance From Scale in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getPointerDistanceFromScale();
};

{% endhighlight %}







### getPointerHeight()









To get PointerHeight in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getPointerHeight();
};

{% endhighlight %}






### getPointerPlacement()









To get Pointer Placement in String



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getPointerPlacement();
};

{% endhighlight %}







### getPointerValue()









To get PointerValue in number



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getPointerValue();
};

{% endhighlight %}







### getPointerWidth()









To get PointerWidth in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getPointerWidth();
};

{% endhighlight %}







### getRangeBorderWidth()









To get Range Border Width in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getRangeBorderWidth();
};

{% endhighlight %}







### getRangeDistanceFromScale()









To get Range Distance From Scale in number



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getRangeDistanceFromScale();
};

{% endhighlight %}







### getRangeEndValue()









To get Range End Value in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getRangeEndValue();
};

{% endhighlight %}







### getRangeEndWidth()









To get Range End Width in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getRangeEndWidth();
};

{% endhighlight %}







### getRangePosition()









To get Range Position in number



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getRangePosition();
};

{% endhighlight %}







### getRangeStartValue()









To get Range Start Value in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getRangeStartValue();
};

{% endhighlight %}







### getRangeStartWidth()









To get Range Start Width in number

{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getRangeStartWidth();
};

{% endhighlight %}







### getScaleBarLength()









To get ScaleBarLength in number



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getScaleBarLength();
};

{% endhighlight %}







### getScaleBarSize()









To get Scale Bar Size in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getScaleBarSize();
};

{% endhighlight %}







### getScaleBorderWidth()









To get Scale Border Width in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getScaleBorderWidth();
};

{% endhighlight %}







### getScaleDirection()









To get Scale Direction in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getScaleDirection();
};

{% endhighlight %}







### getScaleLocation()









To get Scale Location in object

{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getScaleLocation();
};

{% endhighlight %}







### getScaleStyle()









To get Scale Style in string



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getScaleStyle();
};

{% endhighlight %}







### getTickAngle()



To get Tick Angle in number



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getTickAngle();
};

{% endhighlight %}







### getTickHeight()









To get Tick Height in number



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getTickHeight();
};

{% endhighlight %}







### getTickPlacement()









To get getTickPlacement in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getTickPlacement();
};

{% endhighlight %}







### getTickStyle()









To get Tick Style in string


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getTickStyle();
};

{% endhighlight %}







### getTickWidth()









To get Tick Width in number


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getTickWidth();
};

{% endhighlight %}







### getTickXDistanceFromScale()









To get get Tick XDistance From Scale in number

{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getTickXDistanceFromScale();
};

{% endhighlight %}






### getTickYDistanceFromScale()









To get Tick YDistance From Scale in number



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.getTickYDistanceFromScale();
};

{% endhighlight %}







### scales()









Specifies the scales.



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.scales();
};

{% endhighlight %}







### setBarDistanceFromScale()








To set setBarDistanceFromScale

{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setBarDistanceFromScale();
};

{% endhighlight %}






### setBarPointerValue()









To set setBarPointerValue



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setBarPointerValue();
};

{% endhighlight %}







### setBarWidth()









To set setBarWidth


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setBarWidth();
};

{% endhighlight %}







### setCustomLabelAngle()









To set setCustomLabelAngle


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setCustomLabelAngle();
};

{% endhighlight %}







### setCustomLabelValue()









To set setCustomLabelValue


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setCustomLabelValue();
};

{% endhighlight %}







### setLabelAngle()









To set setLabelAngle


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setLabelAngle();
};

{% endhighlight %}







### setLabelPlacement()









To set setLabelPlacement


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setLabelPlacement();
};

{% endhighlight %}







### setLabelStyle()









To set setLabelStyle


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setLabelStyle();
};

{% endhighlight %}







### setLabelXDistanceFromScale()









To set setLabelXDistanceFromScale

{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setLabelXDistanceFromScale();
};

{% endhighlight %}







### setLabelYDistanceFromScale()









To set setLabelYDistanceFromScale


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setLabelYDistanceFromScale();
};

{% endhighlight %}






### setMajorIntervalValue()









To set setMajorIntervalValue


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setMajorIntervalValue();
};

{% endhighlight %}







### setMarkerStyle()









To set setMarkerStyle


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setMarkerStyle();
};

{% endhighlight %}







### setMaximumValue()









To set setMaximumValue


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setMaximumValue();
};

{% endhighlight %}







### setMinimumValue()









To set setMinimumValue


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setMinimumValue();
};

{% endhighlight %}







### setMinorIntervalValue()









To set setMinorIntervalValue


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setMinorIntervalValue();
};

{% endhighlight %}







### setPointerDistanceFromScale()









To set setPointerDistanceFromScale


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setPointerDistanceFromScale();
};

{% endhighlight %}







### setPointerHeight()









To set PointerHeight



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setPointerHeight();
};

{% endhighlight %}







### setPointerPlacement()









To set setPointerPlacement



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setPointerPlacement();
};

{% endhighlight %}







### setPointerValue()









To set PointerValue


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setPointerValue();
};

{% endhighlight %}







### setPointerWidth()









To set PointerWidth


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setPointerWidth();
};

{% endhighlight %}







### setRangeBorderWidth()









To set setRangeBorderWidth


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setRangeBorderWidth();
};

{% endhighlight %}







### setRangeDistanceFromScale()









To set setRangeDistanceFromScale


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setRangeDistanceFromScale();
};

{% endhighlight %}







### setRangeEndValue()









To set setRangeEndValue


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setRangeEndValue();
};

{% endhighlight %}







### setRangeEndWidth()









To set setRangeEndWidth


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setRangeEndWidth();
};

{% endhighlight %}







### setRangePosition()









To set setRangePosition


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setRangePosition();
};

{% endhighlight %}







### setRangeStartValue()









To set setRangeStartValue



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setRangeStartValue();
};

{% endhighlight %}







### setRangeStartWidth()









To set setRangeStartWidth


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setRangeStartWidth();
};

{% endhighlight %}







### setScaleBarLength()









To set setScaleBarLength



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setScaleBarLength();
};

{% endhighlight %}







### setScaleBarSize()









To set setScaleBarSize


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setScaleBarSize();
};

{% endhighlight %}







### setScaleBorderWidth()









To set setScaleBorderWidth


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setScaleBorderWidth();
};

{% endhighlight %}







### setScaleDirection()









To set setScaleDirection


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setScaleDirection();
};

{% endhighlight %}







### setScaleLocation()









To set setScaleLocation


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setScaleLocation();
};

{% endhighlight %}







### setScaleStyle()









To set setScaleStyle


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setScaleStyle();
};

{% endhighlight %}







### setTickAngle()









To set setTickAngle


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setTickAngle();
};

{% endhighlight %}







### setTickHeight()









To set setTickHeight


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setTickHeight();
};

{% endhighlight %}







### setTickPlacement()









To set setTickPlacement


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setTickPlacement();
};

{% endhighlight %}







### setTickStyle()









To set setTickStyle



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setTickStyle();
};

{% endhighlight %}







### setTickWidth()









To set setTickWidth


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setTickWidth();
};

{% endhighlight %}






### setTickXDistanceFromScale()









To set setTickXDistanceFromScale


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setTickXDistanceFromScale();
};

{% endhighlight %}







### setTickYDistanceFromScale()









To set setTickYDistanceFromScale


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default"></EJ.LinearGauge>,
	document.getElementById('linear')
);

function LinearGaugeMethod(){
    var linearObj = $("#default").data("ejLinearGauge");
    linearObj.setTickYDistanceFromScale();
};

{% endhighlight %}





## Events








### drawBarPointers









Triggers while the bar pointer are being drawn on the gauge.

{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default" drawBarPointers = {DrawBarPointers}></EJ.LinearGauge>,
	document.getElementById('linear')
);

function DrawBarPointers(){
    // Do Something
};

{% endhighlight %}








### drawCustomLabel









Triggers while the customLabel are being drawn on the gauge.


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default" drawCustomLabel = {DrawCustomLabel}></EJ.LinearGauge>,
	document.getElementById('linear')
);

function DrawCustomLabel(){
    // Do Something
};

{% endhighlight %}









### drawIndicators









Triggers while the Indicator are being drawn on the gauge.


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default" drawIndicators = {DrawIndicators}></EJ.LinearGauge>,
	document.getElementById('linear')
);

function DrawIndicators(){
     // Do Something
};

{% endhighlight %}








### drawLabels









Triggers while the label are being drawn on the gauge.



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default" drawLabels = {DrawLabels}></EJ.LinearGauge>,
	document.getElementById('linear')
);

function DrawLabels(){
     // Do Something
};

{% endhighlight %}









### drawMarkerPointers









Triggers while the marker are being drawn on the gauge.



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default" drawMarkerPointers={DrawMarkerPointers}></EJ.LinearGauge>,
	document.getElementById('linear')
);

function DrawMarkerPointers(){
     // Do Something
};

{% endhighlight %}









### drawRange









Triggers while the range are being drawn on the gauge.


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default" drawRange = {DrawRange}></EJ.LinearGauge>,
	document.getElementById('linear')
);

function DrawRange(){
      // Do Something
};

{% endhighlight %}









### drawTicks









Triggers while the ticks are being drawn on the gauge.


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default" drawTicks = {DrawTicks}></EJ.LinearGauge>,
	document.getElementById('linear')
);

function DrawTicks(){
     // Do Something
};

{% endhighlight %}









### init









Triggers when the gauge is initialized.


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default" init = {Init}></EJ.LinearGauge>,
	document.getElementById('linear')
);

function Init(){
      // Do Something
};

{% endhighlight %}









### load









Triggers while the gauge start to Load.


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default" load = {Load}></EJ.LinearGauge>,
	document.getElementById('linear')
);

function Load(){
      // Do Something
};

{% endhighlight %}









### mouseClick









Triggers when the left mouse button is clicked.


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default" mouseClick = {MouseClick}></EJ.LinearGauge>,
	document.getElementById('linear')
);

function MouseClick(){
      // Do Something
};

{% endhighlight %}









### mouseClickMove









Triggers when clicking and dragging the mouse pointer over the gauge pointer.

{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default" mouseClickMove={MouseClickMove}></EJ.LinearGauge>,
	document.getElementById('linear')
);

function MouseClickMove(){
      // Do Something
};

{% endhighlight %}









### mouseClickUp









Triggers when the mouse click is released.


{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default" mouseClickUp = {MouseClickUp}></EJ.LinearGauge>,
	document.getElementById('linear')
);

function MouseClickUp(){
      // Do Something
};

{% endhighlight %}









### renderComplete









Triggers while the rendering of the gauge completed.



{% highlight html %}

<div id="linear"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.LinearGauge id="default" renderComplete = {RenderComplete}></EJ.LinearGauge>,
	document.getElementById('linear')
);

function RenderComplete(){
    // Do Something
};

{% endhighlight %}




