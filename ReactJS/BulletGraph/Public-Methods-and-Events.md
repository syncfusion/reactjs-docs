---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: react js
control: BulletGraph	
documentation: ug
api: /api/js/ejbulletgraph
---


## Methods



### destroy ()


To destroy the bullet graph


{% highlight html %}

<div id="bullet"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"></EJ.BulletGraph>,
	document.getElementById('bullet')
);

function BulletGraphMethod(){
    var bulletObj = $("#bulletCore0").data("ejBulletGraph");
    bulletObj.destroy();
};

{% endhighlight %}






### redraw()


To redraw the bullet graph



{% highlight html %}

<div id="bullet"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"></EJ.BulletGraph>,
	document.getElementById('bullet')
);

function BulletGraphMethod(){
    var bulletObj = $("#bulletCore0").data("ejBulletGraph");
    bulletObj.redraw();
};

{% endhighlight %}





### setComparativeMeasureSymbol()


To set the value for comparative measure in bullet graph.



{% highlight html %}

<div id="bullet"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"></EJ.BulletGraph>,
	document.getElementById('bullet')
);

function BulletGraphMethod(){
    var bulletObj = $("#bulletCore0").data("ejBulletGraph");
    bulletObj.setComparativeMeasureSymbol();
};

{% endhighlight %}







### setFeatureMeasureBarValue()


To set the value for feature measure bar.



{% highlight html %}

<div id="bullet"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"></EJ.BulletGraph>,
	document.getElementById('bullet')
);

function BulletGraphMethod(){
    var bulletObj = $("#bulletCore0").data("ejBulletGraph");
    bulletObj.setFeatureMeasureBarValue();
};

{% endhighlight %}






## Events



### drawCaption


Fires on rendering the caption of bullet graph.

{% highlight html %}

<div id="bullet"></div>

{% endhighlight %}

{% highlight javascript %}



ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	drawCaption = {DrawCaption}
    >        
            
    </EJ.BulletGraph>,
	document.getElementById('bullet')
);

function DrawCaption(){
    // Do Something
};

{% endhighlight %}




### drawCategory


Fires on rendering the category.


{% highlight html %}

<div id="bullet"></div>

{% endhighlight %}

{% highlight javascript %}


ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	drawCategory = {DrawCategory}
    >        
            
    </EJ.BulletGraph>,
	document.getElementById('bullet')
);

function DrawCategory(){
    // Do Something
};

{% endhighlight %}









### drawComparativeMeasureSymbol

Fires on rendering the comparative measure symbol.


{% highlight html %}

<div id="bullet"></div>

{% endhighlight %}

{% highlight javascript %}


ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	drawComparativeMeasureSymbol = {DrawComparativeMeasureSymbol}
    >        
            
    </EJ.BulletGraph>,
	document.getElementById('bullet')
);

function DrawComparativeMeasureSymbol(){
    // Do Something
};

{% endhighlight %}





### drawFeatureMeasureBar

Fires on rendering the feature measure bar.


{% highlight html %}

<div id="bullet"></div>

{% endhighlight %}

{% highlight javascript %}


ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	drawFeatureMeasureBar = {DrawFeatureMeasureBar}
    >        
            
    </EJ.BulletGraph>,
	document.getElementById('bullet')
);

function DrawFeatureMeasureBar(){
    // Do Something
};

{% endhighlight %}







### drawIndicator


Fires on rendering the indicator of bullet graph.


{% highlight html %}

<div id="bullet"></div>

{% endhighlight %}

{% highlight javascript %}


ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	drawIndicator = {DrawIndicator}
    >        
            
    </EJ.BulletGraph>,
	document.getElementById('bullet')
);

function DrawIndicator(){
    // Do Something
};

{% endhighlight %}







### drawLabels

Fires on rendering the labels.

{% highlight html %}

<div id="bullet"></div>

{% endhighlight %}

{% highlight javascript %}


ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	drawLabels = {DrawLabels}
    >        
            
    </EJ.BulletGraph>,
	document.getElementById('bullet')
);

function drawLabels(){
    // Do Something
};

{% endhighlight %}







### drawQualitativeRanges


Fires on rendering the qualitative ranges.


{% highlight html %}

<div id="bullet"></div>

{% endhighlight %}

{% highlight javascript %}


ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	drawQualitativeRanges = {DrawQualitativeRanges}
    >        
            
    </EJ.BulletGraph>,
	document.getElementById('bullet')
);

function DrawQualitativeRanges(){
    // Do Something
};

{% endhighlight %}






### load


Fires on loading bullet graph.



{% highlight html %}

<div id="bullet"></div>

{% endhighlight %}

{% highlight javascript %}


ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	load = {load}
    >        
            
    </EJ.BulletGraph>,
	document.getElementById('bullet')
);

function load(){
    // Do Something
};

{% endhighlight %}




