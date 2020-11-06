---
layout: post
title: Columns with Grid widget for Syncfusion Essential ReactJS
description: How to define the columns and its features
platform: reactjs
control: Grid
documentation: ug
--- 
# Columns

Column definitions are used as the [`dataSource`](http://help.syncfusion.com/api/js/ejgrid#members:datasource "dataSource") schema in Grid and it plays vital role in rendering column values in required format. Grid operations such as sorting, filtering, editing would be performed based on the column definitions. The [`field`](http://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") property of the [`columns`](http://help.syncfusion.com/api/js/ejgrid#members:columns "columns") is necessary to map the datasource values in Grid columns.

N> 1. If the column with [`field`](http://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") is not in the datasource, then the column values will be displayed as empty.
N> 2. If the [`field`](http://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") name contains "dot" operator then it is considered as complex binding.

## Column Template

HTML templates can be specified in the [`template`](http://help.syncfusion.com/api/js/ejgrid#members:columns-template "template") definition of the particular column as a string (HTML element) or ID of the template's HTML element.

N> If [`field`](http://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") is not specified, you will not able to perform editing, grouping, filtering, sorting, search and summary functionalities in particular column.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
		var pageSettings = {pageSize:4};

        ReactDOM.render(   
                //The datasource "window.employeeView" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.employeeView} allowPaging = {true} pageSettings={pageSettings}>
            <columns>
                <column headerText="Photo", template = "<img style='width: 75px; height: 70px' src='/13.2.0.29/themes/web/images/employees/{{"{{"}}:EmployeeID{{}}}}.png' alt='{{"{{"}}:EmployeeID{{}}}}' />" />
                <column field="EmployeeID" />
                <column field="FirstName" />
                <column field="LastName" />
                <column field="Country" />
            </columns>    
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img1.png)