---
title: Getting Started for React JS Grid
description: Getting-Started
platform: React JS
control: Grid
documentation: ug
keywords: 
---
# Getting started

##Preparing HTML document

The grid control has the following list of external JavaScript dependencies. 

* [jQuery](http://jquery.com/) 1.7.1 and later versions
* [jsRender](https://github.com/borismoore/jsrender) - to render the templates

Refer to the internal dependencies in the following table.

<table>
<tr>
<th>
File                          </th><th>
Description/Usage</th></tr>
<tr>
<td>
ej.core.min.js</td><td>
It is referred always before using all the JS controls.</td></tr>
<tr>
<td>
ej.data.min.js</td><td>
Used to handle data operation and is used while binding data to the JS controls.</td></tr>
<tr>
<td>
ej.touch.min.js</td><td>
Used to handle touch operations in touch-enabled devices</td></tr>
<tr>
<td>
ej.print.min.js</td><td>
Used to handle print operation in JS controls.</td></tr>
<tr>
<td>
ej.draggable.min.js</td><td>
Used for drag and drop an element in JS controls.</td></tr>
<tr>
<td>
ej.grid.min.js</td><td>
The grid's main file.</td></tr>
<tr>
<td>
ej.pager.min.js</td><td>
It is referred when paging is used in the Grid.  </td></tr>
<tr>
<td>
ej.scroller.min.js</td><td>
It is referred when scrolling is used in the Grid.  </td></tr>
<tr>
<td>
ej.waitingpopup.min.js</td><td>
It is referred when the remote databinding is used in the Grid. The waiting popup shows while requesting the server for data.</td></tr>
<tr>
<td>
ej.gridresize.min.js</td><td>
It is referred when resizing is used in the Grid.</td></tr>
<tr>
<td>
ej.dropdownlist.min.js</td><td rowspan = "8">
These files are used while enable the Editing and Filtering feature in the Grid.</td></tr>
<tr>
<td>
ej.dialog.min.js</td></tr>
<tr>
<td>
ej.button.min.js</td></tr>
<tr>
<td>
ej.autocomplete.min.js</td></tr>
<tr>
<td>
ej.datepicker.min.js</td></tr>
<tr>
<td>
ej.datetimepicker.min.js</td></tr>
<tr>
<td>
ej.timepicker.min.js</td></tr>
<tr>
<td>
ej.checkbox.min.js</td></tr>
<tr>
<td>
ej.editor.min.js</td></tr>
<tr>
<td>
ej.tooltip.js</td><td rowspan = "2">
It is referred when toolbar is enabled in Grid.</td></tr>
<tr>
<td>
ej.toolbar.min.js</td></tr>
<tr>
<td>
ej.menu.js</td><td>
It is referred when excel like filter menu or context menu is enabled.</td></tr>
<tr>
<td>
ej.radiobutton.js</td><td>
It is referred when filtering is enabled.</td></tr>
<tr>
<td>
ej.excelfilter.js</td><td>
It is referred when excel like filter menu is enabled.</td></tr>
<tr>
<td>
ej.globalize.min.js</td><td>
It is referred when using localization in Grid.</td></tr>
</table>


The required ReactJS script dependencies as follows. And you can also refer [React](https://facebook.github.io/react/docs/getting-started.html) to know more about react js.

* `react.min.js` - [http://cdn.syncfusion.com/js/assets/external/react.min.js](http://cdn.syncfusion.com/js/assets/external/react.min.js)
* `react-dom.min.js` - [http://cdn.syncfusion.com/js/assets/external/react-dom.min.js](http://cdn.syncfusion.com/js/assets/external/react-dom.min.js)
* `browser.min.js` - [http://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.34/browser.min.js](http://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.34/browser.min.js)
* `ej.web.react.min.js` - [http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.web.react.min.js](http://cdn.syncfusion.com/14.3.0.49/js/common/ej.web.react.min.js)


To get started, you can use the `ej.web.all.min.js` file that encapsulates all the `ej` controls and frameworks in one single file. So the complete boilerplate code is

{% highlight html %}

      <!DOCTYPE html>
      <html>
      <head>
          <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
          <meta name="description" content="Essential Studio for React JS"/>
          <meta name="author" content="Syncfusion"/>
          <title>Getting started for Grid React JS</title>
          <!-- Essential Studio for React JS  theme reference -->
          <link rel="stylesheet" href="http://cdn.syncfusion.com/13.2.0.29/js/web/flat-azure/ej.web.all.min.css" />

          <!-- Essential Studio for React JS  script references -->
          <script src="http://cdn.syncfusion.com/js/assets/external/react.min.js"></script>
          <script src="http://cdn.syncfusion.com/js/assets/external/react-dom.min.js"></script>
          <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.34/browser.min.js"></script>
          <script src="https://code.jquery.com/jquery-1.10.2.min.js"></script>
          <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
          <script src="http://cdn.syncfusion.com/13.2.0.29/js/web/ej.web.all.min.js"></script>
          <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.web.react.min.js"></script>

          <!-- Add your custom scripts here -->
     </head>
     <body>

     </body>
     </html>


{% endhighlight %}



N> In production, we highly recommend you to use our [custom script generator](http://helpjs.syncfusion.com/js/include-only-the-needed-widgets)  to create custom script file with required controls and its dependencies only. Also to reduce the file size further please use [GZip compression](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer?hl=en) in your server.

For themes, you can use the `ej.web.all.min.css` CDN link from the code example given. To add the themes in your application, please refer to [this link](http://help.syncfusion.com/js/theming-in-essential-javascript-components).

## Create a Grid

Control can be initialized in two ways.

 * Using jsx Template
 * Without using jsx Template
 
## Using jsx Template

By using the jsx template, we can create the html file and jsx file. The `.jsx` file can be convert to `.js` file and it can be referred in html page.

Please refer to the code of HTML file.

{% highlight html %}

       <div id="Grid-default"></div>
       <script type="text/babel" src="app.jsx">
       </script>

{% endhighlight %}


Create a JSX file and paste the following content

{% highlight js %}

        var shipDetails = [
          { Name: 'Hanari Carnes', City: 'Brazil' },
          { Name: 'Split Rail Beer & Ale', City: 'USA' },
          { Name: 'Ricardo Adocicados', City: 'Brazil' }
        ];
		ReactDOM.render(   
		  <EJ.Grid dataSource = {shipDetails} >
                    
          </EJ.Grid>,
          document.getElementById('Grid-default')
        );

{% endhighlight %}



![](Getting-started_images/Getting-started_img1.png)



## Data binding

[`Data binding`](http://helpjs.syncfusion.com/js/grid/data-binding) in the grid is achieved by assigning an array of JavaScript objects to the [`dataSource`](http://help.syncfusion.com/js/api/ejgrid#members:columns-datasource) property. Refer to the following code example.


Please refer to the code of HTML file.

{% highlight html %}

       <div id="Grid-default"></div>
       <script type="text/babel" src="app.jsx">
       </script>

{% endhighlight %}


Create a JSX file and paste the following content


{% highlight js %}
        var cols = ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"];
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} columns={cols}>
                    
          </EJ.Grid>,
          document.getElementById('Grid-default')
        );
   

{% endhighlight %}

![](Getting-started_images/Getting-started_img2.png)



N> ODataAdaptor is the default adaptor for the DataManager. On binding to other web services, proper [data adaptor](http://helpjs.syncfusion.com/js/datamanager/data-adaptors) needs to be set on `adaptor` option of the DataManager. 


## Enable Paging

[Paging](http://helpjs.syncfusion.com/js/grid/paging) can be enabled by setting the [`allowPaging`](http://help.syncfusion.com/js/api/ejgrid#members:allowpaging) to true.  This adds the pager in the bottom of the grid and page size can be customized by using the [`pageSettings.pageSize`](http://help.syncfusion.com/js/api/ejgrid#members:pagesettings-pagesize) property


Please refer to the code of HTML file.

{% highlight html %}

       <div id="Grid-default"></div>
       <script type="text/babel" src="app.jsx">
       </script>

{% endhighlight %}


Create a JSX file and paste the following content


{% highlight js %}

        var pageSettings = { pageSize: 8 };
        var cols = ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"];
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} columns={cols} allowPaging = {true} pageSettings={pageSettings} >
                    
          </EJ.Grid>,
          document.getElementById('Grid-default')
        );

{% endhighlight %}

N> Pager settings can be customized by using the [`pageSettings.pageSize`](http://help.syncfusion.com/js/api/ejgrid#members:pagesettings-pagesize) property. When it is not given the default values for `pageSize` and `pageCount` are 12 and 8 respectively.


![](Getting-started_images/Getting-started_img3.png)



## Enable Filtering

[`Filtering`](http://helpjs.syncfusion.com/js/grid/filter) can be enabled by setting the `allowFiltering` to `true`. By default, the filter bar row is displayed to perform filtering, you can change the filter type by using the [`filterSetting.filterType`](http://help.syncfusion.com/js/api/ejgrid#members:filtersettings) property.


Please refer to the code of HTML file.

{% highlight html %}

       <div id="Grid-default"></div>
       <script type="text/babel" src="app.jsx">
       </script>

{% endhighlight %}

Create a JSX file and paste the following content


{% highlight js %}

        var pageSettings = { pageSize: 8 };
        var cols = ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"];
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} columns={cols} allowPaging = {true} pageSettings={pageSettings} allowFiltering={true} >
                    
          </EJ.Grid>,
          document.getElementById('Grid-default')
        );
        
{% endhighlight %}

![](Getting-started_images/Getting-started_img4.png)



## Enable Grouping

[`Grouping`](http://helpjs.syncfusion.com/js/grid/grouping) can be enabled by setting the [`allowGrouping`](http://help.syncfusion.com/js/api/ejgrid#members:allowgrouping) to `true`.  Columns can be grouped dynamically by drag and drop the grid column header to the group drop area. The initial grouping can be done by adding required column names in the [`groupSettings.groupedColumns`](http://help.syncfusion.com/js/api/ejgrid#members:groupsettings-groupedcolumns) property. 


Please refer to the code of HTML file.

{% highlight html %}

       <div id="Grid-default"></div>
       <script type="text/babel" src="app.jsx">
       </script>

{% endhighlight %}


Create a JSX file and paste the following content

{% highlight js %}

        var pageSettings = { pageSize: 8 };
        var cols = ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"];
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} columns={cols} allowPaging = {true} pageSettings={pageSettings} allowGrouping={true} >
                    
          </EJ.Grid>,
          document.getElementById('Grid-default')
        );
        
        
{% endhighlight %}

![](Getting-started_images/Getting-started_img5.png)



Refer to the following code example for initial grouping.


Please refer to the code of HTML file.

{% highlight html %}

       <div id="Grid-default"></div>
       <script type="text/babel" src="app.jsx">
       </script>

{% endhighlight %}


Create a JSX file and paste the following content

{% highlight js %}

        var pageSettings = { pageSize: 8 };
        var groupSettings = { groupedColumns: ["ShipCountry", "CustomerID"] };
        var cols = ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"];
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} columns={cols} allowPaging = {true} pageSettings={pageSettings} allowGrouping={true} groupSettings={groupSettings} >
                    
          </EJ.Grid>,
          document.getElementById('Grid-default')
        );
       
        
{% endhighlight %}

![](Getting-started_images/Getting-started_img6.png)



## Add Summaries

[`Summaries`](http://helpjs.syncfusion.com/js/grid/summary) can be added by setting the [`showSummary`](http://help.syncfusion.com/js/api/ejgrid#members:showsummary) to true and adding required summary rows and columns in the [`summaryRows`](http://help.syncfusion.com/js/api/ejgrid#members:summaryrows) property. For demonstration, Stock column's sum value is displayed as summary.

{% highlight html %}

        var pageSettings = { pageSize: 8 };
        var groupSettings = { groupedColumns: ["CustomerID"] };
        var cols = ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"];
        var summaryRows = [
                 {
                  	title: "Sum",
                  	summaryColumns: [{ summaryType: ej.Grid.SummaryType.Sum, displayColumn: "Freight", dataMember: "Freight" }]
              	 }
        ];
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		    <EJ.Grid dataSource = {window.gridData} columns={cols} allowPaging = {true} pageSettings={pageSettings} allowGrouping={true} groupSettings={groupSettings} showSummary={true} summaryRows={summaryRows} >
                    
        </EJ.Grid>,
        document.getElementById('Grid-default')
        );
        
        
{% endhighlight %}

![](Getting-started_images/Getting-started_img7.png)
