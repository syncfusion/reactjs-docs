---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: react js
control: TreeMap
documentation: ug
---

## Methods

### refresh()


Method to reload treemap with updated values.



{% highlight html %}

<div id="tree"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.TreeMap id="default"></EJ.TreeMap>,
	document.getElementById('map')
);

function TreeTreeMapMethod(){
    var treeObj = $("#default").data("ejTreeMap");
    treeObj.refresh();
};

{% endhighlight %}



## Events

### treeMapItemSelected


Triggers on treemap item selected.


{% highlight html %}

<div id="tree"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.TreeMap id="default" treeMapItemSelected = {TreeMapItemSelected}></EJ.TreeMap>,
	document.getElementById('tree')
);

function TreeMapItemSelected(){
   // Do Something
};

{% endhighlight %}

### drillStarted


Triggers when drilldown is started



{% highlight html %}

<div id="tree"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.TreeMap id="default" drillStarted = {DrillStarted}></EJ.TreeMap>,
	document.getElementById('tree')
);

function DrillStarted(){
    // Do Something
};

{% endhighlight %}

### drillDownItemSelected


Triggers on treemap  drilldown  item  selected.




{% highlight html %}

<div id="tree"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.TreeMap id="default" drillDownItemSelected = {DrillDownItemSelected}></EJ.TreeMap>,
	document.getElementById('tree')
);

function DrillDownItemSelected(){
   // Do Something
};

{% endhighlight %}

### headerTemplateRendering


Triggers before rendering the treemap drilldown header template



{% highlight html %}

<div id="tree"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.TreeMap id="default" headerTemplateRendering = {HeaderTemplateRendering}></EJ.TreeMap>,
	document.getElementById('tree')
);

function HeaderTemplateRendering(){
    // Do Something
};

{% endhighlight %}


### refreshed


Triggers after refreshing the treemap items.


 
{% highlight html %}

<div id="tree"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.TreeMap id="default" refreshed = {Refreshed}></EJ.TreeMap>,
	document.getElementById('tree')
);

function Refreshed(){
   // Do Something
};

{% endhighlight %}


### treeMapGroupSelected


Triggers when the group selection is performed on treemap items.


{% highlight html %}

<div id="tree"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.TreeMap id="default" treeMapGroupSelected = {TreeMapGroupSelected}></EJ.TreeMap>,
	document.getElementById('tree')
);

function TreeMapGroupSelected(){
    // Do Something
};

{% endhighlight %}



