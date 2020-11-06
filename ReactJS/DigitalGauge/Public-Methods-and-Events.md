---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: react-js
control: Digital Gauge
documentation: ug
---

## Methods





### destroy()



To destroy the digital gauge

{% highlight html %}

<div id="digital"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.DigitalGauge id="default"></EJ.DigitalGauge>,
	document.getElementById('digital')
);

function DigitalGaugeMethod(){
    var digitalObj = $("#default").data("ejDigitalGauge");
    digitalObj.destroy();
};

{% endhighlight %}







### exportImage(fileName, fileType)


To export Digital Gauge as Image



{% highlight html %}

<div id="digital"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.DigitalGauge id="default"></EJ.DigitalGauge>,
	document.getElementById('digital')
);

function DigitalGaugeMethod(){
    var digitalObj = $("#default").data("ejDigitalGauge");
    digitalObj.exportImage();
};

{% endhighlight %}






### getPosition(itemIndex)


Gets the location of an item that is displayed on the gauge.



{% highlight html %}

<div id="digital"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.DigitalGauge id="default"></EJ.DigitalGauge>,
	document.getElementById('digital')
);

function DigitalGaugeMethod(){
    var digitalObj = $("#default").data("ejDigitalGauge");
    digitalObj.getPosition();
};

{% endhighlight %}






### getValue(itemIndex)

ClientSideMethod getValue Gets the value of an item that is displayed on the gauge


{% highlight html %}

<div id="digital"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.DigitalGauge id="default"></EJ.DigitalGauge>,
	document.getElementById('digital')
);

function DigitalGaugeMethod(){
    var digitalObj = $("#default").data("ejDigitalGauge");
    digitalObj.getValue();
};

{% endhighlight %}







### refresh()


Refresh the digital gauge widget



{% highlight html %}

<div id="digital"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.DigitalGauge id="default"></EJ.DigitalGauge>,
	document.getElementById('digital')
);

function DigitalGaugeMethod(){
    var digitalObj = $("#default").data("ejDigitalGauge");
    digitalObj.refresh();
};

{% endhighlight %}





### setPosition(itemIndex, value)


ClientSideMethod Set Position Sets the location of an item to be displayed in the gauge


{% highlight html %}

<div id="digital"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.DigitalGauge id="default"></EJ.DigitalGauge>,
	document.getElementById('digital')
);

function DigitalGaugeMethod(){
    var digitalObj = $("#default").data("ejDigitalGauge");
    digitalObj.setPosition();
};

{% endhighlight %}





### setValue(itemIndex, value)

ClientSideMethod SetValue Sets the value of an item to be displayed in the gauge.


{% highlight html %}

<div id="digital"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.DigitalGauge id="default"></EJ.DigitalGauge>,
	document.getElementById('digital')
);

function DigitalGaugeMethod(){
    var digitalObj = $("#default").data("ejDigitalGauge");
    digitalObj.setValue();
};

{% endhighlight %}






## Events





### init

Triggers when the gauge is initialized.

{% highlight html %}

<div id="digital"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.DigitalGauge id="default" init = {Init}></EJ.DigitalGauge>,
	document.getElementById('digital')
);

function Init(){
    // Do Something
};

{% endhighlight %}







### itemRendering

Triggers when the gauge item rendering.


{% highlight html %}

<div id="digital"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.DigitalGauge id="default" itemRendering = {ItemRendering}></EJ.DigitalGauge>,
	document.getElementById('digital')
);

function ItemRendering(){
    // Do Something
};

{% endhighlight %}






### load

Triggers when the gauge is start to load.


{% highlight html %}

<div id="digital"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.DigitalGauge id="default" load = {Load}></EJ.DigitalGauge>,
	document.getElementById('digital')
);

function Load(){
    // Do Something
};

{% endhighlight %}




### renderComplete

Triggers when the gauge render is completed.


{% highlight html %}

<div id="digital"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.DigitalGauge id="default" renderComplete = {RenderComplete}></EJ.DigitalGauge>,
	document.getElementById('digital')
);

function RenderComplete(){
    // Do Something
};

{% endhighlight %}





