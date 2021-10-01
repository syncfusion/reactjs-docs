---
layout: post
title: Getting Started with React JS ReportViewer Control | Syncfusion
description: Learn here about getting started with Syncfusion React JS ReportViewer Control, its elements, and more.
platform: ReactJS
control: ReportViewer
documentation: ug
---

# Getting Started with React JS ReportViewer

This section explains briefly about how to create a ReportViewer in React JS.

## Script and CSS Reference

Create a **HTML** page and add the script and CSS references in the order mentioned in the following code example.

{% highlight html %}

<!DOCTYPE html>
<html>
    <head>
        <!-- Essential Studio for JavaScript  theme reference -->
        <link rel="stylesheet" href="http://cdn.syncfusion.com/14.3.0.49/js/web/bootstrap-theme/ej.web.all.min.css" />           
        <!--  react script  -->
        <script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.2.1/react.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.2.1/react-dom.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.34/browser.min.js"></script>
        <!--  jquery script  -->
        <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
        <!-- Essential JS UI widget -->    
        <script src="http://cdn.syncfusion.com/14.3.0.49/js/web/ej.web.all.min.js"></script>
        <script src="http://cdn.syncfusion.com/14.3.0.49/js/common/ej.web.react.min.js"></script>

        <!--Add custom scripts here -->
    </head>
    <body>
    </body>
</html>

{% endhighlight %}

N> In the above code, `ej.web.all.min.js` script reference has been added for demonstration purpose. It is not recommended to use this for deployment purpose, as its file size is larger since it contains all the widgets. Instead, you can use [CSG](http://csg.syncfusion.com/# "") utility to generate a custom script file with the required widgets for deployment purpose.

* `react.js` and `react-dom.js` are the core files needed to create react elements.
* `browser.min.js` file is required for code transform.
* `ej.web.react.min.js`  is a react-syncfusion bridge to render Syncfusion components.

## Initialize and configure the control

Control can be initialized in two ways.

 * Using jsx Template
 * Without using jsx Template
 
### Using jsx Template

While making use of jsx template, we have to create both the html and jsx files. The `.jsx` file should be converted into `.js` file using [gulp](/reactjs/overview#converting-jsx-to-javascript-with-react) command and then needs to be added as a reference in the html page.
 
#### Control Initialization

Add a `div` container to render the ReportViewer.

{% highlight html %}

<!DOCTYPE html>
<html>    
     <body>
         <div id="groupingAggregate"></div>
         <script src="scripts/default.js"></script>
     </body>
</html>

{% endhighlight %}

Initialize the ReportViewer by using the ` EjReportViewer` tag.

{% highlight html %}

"use strict";
ReactDOM.render(  
    <EJ.ReportViewer
		id = "groupingReportViewer"
		reportServiceUrl = {'http://js.syncfusion.com/ejservices/api/ReportViewer'}
		processingMode = {"remote"}
		reportPath = {'GroupingAgg.rdl'}>
	</EJ.ReportViewer>,
	document.getElementById('groupingAggregate')
);

{% endhighlight %}

N> Default RDL Report will be rendered, which is used in the online service. You can obtain sample rdl/rdlc files from Syncfusion installed location (%userprofile%\AppData\Local\Syncfusion\EssentialStudio\{{ site.releaseversion }}\Common\Data\ejReportTemplate).

N> The above jsx template needs to be converted from `.jsx` to `.js` extension by using `gulp` nuget package (refer [here](/reactjs/overview#converting-jsx-to-javascript-with-react)) and then it must be referred in the html page.

#### Run the Application

Run the sample application and you can see the ReportViewer on the page as displayed in the following screenshot.

![Getting-Started_images1](Getting-Started_images/Getting-Started_img1.png) 

ReportViewer with Grouping Aggregate Report
{:.caption}

### Using without jsx Template

ReportViewer can be created from a HTML `DIV` element with the HTML `id` attribute set to it. Refer to the following code example.

{% highlight html %}

<body>
	<div id="groupingaggregate"></div>
</body>

{% endhighlight %}

Initialize the ReportViewer control by adding the following script code to the body section of the HTML document.

{% highlight html %}

    <div id="groupingaggregate"></div>
    <script type="text/javascript">
        ReactDOM.render(
        React.createElement(EJ.ReportViewer, {
            id: "groupingReportViewer",
            reportServiceUrl: 'http://js.syncfusion.com/ejservices/api/ReportViewer',
            processingMode: "remote",
            reportPath: 'GroupingAgg.rdl'
        }
        ),
        document.getElementById('groupingaggregate')
    );
    </script>

{% endhighlight %}

Run the application and you can see the ReportViewer on the page as displayed in the following screenshot.

![Getting-Started_images2](Getting-Started_images/Getting-Started_img1.png) 

ReportViewer with Grouping Aggregate Report
{:.caption}

## Load SSRS Server Reports

### Using jsx Template

ReportViewer supports to load RDL/RDLC files from SSRS Server. The following steps help you to load reports from SSRS Server.

Set the `reportPath` from SSRS and SSRS `reportServerUrl` in the ReportViewer properties.

{% highlight html %}

    "use strict";
    ReactDOM.render(
    <ej.reportviewer id="territoryReportViewer"
                     reportserviceurl={ 'http://js.syncfusion.com/ejservices/api/ReportViewer' }
                     reportserverurl={'http://mvc.syncfusion.com/reportserver'}
                     processingmode={"remote"}
                     reportpath={"/SSRSSamples2/Territory sales new"}>
    </ej.reportviewer>,
    document.getElementById('territorysales')
    );

{% endhighlight %}

Run the application and you can see the ReportViewer on the page as displayed in the following screenshot.

   ![Getting-Started_images3](Getting-Started_images/Getting-Started_img2.png) 
   
   Report from SSRS
   {:.caption}
   
### Using without jsx Template

ReportViewer can be created from a HTML `DIV` element with the HTML `id` attribute set to it. Refer to the following code example.

{% highlight html %}

<body>
	<div id="territorysales"></div>
</body>

{% endhighlight %}

Initialize the ReportViewer control by adding the following script code to the body section of the HTML document.

{% highlight html %}

    <div id="groupingaggregate"></div>
    <script type="text/javascript">
        ReactDOM.render(
        React.createElement(EJ.ReportViewer, {
            id: "territoryReportViewer",
            reportServiceUrl: 'http://js.syncfusion.com/ejservices/api/ReportViewer',
            reportServerUrl: 'http://mvc.syncfusion.com/reportserver', 
            processingMode: "remote",
            reportPath: '/SSRSSamples2/Territory Sales new'
        }
        ),
        document.getElementById('territorysales')
    );
    </script>

{% endhighlight %}

Run the application and you can see the ReportViewer on the page as displayed in the following screenshot.

   ![Getting-Started_images4](Getting-Started_images/Getting-Started_img2.png) 
   
   Report from SSRS
   {:.caption}   

## Load RDLC Reports

### Using jsx Template

The ReportViewer has data binding support to visualize the RDLC reports. The following code example helps you to bind data to ReportViewer.

Assign the RDLC report path to ReportViewer’s `reportPath` property and set the data sources to the ReportViewer’s `dataSources` property and specify the `processingMode` as local.

{% highlight html %}

    "use strict";
    ReactDOM.render(
    <ej.reportviewer id="areaReportViewer"
                     reportserviceurl={ 'http://js.syncfusion.com/ejservices/api/ReportViewer' }
                     processingmode={"local"}
                     reportpath={'AreaCharts.rdlc'}
                     datasources={[{value: [{ salespersonid 281, fullname 'Ito' , title 'Sales Representative' , salesterritory 'South West' , y2002 0, y2003 28000, y2004 3018725 },
                     { salespersonid 282, fullname 'Saraiva' , title 'Sales Representative' , salesterritory 'Canada' , y2002 25000, y2003 14000, y2004 3189356 },
                     { salespersonid 283, fullname 'Cambell' , title 'Sales Representative' , salesterritory 'North West' , y2002 12000, y2003 13000, y2004 1930885 },
                     { salespersonid 275, fullname 'Blythe' , title 'Sales Representative' , salesterritory 'North East' , y2002 19000, y2003 47000, y2004 4557045 },
                     { salespersonid 276, fullname 'Mitchell' , title 'Sales Representative' , salesterritory 'South West' , y2002 28000, y2003 46000, y2004 5240075 },
                     { salespersonid 277, fullname 'Carson' , title 'Sales Representative' , salesterritory 'Central' , y2002 33000, y2003 49000, y2004 3857163 },
                     { salespersonid 278, fullname 'Vargas' , title 'Sales Representative' , salesterritory 'Canada' , y2002 11000, y2003 14000, y2004 1764938 },
                     { salespersonid 279, fullname 'Reiter' , title 'Sales Representative' , salesterritory 'South East' , y2002 32000, y2003 26000, y2004 2811012 }],
                     name 'AdventureWorksXMLDataSet' }]}>
    </ej.reportviewer>,
    document.getElementById('areachart')
    );

{% endhighlight %}

> Default RDLC Report will be rendered, which is used in the online service.

Run the application and you can see the ReportViewer on the page as displayed in the following screenshot.

   ![Getting-Started_images5](Getting-Started_images/Getting-Started_img3.png) 
   
   Area Chart RDLC Report
   {:.caption}
   
### Using without jsx Template

ReportViewer can be created from a HTML `DIV` element with the HTML `id` attribute set to it. Refer to the following code example.

{% highlight html %}

<body>
	<div id="areachart"></div>
</body>

{% endhighlight %}

Initialize the ReportViewer control by adding the following script code to the body section of the HTML document.

{% highlight html %}

    <div id="areachart"></div>
    <script type="text/javascript">
       ReactDOM.render(
       React.createElement(EJ.ReportViewer, {
           id: "areaReportViewer",
           reportServiceUrl: 'http://js.syncfusion.com/ejservices/api/ReportViewer',
           processingMode: "local",
           reportPath: 'AreaCharts.rdlc',
           dataSources: [{
               value: [{ SalesPersonID: 281, FullName: 'Ito', Title: 'Sales Representative', SalesTerritory: 'South West', Y2002: 0, Y2003: 28000, Y2004: 3018725 },
               { SalesPersonID: 282, FullName: 'Saraiva', Title: 'Sales Representative', SalesTerritory: 'Canada', Y2002: 25000, Y2003: 14000, Y2004: 3189356 },
               { SalesPersonID: 283, FullName: 'Cambell', Title: 'Sales Representative', SalesTerritory: 'North West', Y2002: 12000, Y2003: 13000, Y2004: 1930885 },
               { SalesPersonID: 275, FullName: 'Blythe', Title: 'Sales Representative', SalesTerritory: 'North East', Y2002: 19000, Y2003: 47000, Y2004: 4557045 },
               { SalesPersonID: 276, FullName: 'Mitchell', Title: 'Sales Representative', SalesTerritory: 'South West', Y2002: 28000, Y2003: 46000, Y2004: 5240075 },
               { SalesPersonID: 277, FullName: 'Carson', Title: 'Sales Representative', SalesTerritory: 'Central', Y2002: 33000, Y2003: 49000, Y2004: 3857163 },
               { SalesPersonID: 278, FullName: 'Vargas', Title: 'Sales Representative', SalesTerritory: 'Canada', Y2002: 11000, Y2003: 14000, Y2004: 1764938 },
               { SalesPersonID: 279, FullName: 'Reiter', Title: 'Sales Representative', SalesTerritory: 'South East', Y2002: 32000, Y2003: 26000, Y2004: 2811012 }],
               name: 'AdventureWorksXMLDataSet'
           }]
       }
    ),
    document.getElementById('areachart')
    );
    </script>

{% endhighlight %}

Run the application and you can see the ReportViewer on the page as displayed in the following screenshot.

   ![Getting-Started_images6](Getting-Started_images/Getting-Started_img3.png) 
   
   Area Chart RDLC Report
   {:.caption}
  