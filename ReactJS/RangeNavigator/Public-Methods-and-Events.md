---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: react js
control: RangeNavigator
documentation: ug
---

## Methods








### _destroy ()









destroy the range navigator widget



{% highlight html %}

<div id="range"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.RangeNavigator id="default"></EJ.RangeNavigator>,
	document.getElementById('range')
);

function RangeNavigatorMethod(){
    var rangeObj = $("#default").data("ejRangeNavigator");
    rangeObj.destroy();
};

{% endhighlight %}








## Events








### load









Fires on load of range navigator.


{% highlight html %}

<div id="range"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.RangeNavigator id="default" load = {Load}></EJ.RangeNavigator>,
	document.getElementById('range')
);

function Load(){
    // Do Something
};

{% endhighlight %}







### loaded









Fires after range navigator is loaded.


{% highlight html %}

<div id="range"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.RangeNavigator id="default" loaded = {Loaded}></EJ.RangeNavigator>,
	document.getElementById('range')
);

function Loaded(){
    // Do Something
};

{% endhighlight %}








### rangeChanged









Fires on changing the range of range navigator.


{% highlight html %}

<div id="range"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.RangeNavigator id="default" rangeChanged = {RangeChanged}></EJ.RangeNavigator>,
	document.getElementById('range')
);

function RangeChanged(){
    // Do Something
};

{% endhighlight %}






### scrollChanged



Fires on changing the scrollbar position of range navigator.




{% highlight html %}

<div id="range"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.RangeNavigator id="default" scrollChanged = {ScrollChanged}></EJ.RangeNavigator>,
	document.getElementById('range')
);

function ScrollChanged(){
    // Do Something
};

{% endhighlight %}




### scrollStart



Fires on when starting to change the scrollbar position of range navigator.



{% highlight html %}

<div id="range"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.RangeNavigator id="default" scrollStart = {ScrollStart}></EJ.RangeNavigator>,
	document.getElementById('range')
);

function ScrollStart(){
   // Do Something
};

{% endhighlight %}


### selectedRangeStart




Fires on when starting to change the slider position of range navigator.






{% highlight html %}

<div id="range"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.RangeNavigator id="default" selectedRangeStart = {SelectedRangeStart}></EJ.RangeNavigator>,
	document.getElementById('range')
);

function SelectedRangeStart(){
    // Do Something
};

{% endhighlight %}

### selectedRangeEnd 




Fires when the selection  ends in the range navigator





{% highlight html %}

<div id="range"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.RangeNavigator id="default" selectedRangeEnd = {SelectedRangeEnd}></EJ.RangeNavigator>,
	document.getElementById('range')
);

function SelectedRangeEnd(){
    // Do Something
};

{% endhighlight %}



### scrollEnd



Fires on changes ending the scrollbar position of range navigator.





{% highlight html %}

<div id="range"></div>

{% endhighlight %}

{% highlight javascript %}

ReactDOM.render(
    <EJ.RangeNavigator id="default" scrollEnd = "ScrollEnd"></EJ.RangeNavigator>,
	document.getElementById('range')
);

function ScrollEnd(){
    // Do Something
};

{% endhighlight %}


