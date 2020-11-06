---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: react js
control: Maps
documentation: ug
---


## Methods

### navigateTo(latitude, longitude, level)


Method for navigating to specific shape based on latitude, longitude and zoom level.



{% highlight html %}

<div id="map"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Map id="default"></EJ.Map>,
	document.getElementById('map')
);

function MapMethod(){
    var mapObj = $("#default").data("ejMap");
    mapObj.navigateTo();
};

{% endhighlight %}


### pan(direction)


Method to perform map panning


{% highlight html %}

<div id="map"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Map id="default"></EJ.Map>,
	document.getElementById('map')
);

function MapMethod(){
    var mapObj = $("#default").data("ejMap");
    mapObj.pan();
};

{% endhighlight %}


### refresh()


Method to reload the map.




{% highlight html %}

<div id="map"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Map id="default"></EJ.Map>,
	document.getElementById('map')
);

function MapMethod(){
    var mapObj = $("#default").data("ejMap");
    mapObj.refresh();
};

{% endhighlight %}


### refreshLayers()


Method to reload the shapeLayers with updated values



{% highlight html %}

<div id="map"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Map id="default"></EJ.Map>,
	document.getElementById('map')
);

function MapMethod(){
    var mapObj = $("#default").data("ejMap");
    mapObj.refreshLayers();
};

{% endhighlight %}


### refreshNavigationControl(navigation)


Method to reload the navigation control with updated values.



{% highlight html %}

<div id="map"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Map id="default"></EJ.Map>,
	document.getElementById('map')
);

function MapMethod(){
    var mapObj = $("#default").data("ejMap");
    mapObj.refreshNavigationControl();
};

{% endhighlight %}


### zoom(level, isAnimate)


Method to perform map zooming.



{% highlight html %}

<div id="map"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Map id="default"></EJ.Map>,
	document.getElementById('map')
);

function MapMethod(){
    var mapObj = $("#default").data("ejMap");
    mapObj.zoom();
};

{% endhighlight %}



## Events

### markerSelected


Triggered on selecting the map markers.


{% highlight html %}

<div id="map"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Map id="default" markerSelected = {MarkerSelected}></EJ.Map>,
	document.getElementById('map')
);

function MarkerSelected(){
    // Do Something
};

{% endhighlight %}



### mouseleave


Triggers while leaving the hovered map shape


{% highlight html %}

<div id="map"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Map id="default" mouseleave = {Mouseleave}></EJ.Map>,
	document.getElementById('map')
);

function Mouseleave(){
    // Do Something
};

{% endhighlight %}



### mouseover


Triggers while hovering the map shape.


{% highlight html %}

<div id="map"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Map id="default" mouseover = {Mouseover}></EJ.Map>,
	document.getElementById('map')
);

function Mouseover(){
    // Do Something
};

{% endhighlight %}



### onRenderComplete


Triggers once map render completed.


{% highlight html %}

<div id="map"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Map id="default" onRenderComplete = {OnRenderComplete}></EJ.Map>,
	document.getElementById('map')
);

function OnRenderComplete(){
    // Do Something
};

{% endhighlight %}



### panned


Triggers when map panning ends.


{% highlight html %}

<div id="map"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Map id="default" panned = {Panned}></EJ.Map>,
	document.getElementById('map')
);

function Panned(){
   // Do Something
};

{% endhighlight %}



### shapeSelected


Triggered on selecting the map shapes.


{% highlight html %}

<div id="map"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Map id="default" shapeSelected = {ShapeSelected}></EJ.Map>,
	document.getElementById('map')
);

function ShapeSelected(){
    // Do Something
};

{% endhighlight %}



### zoomedIn


Triggered when map is zoomed-in.


{% highlight html %}

<div id="map"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Map id="default" zoomedIn = {ZoomedIn}></EJ.Map>,
	document.getElementById('map')
);

function ZoomedIn(){
   // Do Something
};

{% endhighlight %}



### zoomedOut


Triggers when map is zoomed out.


{% highlight html %}

<div id="map"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.Map id="default" zoomedOut = {ZoomedOut}></EJ.Map>,
	document.getElementById('map')
);

function ZoomedOut(){
   // Do Something
};

{% endhighlight %}

<a class="" href="http://www.syncfusion.com/copyright" target="_blank">Copyright &copy; 2001 - 2015 Syncfusion Inc. All Rights Reserved</a>

