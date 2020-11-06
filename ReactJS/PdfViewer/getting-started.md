---
title: Getting Started for Angular 2 PDF viewer
description: PDF viewer 
platform: React JS
control: PDF viewer
documentation: ug
keywords: ejPdfViewer, PDF viewer, js pdfviewer
---

# Getting Started

This section explains briefly about how to integrate a **PDF viewer** control in your application with **React JS**.

## Script and CSS Reference

Create a **HTML** page and add the scripts and CSS references in the order mentioned in the following code example.

{% highlight html %}

    <!DOCTYPE html>
    <html>
        <head>
            <!-- Essential Studio for JavaScript  theme reference -->
            <link rel="stylesheet" href="http://cdn.syncfusion.com/14.4.0.15/js/web/bootstrap-theme/ej.web.all.min.css" />           
            <!--  react script  -->
            <script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.2.1/react.js"></script>
            <script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.2.1/react-dom.js"></script>
            <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.34/browser.min.js"></script>
            <!--  jquery script  -->
            <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
            <!-- Essential JS UI widget -->    
            <script src="http://cdn.syncfusion.com/14.4.0.15/js/web/ej.web.all.min.js"></script>
            <script src="http://cdn.syncfusion.com/14.4.0.15/js/common/ej.web.react.min.js"></script>

            <!--Add custom scripts here -->
        </head>
        <body>
        </body>
    </html>

{% endhighlight %}

N> 1. In production, we highly recommend you to use our [`custom script generator`](http://help.syncfusion.com/js/custom-script-generator) to create custom script file with required controls and its dependencies only. Also to reduce the file size further please use [`GZip compression`](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer?hl=en) in your server.

N> 2. For themes, you can use the `ej.web.all.min.css` CDN link from the code snippet given. To add the themes in your application, please refer to [`this link`](http://help.syncfusion.com/js/theming-in-essential-javascript-components).

* `react.js` and `react-dom.js` are the core files needed to create react elements.
* `browser.min.js` file is required for code transform.
* `ej.web.react.min.js`  is a react-syncfusion bridge to render Syncfusion components.


## Initialize and configure the control

Control can be initialized in two ways.

 * Using jsx Template
 * Without using jsx Template
 
## Using jsx Template

By using the jsx template, we can create the html file and jsx file. The `.jsx` file can be converted into `.js` file and it can be referred in html page.

Please refer to the code of HTML file.

{% highlight html %}

<div id="pdfviewercntl"></div>
<script src="app/pdfviewer/default.js"></script>

{% endhighlight %}

Initialize the PDF viewer by using the `EJ.PdfViewer` tag.

{% highlight html %}

    <!DOCTYPE html>
    <html>
        <head>
            <style>
                #PdfViewer {
                width: 100%;
                height: 550px;
                }
            </style>
        </head>
        <body>
            <div id="PdfViewer1" style="width:99%;"></div>
            <script type="text/babel">
		 var servicePath="http://js.syncfusion.com/ejservices/api/PdfViewer";
                 ReactDOM.render(
                     <EJ.PdfViewer id="PdfViewer" serviceUrl={servicePath}></EJ.PdfViewer>,
                     document.getElementById('PdfViewer1')
                );  
            </script>
        </body>
    </html>

{% endhighlight %}

Now, the PDF viewer control is rendered with default PDF document, which used in the services.

![](getting-started_images/pdfviewer.png)


## Without using jsx Template

PDF viewer can be created from a HTML `DIV` element with the HTML `id` attribute set to it. Refer to the following code example.

{% highlight html %}

    <body>
      <div id="pdfviewer1"></div>
    </body>

{% endhighlight %}

Initialize the PDF viewer control by adding the following script code to the body section of the HTML document.

{% highlight html %}

    <div id="pdfviewer1"></div>
    <script type="text/javascript">
	var service = "http://js.syncfusion.com/ejservices/api/PdfViewer";
        ReactDOM.render(
        React.createElement(EJ.PdfViewer,
            {
			 serviceUrl:service
            },
            document.getElementById('pdfviewer1')
        );        
    </script>

{% endhighlight %}

Now, the PDF viewer control will be rendered with the default PDF document, which is used in the service.

![](getting-started_images/pdfviewer.png)

