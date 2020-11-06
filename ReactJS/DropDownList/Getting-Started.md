---
layout: post
title: Getting started with DropDownList widget for Syncfusion Essential JS
description: To get start with DropDownList by adding references.
platform: React JS
control: DropDownList
documentation: ug
keywords: DropDownList, dropdown, Populating data
---

# Getting Started

The external script dependencies of the DropDownList widget are,

* [jQuery 1.7.1](http://jquery.com/) and later versions.
* [jQuery.easing](http://gsgd.co.uk/sandbox/jquery/easing/) - to support the animation effects.

And the internal script dependencies of the DropDownList widget are:

<table>
	<tr>
		<th>File </th>
		<th>Description / Usage </th>
	</tr>
	<tr>
		<td>ej.core.min.js</td>
		<td>Must be referred always before using all the JS controls.</td>
	</tr>
	<tr>
		<td>ej.data.min.js</td>
		<td>Used to handle data operation and should be used while binding data to JS controls.</td>
	</tr>
	<tr>
		<td>ej.dropdownlist.min.js</td>
		<td>The dropdownlist’s main file</td>
	</tr>
	<tr>
		<td>ej.checkbox.min.js</td>
		<td>Should be referred when using checkbox functionalities in DropDownList.</td>
	</tr>
	<tr>
		<td>ej.scroller.min.js</td>
		<td>Should be referred when using scrolling in DropDownList.</td>
	</tr>
	<tr>
		<td>ej.draggable.min.js</td>
		<td>Should be referred when using popup resize functionality in DropDownList.</td>
	</tr>
</table>

For getting started you can use the ‘ej.web.all.min.js’ file, which encapsulates all the 'ej' controls and frameworks in one single file.<br/> 

For themes, you can use the ‘ej.web.all.min.css’ CDN link from the snippet given. To add the themes in your application, please refer [this link](http://help.syncfusion.com/js/theming-in-essential-javascript-components#adding-specific-theme-to-your-application).

## Creating DropDownList in React JS

The DropDownList can be created from a HTML ‘select’ element with the HTML 'id' attribute and pre-defined options set to it. Use the below given code to create a DropDownList in React JS.

You can create a React application and add necessary scripts and styles with the help of the given [React Getting Started Documentation.](https://help.syncfusion.com/reactjs/overview)

Define an HTML element for adding DropDownList in the application and refer the JSX file.

{% highlight html %}
	
<div id="dropdownlist-default"></div>
<script src="app/dropdownlist/default.js"></script>
			
{% endhighlight %}

Create a JSX file for rendering DropDownList component using &lt;EJ.DropDownList&gt; syntax. Add required properties to it in &lt;EJ.DropDownList&gt; tag element
	
{% highlight javascript %}	
	
"use strict";
	var list = [
		{ empid: "cr1", text: "ListItem 1", value: "ListItem 1" },
        { empid: "cr2", text: "ListItem 2", value: "ListItem 2" },
    	{ empid: "cr3", text: "ListItem 3", value: "ListItem 3" },
        { empid: "cr4", text: "ListItem 4", value: "ListItem 4" },
        { empid: "cr5", text: "ListItem 5", value: "ListItem 5" },
    ];

ReactDOM.render(
   <EJ.DropDownList dataSource={list} fields-text="text" fields-value="value">
   </EJ.DropDownList>,
document.getElementById('dropdownlist-default')
);
	
{% endhighlight %}

![](Getting-Started_images/Getting-Started_img1.jpeg)

## Populating data

The DropDownList can be bounded to both local array and remote data services using [ej.DataManager](http://help.syncfusion.com/js/datamanager/overview). You can use [DataManager](http://help.syncfusion.com/js/datamanager/overview) component to serve data from the data services based on the query provided.You can also bind local data using DataManager. To bind data to DropDownList widget, the [dataSource](http://help.syncfusion.com/js/api/ejdropdownlist#members:datasource) property should be assigned with the instance of 'ej.DataManager'.
 
N> ODataAdaptor is the default adaptor for DataManager. On binding to other web services, proper [data adaptor](http://help.syncfusion.com/js/datamanager/data-adaptors) needs to be set on 'adaptor' option of DataManager. 
	
{% highlight html %}

<div id="dropdownlist-default"></div>
<script src="app/dropdownlist/default.js"></script>

{% endhighlight %}
	
{% highlight javascript %}	
	
"use strict";

var  customers= [
                 { id: "1", text: "ALFKI" }, { id: "2", text: "ANATR" }, { id: "3", text: "ANTON" },
                 { id: "4", text: "AROUT" }, { id: "5", text: "BERGS" }, { id: "6", text: "BLAUS" }
            ];
var dataManager=ej.DataManager(customers);

ReactDOM.render(
   <EJ.DropDownList dataSource={dataManager} fields-text="text" >
   </EJ.DropDownList>,
document.getElementById('dropdownlist-default')
);
			
{% endhighlight %}
	
![](Getting-Started_images/Getting-Started_img2.jpeg)

## Setting Dimensions

DropDownList dimensions can be set using width and height API.
	
{% highlight html %}

<div id="dropdownlist-default"></div>
<script src="app/dropdownlist/default.js"></script>

{% endhighlight %}
	
{% highlight javascript %}	
	
"use strict";
	var list = [
		{ empid: "cr1", text: "ListItem 1", value: "ListItem 1" },
        { empid: "cr2", text: "ListItem 2", value: "ListItem 2" },
    	{ empid: "cr3", text: "ListItem 3", value: "ListItem 3" },
        { empid: "cr4", text: "ListItem 4", value: "ListItem 4" },
        { empid: "cr5", text: "ListItem 5", value: "ListItem 5" },
    ];

ReactDOM.render(
   <EJ.DropDownList dataSource={list} fields-text="text" fields-value='ListItem 1' width="300px" height="40px">
   </EJ.DropDownList>,
document.getElementById('dropdownlist-default')
);

{% endhighlight %}

**Setting dimensions to Popup list**

PopupWidth and popupHeight can be used to create a fixed size popup list.

{% highlight html %}

<select id="dropdown1" ej-dropdownlist e-datasource="dataList" e-value="value" e-popupHeight="popupheight" e-popupWidth="popupwidth"/>

{% endhighlight %}
	
{% highlight javascript %}

"use strict";
	var list = [
		{ empid: "cr1", text: "ListItem 1", value: "ListItem 1" },
        { empid: "cr2", text: "ListItem 2", value: "ListItem 2" },
    	{ empid: "cr3", text: "ListItem 3", value: "ListItem 3" },
        { empid: "cr4", text: "ListItem 4", value: "ListItem 4" },
        { empid: "cr5", text: "ListItem 5", value: "ListItem 5" },
    ];

ReactDOM.render(
   <EJ.DropDownList dataSource={list} fields-text="text" fields-value='ListItem 1' popupHeight="100px" popupWidth="200px">
   </EJ.DropDownList>,
document.getElementById('dropdownlist-default')
);
	
{% endhighlight %}
