---
layout: post
title: Filtering with Grid widget for Syncfusion Essential ReactJS
description: How to enable filtering and its functionalities
platform: reactjs
control: Grid
documentation: ug
--- 
# Filtering

Filtering helps to view particular or related records from dataSource which meets a given filtering criteria. To enable filter, set `allowFiltering` as `true`. 

The Grid supports three types of filter, they are

1. Filter bar
2. Menu 
3. Excel

And also four types of filter menu is available in all filter types, they are

1. String 
2. Numeric 
3. Date 
4. Boolean

The corresponding filter menu is opened based on the column type.

N> 1. Need to specify the [`type`](http://help.syncfusion.com/api/js/ejgrid#members:columns-type "type") of column, when first record data value is empty or null otherwise the filter menu is not opened. 
N> 2. The default filter type is Filter bar, when `allowFiltering` is enabled and [`filtertype`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filtertype "filterType") is not set.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>      
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} allowFiltering={true}>
            <columns>
                <column field="OrderID" />
                <column field="EmployeeID" />
                <column field="CustomerID" />
                <column field="ShipCountry" />
                <column field="Freight" />
            </columns>   
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img1.png)


## Menu filter

You can enable menu filter by setting [`filterType`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filtertype "filterType") of [`filterSettings`] as `menu`. 

There is an option to show or hide the additional filter options in the menu by setting [`showPredicate`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-showpredicate "filterSettings.showPredicate") of [`filterSettings`] as `true` or `false` respectively.

N> For [`filterType`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filtertype "filterType") property you can assign either `string` value ("menu") or `enum` value (`ej.Grid.FilterType.Menu`).

We can also filter a specified range of values by using the `between` operator for the column type `number`, `date` and `datetime`.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
        var filterType = {filterType:"menu"};
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} allowFiltering={true} filterSettings={filterType}>
            <columns>
                <column field="OrderID" />
                <column field="EmployeeID" />
                <column field="CustomerID" />
                <column field="OrderDate" format="{0:MM/dd/yyyy}" />
                <column field="Verified" />
            </columns>   
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}


The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img2.png)
{:caption}
Numeric Filter

![](filtering_images/filtering_img3.png)
{:caption}
String Filter

![](filtering_images/filtering_img4.png)
{:caption}
Date Filter

![](filtering_images/filtering_img5.png)

Boolean Filter

## Excel-like filter

You can enable excel menu by setting of [`filterType`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filtertype "filterSettings.filterType") of [`filterSettings`] as `excel`. The excel menu contains an option such as Sorting, Clear filter, submenu for advanced filtering.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script> 
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
        var filterType = {filterType:"excel"};
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} allowFiltering={true} filterSettings={filterType}>
            <columns>
                <column field="OrderID" />
                <column field="EmployeeID" />
                <column field="CustomerID" />
                <column field="ShipCountry"/>
                <column field="Freight" />
            </columns>   
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img6.png)


### Checkbox list generation:

By default, the checkbox list is generated from distinct values of the filter column from dataSource which gives an option to search and select the required items.

Also on checkbox list generation, if the number of distinct values are greater than 1000, then the excel filter will display only first 1000 values to ensure the best performance on rendering and searching. However this limit has been customized according to your requirement by setting [`maxFilterChoices`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-maxfilterchoices "filterSettings.maxFilterChoices") of [`filterSettings`] with required limit in integer.

N> 1. Using excel filter events you can change the dataSource of the checkbox list. 
N> 2. [`ej.Query`](http://help.syncfusion.com/api/js/ejquery# "ej.Query") of checkbox list can also be changed using excel filter events.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
        var filterType = {filterType:"excel", maxFilterChoices : 4 };
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} allowFiltering={true} filterSettings={filterType}>
            <columns>
                <column field="OrderID" />
                <column field="EmployeeID" />
                <column field="CustomerID" />
                <column field="ShipCountry"/>
                <column field="Freight" />
            </columns>   
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img7.png)


### Add current selection to filter checkbox:

When filtering is done multiple times on the same column then the previously filtered values on the column will be cleared. So, to retain the old values `Add current selection to filter` checkbox can be used which is displayed when data is searched in the search bar.

The following image describes the above mentioned behavior.

![](filtering_images/filtering_img12.png)


### Case Sensitivity

To perform filter operation with case sensitive in excel styled filter menu mode by setting [`enableCaseSensitivity`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-enablecasesensitivity "enableCaseSensitivity") as `true`.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
        var filterType = {filterType: "excel", enableCaseSensitivity: true };
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} allowFiltering={true} filterSettings={filterType}>
            <columns>
                <column field="OrderID" />
                <column field="EmployeeID" />
                <column field="CustomerID" />
                <column field="ShipCountry"/>
                <column field="Freight" />
            </columns>   
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img8.png)


## Filter bar

[`Filterbar`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filtertype "Filter bar") row is located next to column header of grid. You can filter the records with different expressions depending upon the column type. To show the filter bar row, set the [`filterType`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filtertype "filterType") as `filterbar`.

List of Filter bar Expressions:

You can enter the below filter expressions manually in the filter bar.

 <table>
        <tr>
            <th>
                Expression
            </th>
            <th>
                Example
            </th>
            <th>
                Description
            </th>
            <th>
                Column Type
            </th>
        </tr>
        <tr>
            <td>
                =
            </td>
            <td>
                = value
            </td>
            <td>
                equal
            </td>
            <td rowspan="5">
                Numeric
            </td>
        </tr>
        <tr>
            <td>
                != 
            </td>
            <td>
                != value
            </td>
            <td>
                notequal
            </td>
           
        </tr>
        <tr>
            <td>
                >
            </td>
            <td>
                > value
            </td>
            <td>
                greaterthan
            </td>
          
        </tr>
        <tr>
            <td>
                <
            </td>
            <td>
                < value
            </td>
            <td>
                lessthan
            </td>
          
        </tr>
        <tr>
            <td>
                >=
            </td>
            <td>
                >= value
            </td>
            <td>
                greaterthanorequal
            </td>
           >
        </tr>
        <tr>
            <td>
                <=
            </td>
            <td>
                <= value
            </td>
            <td>
                lessthanorequal
            </td>
           
        </tr>
        <tr>
            <td>
                N/A
            </td>
            <td>
                N/A
            </td>
            <td>
                Always `startswith` operator will be used for string filter
            </td>
            <td>
                String
            </td>
        </tr>
        <tr>
            <td>
                N/A
            </td>
            <td>
                N/A
            </td>
            <td>
                Always `equal` operator will be used for Date filter 
            </td>
            <td>
                Date
            </td>
        </tr>
        <tr>
            <td>
                N/A
            </td>
            <td>
                N/A
            </td>
            <td>
                Always `equal` operator will be used for Boolean filter
            </td>
            <td>
                Boolean
            </td>
        </tr>
    </table>
	
	
The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}
   
Create a JSX file and paste the following content

{% highlight javascript %}
        var filterType = {filterType:"filterbar"};
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} allowFiltering={true} filterSettings={filterType}>
            <columns>
                <column field="OrderID" />
                <column field="EmployeeID" />
                <column field="CustomerID" />
                <column field="ShipCountry"/>
                <column field="Freight" />
            </columns>   
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img9.png)


Filter bar modes:

This specifies the grid to start the filter action while typing in the filter bar or after pressing the enter key based on [`filterBarMode`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filterbarmode "filterBarMode").There are two types of [`filterBarMode`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filterbarmode "filterBarMode"), they are

1. OnEnter
2. Immediate

N> For [`filterBarMode`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filterbarmode "filterBarMode") property you can assign either `string` value (onenter) or `enum` value (`ej.Grid.FilterBarMode.OnEnter`).

Filter bar message:

The filter bar message is supported only for the [`filterType`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filtertype "filterType") as filterbar. The filtered data with column name is displayed in the grid pager itself. By default [`showFilterBarStatus`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-showfilterbarmessage "showFilterBarMessage") is true.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
        var filterType = {showFilterBarStatus: true };
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} allowFiltering={true} filterSettings={filterType}>
            <columns>
                <column field="OrderID" />
                <column field="EmployeeID" />
                <column field="CustomerID" />
                <column field="ShipCountry"/>
                <column field="Freight" />
            </columns>   
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img10.png)


## Filter Operators

The grid controls uses filter operators from [`ej.DataManager`](http://help.syncfusion.com/api/js/ejdatamanager# "ej.DataManager"), which are used at the time of filtering.

List of Column type and Filter operators

<table>
        <tr>
            <th>
                Column Type
            </th>
            <th>
                Filter Operators
            </th>
        </tr>
        <tr>
            <td rowspan="6">
                Number
            </td>
            <td>
                ej.FilterOperators.greaterThan
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.greaterThanOrEqual
            </td>
        </tr>
        <tr>
       
            <td>
                ej.FilterOperators.lessThan
            </td>
        </tr>
        <tr>
            
            <td>
                ej.FilterOperators.lessThanOrEqual
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.equal
            </td>
        </tr>
        <tr>
            <td>
                ej.FilterOperators.notEqual
            </td>
        </tr>
        <tr>
            <td rowspan="5">
                String
            </td>
            <td>
                ej.FilterOperators.startsWith
            </td>
        </tr>
        <tr>
          
            <td>
                ej.FilterOperators.endsWith
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.contains
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.equal
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.notEqual
            </td>
        </tr>
        <tr>
            <td rowspan="2">
                Boolean
            </td>
            <td>
                ej.FilterOperators.equal
            </td>
        </tr>
        <tr>
            
            <td>
                ej.FilterOperators.notEqual
            </td>
        </tr>
        <tr>
            <td rowspan="6">
                Date
            </td>
            <td>
                ej.FilterOperators.greaterThan
            </td>
        </tr>
        <tr>
            
            <td>
                ej.FilterOperators.greaterThanOrEqual
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.lessThan
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.lessThanOrEqual
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.equal
            </td>
        </tr>
        <tr>
          
            <td>
                ej.FilterOperators.notEqual
            </td>
        </tr>
    </table>

## FilterBar Template

Usually enabling `allowFiltering`, will create default textbox in Grid FilterBar. So, Using [`filterBarTemplate`] property of `column` we can render any other controls like AutoComplete, DropDownList etc in filterbar to filter the grid data for the particular column.  
It has three functions. They are    

1. `create` - It is used to create the control at time of initialize.
2. `read`   - It is used to read the Filter value selected.
3. `write`  - It is used to render the control and assign the value selected for filtering.


The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight  %}

Create a JSX file and paste the following content

{% highlight javascript %}
        var filterFreight = {
            write: function (args) {
                args.element.ejNumericTextbox({ width: "100%", decimalPlaces: 2, focusOut: ej.proxy(args.column.filterBarTemplate.read, this, args) });
            },
            read: function (args) {
                this.filterColumn(args.column.field, "equal", args.element.val(), "and", true)
            }
        };
        var filtercustomer = {
            create: function (args) {
                return "<input>"
            },
            write: function (args) {
                var data = ej.DataManager(window.gridData).executeLocal(new ej.Query().select("CustomerID"));
                args.element.ejAutocomplete({ width: "100%", dataSource: data, enableDistinct: true, focusOut: ej.proxy(args.column.filterBarTemplate.read, this, args) });
            },
            read: function (args) {
                this.filterColumn(args.column.field, "equal", args.element.val(), "and", true)
            }
        };
        var filteremployee = {
            write: function (args) {
                var data = [{ text: "clear", value: "clear" }, { text: "1", value: 1 }, { text: "2", value: 2 }, { text: "3", value: 3 }, { text: "4", value: 4 },
                    { text: "5", value: 5 }, { text: "6", value: 6 }, { text: "7", value: 7 }, { text: "8", value: 8 }, { text: "9", value: 9 }
                ]
                args.element.ejDropDownList({ width: "100%", dataSource: data, change: ej.proxy(args.column.filterBarTemplate.read, this, args) })
            },
            read: function (args) {
                if (args.element.val() == "clear") {
                    this.clearFiltering(args.column.field);
                    args.element.val("")
                }
                this.filterColumn(args.column.field, "equal", args.element.val(), "and", true)
            }
        };
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} allowFiltering={true}>
            <columns>
                <column field="OrderID" headerText="Order ID" textAlign="right" width={90}/>
                <column field="CustomerID" headerText="CustomerID" textAlign="left" width={90} filterBarTemplate={filtercustomer} />
                <column field="EmployeeID" headerText="EmployeeID" textAlign="left" width={90} filterBarTemplate={filteremployee}  />
                <column field="Freight" headerText="Freight" textAlign="left" format="{0:C2}" width={90} filterBarTemplate={filterFreight}  />
                <column field="ShipCountry" headerText="Ship Country" textAlign="left" width={90} />
                 <column field="Verified" headerText="EmployeeID" width={90} />
            </columns>   
          </EJ.Grid>,
          document.getElementById('Grid')
        );

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img11.png)
{:caption}
After Filtering
 
