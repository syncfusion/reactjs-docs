---
layout: post
title: Welcome to Syncfusion Essential ReactJS
description: Overview of Syncfusion Essential ReactJS widgets based on HTML5 and jQuery.
platform: ReactJS
control: Barcode
documentation: ug
---

# Overview

The Syncfusion Essential JS Barcode widget enables rendering of one dimension and two dimension barcodes in web page. Barcode provides you a simple and inexpensive method of encoding text information that can be easily read by electronic readers.

**Key Features**

* Supports 10 one-dimensional barcodes including Code 39 and Code 32 barcodes.
* Supports 2 two-dimensional barcodes such as QR and Data Matrix barcodes.

This section helps to understand the getting started of the ReactJS Barcode with the step-by-step instructions.

## Create an Barcode


You can create a React application and add necessary scripts and styles with the help of the given [ReactJs Getting Started](https://help.syncfusion.com/reactjs/overview) Documentation.

Define an HTML element for adding Barcode in the application and refer the JSX file created.

{% highlight html %}

<div id="barcode-qrbarcode" align="center"></div>
<script src="app/barcode/qrbarcode.js"></script>


{% endhighlight %}



Create a JSX file for rendering Barcode component using <EJ.Barcode> syntax.

{% highlight js %}

"use strict";

ReactDOM.render(
    <div className="control">
        <EJ.Barcode id="default" text="http://www.syncfusion.com" symbologyType="qrbarcode" xDimension="5" >
        </EJ.Barcode>
    </div>,  
document.getElementById('barcode-default')
);


{% endhighlight %}


Run the above code to render the following output:

![](getting-started-images\default.png)
