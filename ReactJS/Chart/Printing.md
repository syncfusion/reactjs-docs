---
layout: post
title: Print  in Essential JavaScript Chart
description: Learn how to print the chart.
platform: js
control: Chart
documentation: ug
api : /api/js/ejchart
---

# Printing Chart
The rendered chart can be printed directly from the browser by calling the public method [`print`](../api/ejchart#methods:print). ID of the chart div element must be passed as argument to that method.

{% highlight html %}

<body>
   <button type="button" onclick="print()" ></button> 
<div id="chartcontainer"></div>
<script>
function print() {
var chartObj = $("#chartcontainer").ejChart("instance");
chartObj.print("chartcontainer");
        }
</script>
</body>

{% endhighlight %}

{% highlight html %}

ReactDOM.render(
    <EJ.Chart id="chartcontainer">
            
    </EJ.Chart>,
	document.getElementById('chartcontainer')
);

{% endhighlight %}


This print method can be called by performing any action on the web page. For example, by clicking a button. While calling the print method in chart, print preview will be displayed in the browser.

![](/js/Chart/Printing_images/Printing_img1.png)

[Click](http://js.syncfusion.com/demos/web/#!/bootstrap/chart/exportandprint) here to view the Printing chart online demo sample

## Printing Multiple chart

Multiple charts in a web page can be printed together. For printing multiple charts, ID of the chart div elements have to be passed as shown in the below code 


{% highlight javascript %}
   
//Render Chart1
ReactDOM.render(
    <EJ.Chart id="container1">
            
    </EJ.Chart>,
        document.getElementById('container1')
);

//Render Chart2
ReactDOM.render(
    <EJ.Chart id="container2">
            
    </EJ.Chart>,
       document.getElementById('container2')
);


//Print multiple charts 
function print() {
    var chartObj = $("#container1").ejChart("instance");
    chartObj.print("container1","container2");
}

{% endhighlight %}

The Print preview of multiple Charts is shown below 

![](/js/Chart/Printing_images/Printing_img2.png)

## Page Setup

Some of print options are not configurable through JavaScript code. You need to customize layout, paper size, margins options through browser's page setup dialog. Please find the following guidelines link to browser page setup.

* [Chrome](https://support.google.com/chrome/answer/1379552?hl=en)
* [Firefox](https://support.mozilla.org/en-US/kb/how-print-web-pages-firefox)
* [Safari](http://www.mintprintables.com/print-tips/adjust-margins-osx/)
* [IE](http://www.helpteaching.com/help/print/index.htm) 
