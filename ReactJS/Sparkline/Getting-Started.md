---
layout: post
title: Getting-Started
description: getting started
platform: React JS
control: Sparkline
documentation: ug
---
# Getting Started

This section explains you the steps required to populate the Sparkline with data, tooltips and type for Sparkline. This section covers only the minimal features that you need to know to get started with the Sparkline.


## Adding Script Reference

Create an **HTML** page and add the scripts references in the order mentioned in the following code example.

* [`jQuery`](http://jquery.com) 1.10.2 and later versions


The required ReactJS script dependencies as follows. And you can also refer [React](https://facebook.github.io/react/docs/getting-started.html) to know more about react js.

* `react.min.js` - [http://cdn.syncfusion.com/js/assets/external/react.min.js](http://cdn.syncfusion.com/js/assets/external/react.min.js)
* `react-dom.min.js` - [http://cdn.syncfusion.com/js/assets/external/react-dom.min.js](http://cdn.syncfusion.com/js/assets/external/react-dom.min.js)
* `ej.web.react.min.js` - [http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.web.react.min.js](http://cdn.syncfusion.com/14.3.0.49/js/common/ej.web.react.min.js)

To get started, you can use the `ej.web.all.min.js` file that encapsulates all the `ej` controls and frameworks in one single file.

{% highlight html %}
<!DOCTYPE html>
   <html>
     <head>
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta name="description" content="Essential Studio for React JS">
        <meta name="author" content="Syncfusion">
        <title>Getting Started for Ribbon React JS</title>
        <!-- Essential Studio for JavaScript  theme reference -->
        <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
        <!-- Essential Studio for JavaScript  script references -->
        <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
         <script src="http://cdn.syncfusion.com/js/assets/external/react.min.js"></script>
        <script src="http://cdn.syncfusion.com/js/assets/external/react-dom.min.js"></script>
        <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
        <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.web.react.min.js"></script>
        <!-- Add your custom scripts here -->
    </head>
        <body>
        </body>
   </html>

{% endhighlight %}

N> 1. In production, we highly recommend you to use our [`custom script generator`](http://help.syncfusion.com/js/custom-script-generator) to create custom script file with required controls and its dependencies only. Also to reduce the file size further please use [`GZip compression`](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer?hl=en) in your server.
N> 2. For themes, you can use the `ej.web.all.min.css` CDN link from the code snippet given. To add the themes in your application, please refer to [`this link`](http://help.syncfusion.com/js/theming-in-essential-javascript-components).

## Control Initialization

Control can be initialized in two ways.

 * Using jsx Template
 * Without using jsx Template
 
## Using jsx Template

By using the jsx template, we can create the html file and jsx file. The `.jsx` file can be convert to `.js` file and it can be referred in html page.

### Create Sparkline

You can easily create the Sparkline widget by following  the below steps.

1.Create a <div> tag.
	
   {% highlight html %}

<!DOCTYPE html>
<html>    
    <body>
	<div id="sparkline-default" ></div>
            <script src="app/sparkline/default.js"></script>    
    </body>
</html>

{% endhighlight %}


2.Initialize the Sparkline by using the `EJ.Sparkline` tag

{% highlight javascript %}

"use strict";
ReactDOM.render(
    <div className="default">
        <EJ.Sparkline id="sparkline1"></EJ.Sparkline>,
    </div>,
    document.getElementById('sparkline-default')
    );

{% endhighlight %}

Now, the Sparkline is rendered with some auto-generated random values and with default Line type Sparkline.

![](Getting-Started_images/Getting-Started_img1.jpg)

Simple Sparkline
{:.caption}

 The Sparkline is rendered to it's default size. You can also customize the Sparkline dimension either by setting the width and height of the container element as in the above code example or by using the **size** of the Sparkline.


## Populate Sparkline with data

Now, this section explains how to plot JSON data to the Sparkline. First, let us prepare a sample JSON data with each object containing following fields – employeeId and sales.

var sparklineData = [
{ employeeId: 1, sales: 25 },
{ employeeId: 2, sales: 28 },
{ employeeId: 3, sales: 34 },
{ employeeId: 4, sales: 32 },
{ employeeId: 5, sales: 40 },
{ employeeId: 6, sales: 32 },
{ employeeId: 7, sales: 35 },
{ employeeId: 8, sales: 55 },
{ employeeId: 9, sales: 38 },
{ employeeId: 10, sales: 30 }];

Now, add the dataSource to the Sparkline and provide the field name to get the values from the dataSource in xName and yName options.

{% highlight javascript %}
<script type="text/babel">

<!DOCTYPE html>
<html>    
    <body>
        <script type="text/babel">
            ReactDOM.render(
                     <div className="default">
                        <EJ.Sparkline id="sparkline1" dataSource={sparklineData} xName="employeeId" yName="sales"></EJ.Sparkline>,
                     </div>,
                     document.getElementById('sparkline-default')
                     );
        </script>
    </body>
</html>


{% endhighlight %}


## Sparkline Type 

 To change the sparkline types, following example code illustrates this.
{% highlight javascript %}

<script type="text/babel">

<!DOCTYPE html>
<html>    
    <body>
        <script type="text/babel">
            ReactDOM.render(
                     <div className="default">
                        <EJ.Sparkline id="sparkline1" type="column"></EJ.Sparkline>,
                     </div>,
                     document.getElementById('sparkline-default')
                     );
        </script>
    </body>
</html>


{% endhighlight %}


## Enable Tooltip

To enable the Sparkline tooltip we can see the current point values.

The following code example illustrates enable tooltip in sparkline,

{% highlight javascript %}

<script type="text/babel">
  var tooltip =    {
                visible: true,
                   };
<!DOCTYPE html>
<html>    
    <body>
        <script type="text/babel">
            ReactDOM.render(
                     <div className="default">
                        <EJ.Sparkline id="sparkline1" tooltip={tooltip}></EJ.Sparkline>,
                     </div>,
                     document.getElementById('sparkline-default')
                     );
        </script>
    </body>
</html>

{% endhighlight %}

![](Getting-Started_images/Getting-Started_img2.png)


## Without using jsx Template

The Sparkline can be created from a HTML `DIV` element with the HTML `id` attribute set to it. Refer to the following code example.

{% highlight html %}

<div id="sparkline-default"></div>
           
{% endhighlight %}

{% highlight javascript %}

<script type="text/babel">

var tooltip =    {
                visible: true,
                   };

 var dataSource1= [25,28,34,32,40,32,35,55,38,30];                  
        

ReactDOM.render(
    React.createElement(EJ.Sparkline, {id: "sparkline1", 
    dataSource: dataSource1, 
    tooltip: tooltip, 
    type: "line", 
     }
    ),
    document.getElementById('sparkline- default')
);

</script>
 {% endhighlight %}
 
 Run the above code example and you will see the following output.

![](Getting-Started_images/Getting-Started_img2.png)  