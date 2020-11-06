---
layout: post
title: Getting Started for Essential JavaScript SunburstChart
description: How to create a SunburstChart.
platform: ts
control: SunburstChart
documentation: ug
---

# Getting Started

This section explains you the steps required to populate the Sunburst Chart with data, data labels, legend and title. This section covers only the minimal features that you need to know to get started with the Sunburst Chart.

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


### Create Sunburst Chart

You can easily create the Sunburst Chart widget by following  the below steps.

1.Create a <div> tag.
	
{% highlight html %}

<!DOCTYPE html>
    <html> 
        <body> 
            <div id="sunburst"></div>
                <script src="app/sunburstchart/default.js">
                </script>
        </body>
    </html>


{% endhighlight %}


2.Initialize the Sunburst chart by using the `EJ.SunburstChart` tag

{% highlight javascript %}

"use strict";
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1">                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);


{% endhighlight %}

## Populate Data source:
The datasource for the Sunburst Chart is populated as a JSON object. The “default_data” contains the JSON data for rendering the Sunburst Chart as shown in the sample.

{% highlight js %}

var default_data = [

{ Category: "Employees", Country: "USA", JobDescription: "Sales", JobGroup: "Executive", EmployeesCount: 50 },
{ Category: "Employees", Country: "USA", JobDescription: "Sales", JobGroup: "Analyst", EmployeesCount: 40 },
{ Category: "Employees", Country: "USA", JobDescription: "Marketing", EmployeesCount: 40 },
{ Category: "Employees", Country: "USA", JobDescription: "Technical", JobGroup: "Testers", EmployeesCount: 55 },
{ Category: "Employees", Country: "USA", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Windows", EmployeesCount: 175 },
{ Category: "Employees", Country: "USA", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Web", EmployeesCount: 70 },
{ Category: "Employees", Country: "USA", JobDescription: "Management", EmployeesCount: 40 },
{ Category: "Employees", Country: "USA", JobDescription: "Accounts", EmployeesCount: 60 },

{ Category: "Employees", Country: "India", JobDescription: "Technical", JobGroup: "Testers", EmployeesCount: 43 },
{ Category: "Employees", Country: "India", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Windows", EmployeesCount: 125 },
{ Category: "Employees", Country: "India", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Web", EmployeesCount: 60 },
{ Category: "Employees", Country: "India", JobDescription: "HR Executives", EmployeesCount: 70 },
{ Category: "Employees", Country: "India", JobDescription: "Accounts", EmployeesCount: 45 },

{ Category: "Employees", Country: "Germany", JobDescription: "Sales", JobGroup: "Executive", EmployeesCount: 30 },
{ Category: "Employees", Country: "Germany", JobDescription: "Sales", JobGroup: "Analyst", EmployeesCount: 40 },
{ Category: "Employees", Country: "Germany", JobDescription: "Marketing", EmployeesCount: 50 },
{ Category: "Employees", Country: "Germany", JobDescription: "Technical", JobGroup: "Testers", EmployeesCount: 40 },
{ Category: "Employees", Country: "Germany", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Windows", EmployeesCount: 65 },
{ Category: "Employees", Country: "Germany", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Web", EmployeesCount: 27 },
{ Category: "Employees", Country: "Germany", JobDescription: "Management", EmployeesCount: 33 },
{ Category: "Employees", Country: "Germany", JobDescription: "Accounts", EmployeesCount: 55 },

{ Category: "Employees", Country: "UK", JobDescription: "Technical", JobGroup: "Testers", EmployeesCount: 45 },
{ Category: "Employees", Country: "UK", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Windows", EmployeesCount: 96 },
{ Category: "Employees", Country: "UK", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Web", EmployeesCount: 55 },
{ Category: "Employees", Country: "UK", JobDescription: "HR Executives", EmployeesCount: 60 },
{ Category: "Employees", Country: "UK", JobDescription: "Accounts", EmployeesCount: 30 },

{ Category: "Employees", Country: "France", JobDescription: "Technical", JobGroup: "Testers", EmployeesCount: 40 },
{ Category: "Employees", Country: "France", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Windows", EmployeesCount: 65 },
{ Category: "Employees", Country: "France", JobDescription: "Technical", JobGroup: "Developers", JobRole: "Web", EmployeesCount: 27 },
{ Category: "Employees", Country: "France", JobDescription: "Marketing", EmployeesCount: 50 }

 ];

{% endhighlight %}

### Initialize Sunburst Chart with data

Now, bind the default_Datasource to [`datasource`](../api/ejsunburstchart#members:datasource) property of the Sunburst Chart. The[`levels`](../api/ejsunburstchart#members:levels) property determines the number of hierarchical levels. Each hierarchy level is formed based on the property specified in [`groupMemberPath`](../api/ejsunburstchart#members:groupMemeberPath) property, and each arc segment size is calculated using [`valueMemberPath`](../api/ejsunburstchart#members:valueMemberPath).

{% highlight js %}

"use strict"; 
 var levels=[
        {groupMemberPath: "Country" },
        {groupMemberPath: "JobDescription"},
        {groupMemberPath: "JobGroup"},
        {groupMemberPath: "JobRole" }
    ];
    
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1" valueMemberPath = "EmployeesCount"  
    dataSource = {default_data}    
    levels = {levels} ></EJ.SunburstChart>,
          document.getElementById('sunburst')
);

{% endhighlight %}


## Add Title to the Sunburst Chart

The title of the Sunburst chart is used to provide quick information to the user about the data being plotted in the Sunburst Chart. You can add it by using the [`text`](../api/ejsunburstchart#members:title-text) property of the [`title`](../api/ejsunburstchart#members:title) 

{% highlight js %}

"use strict";
 var title = { text:'Employees Count'};
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"
     title = {title}></EJ.SunburstChart>,
          document.getElementById('sunburst')
);


{% endhighlight %}

## Enable Legend

You can enable or disable the legend by using the [`visible`](../api/ejsunburstchart#members:legend-visible) property present inside the [`legend`](../api/ejsunburstchart#members:legend)

{% highlight js %}

"use strict";
 var legend = { visible:true, position: "left" }; 
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"     
    legend = {legend}></EJ.SunburstChart>,
          document.getElementById('sunburst')
);


{% endhighlight %}

## Add Data Labels

The data labels are used to improve the readability of the Sunburst chart. This can be achieved by enabling the [`visible`](../api/ejsunburstchart#members:datalabelsettings-visible) property in the [`datalabelSettings`](../api/ejsunburstchart#members:datalabelsettings).

{% highlight js %}

"use strict";
var datalabelSettings = { visible:true};
ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"     
     datalabelSettings = {datalabelSettings}></EJ.SunburstChart>,
          document.getElementById('sunburst')
);

{% endhighlight %}

Now the Sunburst Chart is rendered along with the specified customizations

![](/js/SunburstChart/Getting-Started_images/Getting-Started_img1.png)

[Click](http://js.syncfusion.com/demos/web/#!/bootstrap/sunburst/deafult) here to view the default sample of the SunburstChart 
