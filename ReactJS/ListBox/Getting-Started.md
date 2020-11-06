---
layout: post
title: getting started
description: getting started
platform: js
control: ListBox
documentation: ug
---

## Getting Started

The React **ListBox** control contains a list of selectable items. It performs exceptionally well with thousands of items and supports checkboxes, template, single and multiple selection, keyboard navigation and virtual scrolling.

## Key Features

**Data Binding**: Supports Data binding with JSON data and remote data.

**Multi Selection**: Supports multiple selection of list items.

**Virtual Scrolling**: Provides support to load its data on demand through virtual scrolling which greatly improves the application’s performance.

**Template Support**: Support Template contents to render as list items

**Grouping**: Groups the set of list items with header

**Cascading**: To populate data in a ListBox based on the selection in another ListBox.

**Drag and Drop**: Supports drag and drop features for list items


This section helps to understand the getting started of the React ListBox with the step-by-step instructions.


## Create an ListBox 

You can create a React application and add necessary scripts and styles with the help of the given [ReactJJs Getting Started](https://help.syncfusion.com/reactjs/overview) Documentation.

Define an HTML element for adding ListBox in the application and refer the JSX file created.

{% highlight html %}

<script src="scripts/sampledata.js"></script>
<div id="listbox-default"></div>
<script src="app/listbox/default.js"></script>


{% endhighlight %}



To configure data for ListBox component, define data in an array and map corresponding fields to it.

{% highlight js %}

var BikeList = [
{ empid: "bk1", text: "Aache RTR" }, { empid: "bk2", text: "CBR 150-R" }, { empid: "bk3", text: "CBZ Xtreme" },
    { empid: "bk4", text: "Discover" }, { empid: "bk5", text: "Dazzler" }, { empid: "bk6", text: "Flame" },
    { empid: "bk7", text: "Fazzer" }, { empid: "bk8", text: "FZ-S" }, { empid: "bk9", text: "Pulsar" },
    { empid: "bk10", text: "Shine" }, { empid: "bk11", text: "R15" }, { empid: "bk12", text: "Unicorn" }
];

window.listBoxFields = { id: "empid", value: "text" };


{% endhighlight %}


Create a JSX file for rendering ListBox component using &lt;EJ.ListBox&gt; syntax. Add required properties to it in &lt;EJ.ListBox&gt; tag element

{% highlight js %}

"use strict";

ReactDOM.render(
  <div>  
    <div className="lblTitle">Select a bike</div>
<EJ.ListBox id="default" width="100%" dataSource={BikeList} fields={window.listBoxFields}>
    </EJ.ListBox>
  </div>,
document.getElementById('listbox-default')
);


{% endhighlight %}



Run the above code to render the following output:

![](GettingStarted_images\createanlistbox_img1.png)

## Selection

The React **ListBox** widget also supports the item selection.

Use the following code render the ListBox with Selection

{% highlight js %}

"use strict";

ReactDOM.render(
  <div>  
    <div className="lblTitle">Select a bike</div>
<EJ.ListBox id="default" width="100%" dataSource={BikeList} fields={window.listBoxFields} selectedIndex=”2”>
    </EJ.ListBox>
  </div>,
document.getElementById('listbox-default')
);


{% endhighlight %}



Run the above code to render the following output.



![](GettingStarted_images\selection_img1.png)



_Note: You can find the ListBox properties from the_ [API reference](https://help.syncfusion.com/api/js/ejlistbox) _document_ 




