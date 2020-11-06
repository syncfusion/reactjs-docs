---
layout: post
title: Editing with Grid widget for Syncfusion Essential ReactJS
description: How to perform editing and configure edit time functionalities like edit type, edit time controls etc
platform: reactjs
control: Grid
documentation: ug
--- 
# Editing

The grid control has support for dynamic insertion, updating and deletion of records. You can start the edit action either by double clicking the particular row or by selecting the required row and clicking on Edit icon in toolbar. Similarly, you can add new record to grid either by clicking on insert icon in toolbar or on an external button which is bound to call [`addRecord`](http://help.syncfusion.com/api/js/ejgrid#methods:addrecord "addRecord") method of grid.  `Save` and `Cancel` while on edit mode is possible using respective toolbar icon in grid.

Deletion of the record is possible by selecting the required row and clicking on Delete icon in toolbar. 

The primary key for the data source should be defined in [`columns`](http://help.syncfusion.com/api/js/ejgrid#members:columns "columns") property, for editing to work properly. In [`e-columns`](http://help.syncfusion.com/api/js/ejgrid#members:columns "columns") property, particular primary column's [`isPrimaryKey`](http://help.syncfusion.com/api/js/ejgrid#members:columns-isprimarykey "isPrimaryKey") property should be set to `true`. Refer the Knowledge base [link](http://www.syncfusion.com/kb/2675/cant-edit-any-row-except-the-first-row-in-grid# "link") for more information.

N> 1. In grid, the primary key column will be automatically set to read only while editing the row, but you can specify primary key column value while adding a new record.
N> 2. The column which is specified as [`isIdentity`](http://help.syncfusion.com/api/js/ejgrid#members:columns-isidentity "isIdentity") will be in readonly mode both while editing and adding a record. Also, auto incremented value is assigned to that [`isIdentity`](http://help.syncfusion.com/api/js/ejgrid#members:columns-isidentity "isIdentity") column.

## Toolbar with edit option

Using toolbar which is rendered at the top of the grid header, you can show all the CRUD related action. To enable toolbar and toolbar items, set [`showToolbar`](http://help.syncfusion.com/api/js/ejgrid#members:toolbarsettings-showtoolbar "showToolbar") property as true and [`toolbarItems`](http://help.syncfusion.com/api/js/ejgrid#members:toolbarsettings-toolbaritems "toolbarItems"). The default toolbar items are `Add`, `Edit`, `Delete`, `Update` and `Cancel`.

N> For [`toolbarItems`](http://help.syncfusion.com/api/js/ejgrid#members:toolbarsettings-toolbaritems "toolbarItems") property you can assign either `string` value ("add") or `enum` value (`ej.Grid.ToolBarItems.Add`).

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
		var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true };
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   

        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="EmployeeID" />
                <column field="ShipCity" />
                <column field="ShipCountry" />
            </columns>    
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img1.png)


## Cell edit type and its params

The edit type of bound column can be customized using [`editType`](http://help.syncfusion.com/api/js/ejgrid#members:columns-edittype "editType") property of [`columns`](http://help.syncfusion.com/api/js/ejgrid#members:columns "columns"). The following Essential JavaScript controls are supported built-in by [`editType`](http://help.syncfusion.com/api/js/ejgrid#members:columns-edittype "editType"). You can set the [`editType`](http://help.syncfusion.com/api/js/ejgrid#members:columns-edittype "editType") based on specific data type of the column. 

* [`CheckBox`](http://help.syncfusion.com/api/js/ejcheckbox# "CheckBox") control for boolean data type.
* [`NumericTextBox`](http://help.syncfusion.com/api/js/ejtextboxes# "NumericTextBox") control for integers, double, and decimal data types.
* [`InputTextBox`] control for string data type.
* [`DatePicker`](http://help.syncfusion.com/api/js/ejdatepicker# "DatePicker") control for date data type.
* [`DateTimePicker`](http://help.syncfusion.com/api/js/ejdatetimepicker# "DateTimePicker") control for date-time data type.
* [`DropDownList`](http://help.syncfusion.com/api/js/ejdropdownlist# "DropDownList") control for list of data type.



And also you can define the model for all the editTypes controls while editing through [`editParams`](http://help.syncfusion.com/api/js/ejgrid#members:columns-editparams "editParams") property of [`columns`](http://help.syncfusion.com/api/js/ejgrid#members:columns "columns").

The following table describes [`editType`](http://help.syncfusion.com/api/js/ejgrid#members:columns-edittype "editType") and their corresponding [`editParams`](http://help.syncfusion.com/api/js/ejgrid#members:columns-editparams "editParams") of the specific data type of the column.

<table>
<tr>
<th>
EditType</th><th>
EditParams</th><th>
Example</th></tr>
<tr>
<td>
CheckBox</td><td>
{{ '[ejCheckBox](http://help.syncfusion.com/api/js/ejcheckbox)' | markdownify }} </td><td>
editParams: { checked: true }</td></tr>
<tr>
<td>
NumericTextBox </td><td>
{{ '[ejTextBoxes](http://help.syncfusion.com/api/js/ejtextboxes)' | markdownify }} </td><td>
editParams: { decimalPlaces: 2, value:5  }</td></tr>
<tr>
<td>
InputTextBox </td><td>
-</td><td>
-</td></tr>
<tr>
<td>
DatePicker </td><td>
{{ '[ejDatePicker](http://help.syncfusion.com/api/js/ejdatepicker)' | markdownify }} </td><td>
editParams: {  buttonText : "Now" }</td></tr>
<tr>
<td>
DateTimePicker</td><td>
{{ '[ejDateTimePicker](http://help.syncfusion.com/api/js/ejdatetimepicker)' | markdownify }} </td><td>
editParams: {  enabled: true }</td></tr>
<tr>
<td>
DropDownList</td><td>
{{ '[ejDropDownList](http://help.syncfusion.com/api/js/ejdropdownlist)' | markdownify }} </td><td>
editParams: {  allowGrouping: true }</td></tr>

</table>

N> 1. If [`editType`](http://help.syncfusion.com/api/js/ejgrid#members:columns-edittype "editType") is not set, then by default it will display the input element ("stringedit") while editing a column.
N> 2. For [`editType`](http://help.syncfusion.com/api/js/ejgrid#members:columns-edittype "editType") property you can assign either `string` value ("numericedit") or `enum` value (`ej.Grid.EditingType.Numeric`).

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

{% highlight javascript %}
		var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true };
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   
		var decimalPlaces = {decimalPlaces:3};
		var enableAnimation = {enableAnimation:true};
		var showRoundedCorner = {showRoundedCorner:true};
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" editType="stringedit" />
                <column field="Freight" editType="numericedit" editParams={decimalPlaces} />
                <column field="ShipCity" editType="dropdownedit" editParams={enableAnimation} />
                <column field="ShipCountry" />
                <column field="OrderDate" editType="datepicket" format="{0:MM/dd/yyyy}" />
                <column field="Verified" editType="booleanedit" editParams={showRoundedCorner} />
            </columns>  
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img2.png)


## Cell Edit Template

On editing the column values, custom editor can be created by using [`editTemplate`](http://help.syncfusion.com/api/js/ejgrid#members:columns-edittemplate "editTemplate") property of [`columns`](http://help.syncfusion.com/api/js/ejgrid#members:columns "columns"). It has three functions, they are

1. `create` - It is used to create the control at time of initialize.
2. `read` - It is used to read the input value at time of save.
3. `write` - It is used to assign the value to control at time of editing.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
        var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true };
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   
        var postalEditTemplate = {
            create : function () {
                    return "<input>";
            },
            read : function (args) {
                return args.ejMaskEdit("get_UnstrippedValue");
            },
            write : function (args) {
                args.element.ejMaskEdit({
                maskFormat : "99-99-9999",
                value : args.rowdata["ShipPostalCode"]
                });
            }
        };
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="EmployeeID" />
                <column field="Freight" />
                <column field="ShipCountry" />
                <column field="ShipPostalCode" editTemplate={postalEditTemplate} />
            </columns>  
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img3.png)


## Edit Modes

### Inline 

Set [`editMode`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-editmode "editMode") as `normal`, then the row itself is changed as edited row.

N> For [`editMode`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-editmode "editMode") property you can assign either `string` value ("normal") or `enum` value (`ej.Grid.EditMode.Normal`).

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
        var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true, editMode:"normal" };
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   

        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="Freight" editType="numericedit" />
                <column field="ShipCountry" editType="dropdownedit"/>
                <column field="OrderDate" editType="datepicker" format="{0:MM/dd/yyyy}"/>
            </columns>  
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img4.png)


### Inline Form

Set [`editMode`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-editmode "editMode") as `inlineform`, then edit form will be inserted next to the row which is to be edited.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
        var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true, editMode:"inlineform" };
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   

        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="Freight" editType="numericedit" />
                <column field="ShipCountry" editType="dropdownedit"/>
                <column field="OrderDate" editType="datepicker" format="{0:MM/dd/yyyy}"/>
            </columns>  
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img5.png)


### Inline Template Form

You can edit any of the fields pertaining to a single record of data and apply it to a template so that the same format is applied to all the other records that you may edit later.

Using this template support, you can edit the fields that are not bound to grid columns.

To edit the records using Inline template form, set [`editMode`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-editmode "editMode")as `inlineformtemplate` and specify the template ID to [`inlineFormTemplateID`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-inlineformtemplateid "editSettings.inlineFormTemplateID") of [`editSettings`] property.

While using template form, you can change the HTML elements to appropriate JS controls based on the column type. This can be achieved by using [`actionComplete`](http://help.syncfusion.com/api/js/ejgrid#events:actioncomplete "actionComplete") event of grid.

N> 1. `value` attribute is used to bind the corresponding field value while editing.
N> 2. `name` attribute is used to get the changed field values while saving the edited record.
N> 4.  For [`editMode`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-editmode "editMode") property you can assign either `string` value ("inlineformtemplate") or `enum` value (`ej.Grid.EditMode.InlineTemplateForm`) 

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>

   <script id="template" type="text/x-jsrender">
        <table cellspacing="10">
            <tr>
                <td>Order ID</td>
                <td>
                    <input id="OrderID" name="OrderID" disabled="disabled" ngModel="{{"{{"}}:OrderID{{}}}}" value="{{"{{"}}:OrderID{{}}}}"/>
                </td>
                <td>Customer ID</td>
                <td>
                    <input id="CustomerID" name="CustomerID" ngModel="{{"{{"}}:CustomerID{{}}}}" value="{{"{{"}}:CustomerID{{}}}}" class="e-field e-ejinputtext" style="width: 116px; height: 28px" />
                </td>
            </tr>
            <tr>
                <td>Employee ID</td>
                <td>
                    <input type="text" id="EmployeeID" name="EmployeeID" ngModel="{{"{{"}}:EmployeeID{{}}}}" value="{{"{{"}}:EmployeeID{{}}}}"/>
                </td>
                <td>Ship City</td>
                <td>
                    <select id="ShipCity" name="ShipCity">
                        <option value="Argentina">Argentina</option>
                        <option value="Austria">Austria</option>
                        <option value="Belgium">Belgium</option>
                        <option value="Brazil">Brazil</option>
                        <option value="Canada">Canada</option>
                        <option value="Denmark">Denmark</option>
                    </select>
                </td>
            </tr>
        </table>
    </script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
        var EditGrid = React.createClass({
		actionComplete: function(e){
            $("#EmployeeID").ejNumericTextbox();
            $("#Freight").ejNumericTextbox();
            $("#ShipCity").ejDropDownList();
        },
		editSettings: { allowEditing: true, allowAdding: true, allowDeleting: true, editMode: "inlineformtemplate", inlineFormTemplateID: "#template" },
        toolbarItems: { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] },
		render: function () {
            return (   
			 //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={this.editSettings} toolbarSettings={this.toolbarItems} actionComplete={this.actionComplete}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="ShipCity" />
            </columns>    
          </EJ.Grid>
			);
			}
		});
		
		ReactDOM.render(<EditGrid />, document.getElementById('Grid'));

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img6.png)

{:caption}
Before the template elements are converted to JS controls


![](Editing_images/Editing_img7.png)
{:caption}
After the template elements are converted to JS controls using actionComplete event 


### Dialog

Set [`editMode`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-editmode "editMode") as `dialog` to edit data using a dialog box, which displays the fields associated with the data record being edited.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
        var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true, editMode: "dialog" };
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   

        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="Freight" editType="numericedit" />
                <column field="ShipCountry" editType="dropdownedit"/>
                <column field="OrderDate" editType="datepicker" format="{0:MM/dd/yyyy}"/>
            </columns>  
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img8.png)


### Dialog Template Form

You can edit any of the fields pertaining to a single record of data and apply it to a template so that the same format is applied to all the other records that you may edit later.

Using this template support, you can edit the fields that are not bound to grid columns.

To edit the records using Inline template form, set [`editMode`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-editmode "editMode") as dialogtemplate and specify the template id to [`dialogEditorTemplateID`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-dialogeditortemplateid "dialogEditorTemplateID") property of [`editSettings`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings "editSettings").

While using template, you can change the elements that are defined in the `template`, to appropriate JS controls based on the column type. This can be achieved by using [`actionComplete`](http://help.syncfusion.com/api/js/ejgrid#events:actioncomplete "actionComplete") event of grid.

N> 1. `value` attribute is used to bind the corresponding field value while editing.
N> 2. `name` attribute is used to get the changed field values while save the edited record. 
N> 3. For [`editMode`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-editmode "editMode") property you can assign either `string` value ("dialogtemplate") or `enum` value (`ej.Grid.EditMode.DialogTemplate`).

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>

 <script id="template" type="text/x-jsrender">
        <table cellspacing="10">
            <tr>
                <td>Order ID</td>
                <td>
                    <input id="OrderID" name="OrderID" disabled="disabled" ngModel="{{"{{"}}:OrderID{{}}}}" value="{{"{{"}}:OrderID{{}}}}"/>
                </td>
                <td>Customer ID</td>
                <td>
                    <input id="CustomerID" name="CustomerID" ngModel="{{"{{"}}:CustomerID{{}}}}" value="{{"{{"}}:CustomerID{{}}}}" class="e-field e-ejinputtext" style="width: 116px; height: 28px" />
                </td>
            </tr>
            <tr>
                <td>Employee ID</td>
                <td>
                    <input type="text" id="EmployeeID" name="EmployeeID" ngModel="{{"{{"}}:EmployeeID{{}}}}" value="{{"{{"}}:EmployeeID{{}}}}"/>
                </td>
                <td>Ship City</td>
                <td>
                    <select id="ShipCity" name="ShipCity">
                        <option value="Argentina">Argentina</option>
                        <option value="Austria">Austria</option>
                        <option value="Belgium">Belgium</option>
                        <option value="Brazil">Brazil</option>
                        <option value="Canada">Canada</option>
                        <option value="Denmark">Denmark</option>
                    </select>
                </td>
            </tr>
        </table>
    </script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
var EditGrid = React.createClass({
		 actionComplete: function(e){
            $("#EmployeeID").ejNumericTextbox();
            $("#Freight").ejNumericTextbox();
            $("#ShipCity").ejDropDownList();
        },
		editSettings: { allowEditing: true, allowAdding: true, allowDeleting: true, editMode: "dialogtemplate", dialogEditorTemplateID: "#template"  },
        toolbarItems: { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] },
		render: function () {
            return (   
			 //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={this.editSettings} toolbarSettings={this.toolbarItems} actionComplete={this.actionComplete}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="ShipCity" />
            </columns>    
          </EJ.Grid>
			);
			}
		});
		
		ReactDOM.render(<EditGrid />, document.getElementById('Grid')); 
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img9.png)
{:caption}
Before the template elements are converted to JS controls

![](Editing_images/Editing_img10.png)
{:caption}
After the template elements are converted to JS controls using actionComplete event 

### External Form

By setting the [`editMode`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-editmode "editMode") as externalform, the edit form is opened outside the grid content.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
        var pageSettings = {pageSize:7};
		var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true, editMode:"externalform"}
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   

        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems} pageSettings={pageSettings}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="Freight" editType="numericedit" />
                <column field="ShipCountry" editType="dropdownedit"/>
                <column field="OrderDate" editType="datepicker" format="{0:MM/dd/yyyy}"/>
            </columns>  
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img11.png)


Form Position:

You can position an external edit form in the following two ways. 

1. Top-right
2. Bottom left

This can be achieved by setting the [`formPosition`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-formposition "formPosition") property of [`editSettings`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings "editSettings") as "topright" or "bottomleft".

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
        var pageSettings = {pageSize:7};
        var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true, editMode:"externalform", formPosition:"topRight"};
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   

        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems} pageSettings={pageSettings}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="Freight" editType="numericedit" />
                <column field="ShipCountry" editType="dropdownedit"/>
            </columns>  
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img12.png)


### External Template Form

You can edit any of the fields pertaining to a single record of data and apply it to a template so that the same format is applied to all the other records that you may edit later.

Using this template support, you can edit the fields that are not bound to grid columns.

To edit the records using External template form, set [`editMode`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-editmode "editMode") as externalformtemplate and specify the template id to [`externalFormTemplateID`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-externalformtemplateid "externalFormTemplateID") property of [`e-edit-settings`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings "editSettings").

While using template, you can change the elements that are defined in the template, to appropriate JS controls based on the column type. This can be achieved by using [`actionComplete`](http://help.syncfusion.com/api/js/ejgrid#events:actioncomplete "actionComplete") event of grid.

N> 1. `value` attribute is used to bind the corresponding field value while editing. 
N> 2. `name` attribute is used to get the changed field values while save the edited record. 
N> 3. For [`editMode`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-editmode "editMode") property you can assign either `string` value ("externalformtemplate") or `enum` value (`ej.Grid.EditMode.ExternalFormTemplate`).

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>

 <script id="template" type="text/x-jsrender">
        <table cellspacing="10">
            <tr>
                <td>Order ID</td>
                <td>
                    <input id="OrderID" name="OrderID" disabled="disabled" ngModel="{{"{{"}}:OrderID{{}}}}" value="{{"{{"}}:OrderID{{}}}}"/>
                </td>
                <td>Customer ID</td>
                <td>
                    <input id="CustomerID" name="CustomerID" ngModel="{{"{{"}}:CustomerID{{}}}}" value="{{"{{"}}:CustomerID{{}}}}" class="e-field e-ejinputtext" style="width: 116px; height: 28px" />
                </td>
            </tr>
            <tr>
                <td>Employee ID</td>
                <td>
                    <input type="text" id="EmployeeID" name="EmployeeID" ngModel="{{"{{"}}:EmployeeID{{}}}}" value="{{"{{"}}:EmployeeID{{}}}}"/>
                </td>
                <td>Ship City</td>
                <td>
                    <select id="ShipCity" name="ShipCity">
                        <option value="Argentina">Argentina</option>
                        <option value="Austria">Austria</option>
                        <option value="Belgium">Belgium</option>
                        <option value="Brazil">Brazil</option>
                        <option value="Canada">Canada</option>
                        <option value="Denmark">Denmark</option>
                    </select>
                </td>
            </tr>
        </table>
    </script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
var EditGrid = React.createClass({
		 actionComplete: function(e){
            $("#EmployeeID").ejNumericTextbox();
            $("#Freight").ejNumericTextbox();
            $("#ShipCity").ejDropDownList();
        },
        pageSettings = {pageSize:5},
		editSettings: { allowEditing: true, allowAdding: true, allowDeleting: true, editMode: "externalformtemplate", externalFormTemplateID: "#template"  },
        toolbarItems: { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] },
		render: function () {
            return (   
			 //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={this.editSettings} toolbarSettings={this.toolbarItems} actionComplete={this.actionComplete}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="ShipCity" />
            </columns>    
          </EJ.Grid>
			);
		}
});
		
		ReactDOM.render(<EditGrid />, document.getElementById('Grid'));

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img13.png)
{:caption}
Before the template elements are converted to JS controls

![](Editing_images/Editing_img14.png)
{:caption}
After the template elements are converted to JS controls using actionComplete event

### Batch / Excel-like

Users can start editing by clicking a cell and typing data into it. Edited cell will be marked while navigating to next cell or any other row, so that you know which fields or cells has been edited. Set [`editMode`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-editmode "editMode") as `batch` to enable batch editing.

N> `getBatchChanges` method of grid holds the unsaved record changes.
N> Refer the KB [link](http://www.syncfusion.com/kb/3016/how-to-suppress-grid-confirmation-messages# "link") for "How to suppress grid confirmation messages" in batch mode.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
<div ng-controller="BatchCtrl">
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
		var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true, editMode:"batch" };
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   

        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="Freight" editType="numericedit" />
                <column field="ShipCountry" editType="dropdownedit"/>
                <column field="OrderDate" editType="datepicker" format="{0:MM/dd/yyyy}"/>
            </columns>  
          </EJ.Grid>,
          document.getElementById('Grid')
        );

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img15.png)


## Confirmation messages

To show the confirm dialog while saving or discarding the batch changes (discarding during the grid action like filtering, sorting and paging), set [`showConfirmDialog`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-showconfirmdialog "showConfirmDialog") as `true`.

N> [`showConfirmDialog`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-showconfirmdialog "showConfirmDialog") property is only for batch editing mode.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
		var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true, editMode:"batch",showConfirmDialog:true };
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   

        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="Freight" editType="numericedit" />
                <column field="ShipCountry" editType="dropdownedit"/>
                <column field="OrderDate" editType="datepicker" format="{0:MM/dd/yyyy}"/>
            </columns>  
          </EJ.Grid>,
          document.getElementById('Grid')
        );

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img16.png)


To show delete confirm dialog while deleting a record, set [`showDeleteConfirmDialog`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-showdeleteconfirmdialog "showDeleteConfirmDialog") as true.

N> [`showDeleteConfirmDialog`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-showdeleteconfirmdialog "showDeleteConfirmDialog") property is for all type of [`editMode`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-editmode "editMode").

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
		var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true, showDeleteConfirmDialog:true };
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   

        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="Freight" editType="numericedit" />
                <column field="ShipCountry" editType="dropdownedit"/>
                <column field="OrderDate" editType="datepicker" format="{0:MM/dd/yyyy}"/>
            </columns>  
          </EJ.Grid>,
          document.getElementById('Grid')
        );

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img17.png)


## Column Validation

We can validate the value of the added or edited record cell before saving.

The below validation script files are needed when editing is enabled with validation.

1. jquery.validate.min.js
2. jquery.validate.unobtrusive.min.js
 
 
### jQuery Validation


You can set validation rules using [`validationRules`](http://help.syncfusion.com/api/js/ejgrid#members:columns-validationrules "validationRules") property of [`columns`](http://help.syncfusion.com/api/js/ejgrid#members:columns "columns"). The following are jQuery validation methods.

__List__ __of__ __Jquery__ __validation__ __methods__

<table>
<tr>
<th>
Rules</th><th>
Description</th></tr>
<tr>
<td>
required</td><td>
Requires an element.</td></tr>
<tr>
<td>
remote</td><td>
Requests a resource to check the element for validity.</td></tr>
<tr>
<td>
minlength</td><td>
Requires the element to be of given minimum length.</td></tr>
<tr>
<td>
maxlength</td><td>
Requires the element to be of given maximum length.</td></tr>
<tr>
<td>
range</td><td>
Requires the element to be in given value range.</td></tr>
<tr>
<td>
min</td><td>
The element requires a given minimum.</td></tr>
<tr>
<td>
max</td><td>
The element requires a given maximum.</td></tr>
<tr>
<td>
range</td><td>
Requires the element to be in a given value range.</td></tr>
<tr>
<td>
email</td><td>
The element requires a valid email.</td></tr>
<tr>
<td>
url</td><td>
The element requires a valid URL</td></tr>
<tr>
<td>
date</td><td>
Requires the element to be a date.</td></tr>
<tr>
<td>
dateISO</td><td>
The element requires an ISO date.</td></tr>
<tr>
<td>
number</td><td>
The element requires a decimal number.</td></tr>
<tr>
<td>
digits</td><td>
The element requires digits only.</td></tr>
<tr>
<td>
creditcard</td><td>
Requires the element to be a credit card number.</td></tr>
<tr>
<td>
equalTo</td><td>
Requires the element to be the same as another.</td></tr>
</table>

Grid supports all the standard validation methods of jQuery, please refer the jQuery validation documentation [link](http://jqueryvalidation.org/documentation/# "link") for more information.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
		var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true,showDeleteConfirmDialog:true};
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   
        var requireValid = {required: true};
        var lengthValid = {minlength:3};
        var rangeValid = {range:[0, 1000]};
        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} validationRules={requireValid} />
                <column field="CustomerID" validationRules={lengthValid}/>
                <column field="ShipCity" />
                <column field="Freight" editType="numericedit" validationRules={rangeValid}/>
                <column field="ShipCountry" />
            </columns>  
          </EJ.Grid>,
          document.getElementById('Grid')
        );

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img18.png)


## Persisting data in Server

Edited data can be persisted in database using RESTful web services. 

All the CRUD operations in grid are done through DataManager. DataManager have an option to bind all the CRUD related data in server side. Please refer the ['link'](http://help.syncfusion.com/js/datamanager/overview# "link") to know about the DataManager.

For you information ODataAdaptor persist data in server as per OData protocol.

In the below section, we have explained how to get the edited data details at the server side using URLAdaptor. 

### URL Adaptor

You can use the `UrlAdaptor` of [`ejDataManger`](http://help.syncfusion.com/api/js/ejdatamanager# "ejDataManger") when binding datasource from remote data. At initial load of Grid, using URL property of DataManager, data are fetched from remote data and bound to Grid. You can map CRUD operation in Grid to Server-Side Controller action using the properties `insertUrl`, `removeUrl`, `updateUrl`, `crudUrl` and `batchUrl`.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
        var data = ej.DataManager({
          url: "/Home/DataSource",
          adaptor: "UrlAdaptor",
          updateUrl : "/Home/Update",
	      insertUrl : "/Home/Insert",
		  removeUrl : "/Home/Delete",
        });
		var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true,showDeleteConfirmDialog:true};
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   

        ReactDOM.render(   
		  <EJ.Grid dataSource = {data} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="EmployeeID" />
                <column field="Freight" editType="numericedit" format="{0:C}" />
                <column field="ShipName" />
                <column field="ShipCountry" />
            </columns>  
          </EJ.Grid>,
          document.getElementById('Grid')
        );

{% endhighlight %}

Also when you use `UrlAdaptor`, you need to return the data as `JSON` and the JSON object must contain a property as `result` with dataSource as its value and one more property `count` with the dataSource total records count as its value.

The following code example describes the above behavior.

{% highlight cs %}
public ActionResult DataSource(DataManager data)
{
	IEnumerable DataSource = OrderRepository.GetAllRecords();
	DataResult result = new DataResult();
	DataOperations operation = new DataOperations();
	result.result = DataSource;
	result.count = result.result.AsQueryable().Count();
	if (data.Skip > 0)
		result.result = operation.PerformSkip(result.result, data.Skip);
	if (data.Take > 0)
		result.result = operation.PerformTake(result.result, data.Take);
	return Json(result, JsonRequestBehavior.AllowGet);
}
public class DataResult
{
	public IEnumerable result { get; set; }
	public int count { get; set; }
}
{% endhighlight %}

The grid actions (sorting, filtering, paging, searching, and aggregates) details are obtained in the 'DataManager' class. While initializing the grid, paging only enabled hence in the below screen shot paging details are bound to the DataManager class.

Please refer the below screen shot.

![](Editing_images/Editing_img20.png)


Also, using 'DataOperations' helper class you can perform grid action at server side. The in-built methods that we have provided in the DataOperations class are listed below.

1. PerformSorting
2. PerformFiltering
3. PerformSearching
4. PerformSkip
5. PerformTake
6. PerformWhereFilter
7. PerformSelect
8. Execute

### Accessing CRUD action request details in server side:

The 'Server-Side' function must be declared with the following parameter name for each editing functionality.

Parameters Table

<table>
        <tr>
            <th>
                Action
            </th>
            <th>
                Parameter Name</th>
            <th>
                Example
            </th>
        </tr>
        <tr>
            <td rowspan="2">
                Update,Insert
            </td>
            <td>
                value
            </td>
            <td rowspan="2">
                public ActionResult Update(EditableOrder value){ }
            </td>
        </tr>
        <tr>
           
            <td>
                public ActionResult Insert(EditableOrder value){ }
            </td>
        </tr>
        <tr>
            <td>
                Remove
            </td>
            <td>
                key
            </td>
            <td>
                public ActionResult Remove(int key){ }
            </td>
        </tr>
        <tr>
            <td>
                Batch Add
            </td>
            <td>
                added
            </td>
            <td rowspan="3">
                public ActionResult BatchUpdate(string action, List &lt;editableorder&gt; added, List &lt;editableorder&gt; changed, List &lt;editableorder&gt; deleted, int? key){ }
            </td>
        </tr>
        <tr>
            <td>
                Batch Update
            </td>
            <td>
                changed
            </td>
            
        </tr>
        <tr>
            <td>
                Batch Delete
            </td>
            <td>
                deleted
            </td>
           
        </tr>
        <tr>
            <td>
                Crud Update,Crud Insert
            </td>
            <td>
                value, action
            </td>
            <td>
                public ActionResult CrudUrl(EditableOrder value, string action){ }
            </td>
        </tr>
        <tr>
            <td>
                Crud Remove
            </td>
            <td>
                action, key, keyColumn
            </td>
            <td>
               public ActionResult CrudUrl(string action, int? key, string keyColumn){ }
            </td>
        </tr>
		<tr>
            <td>
               Crud Remove - Multi Delete
            </td>
            <td>
                action, key, deleted
            </td>
            <td>
               public ActionResult CrudUrl(string action, string key, List <EditableOrder> deleted){ }
            </td>
        </tr>
    </table>

	
### Insert Record:

Using `insertUrl` property, you can specify the controller action mapping URL to perform insert operation at server side.

The following code example describes the above behavior.

{% highlight cs %}
public ActionResult Insert(EditableOrder value)
{
    OrderRepository.Add(value);
    var data = OrderRepository.GetAllRecords();
    return Json(value, JsonRequestBehavior.AllowGet);
}
{% endhighlight %}

The newly added record details are bound to the 'value' parameter. Please refer the below image.


![](Editing_images/Editing_img21.png)


### Update Record:

Using `updateUrl` property, you can specify the controller action mapping URL to perform save/update operation at server side.

The following code example describes the above behavior.

{% highlight cs %}
public ActionResult Update(EditableOrder value)
{
    OrderRepository.Update(value);
    var data = OrderRepository.GetAllRecords();
    return Json(value, JsonRequestBehavior.AllowGet);
}
{% endhighlight %}

The updated record details are bound to the 'value' parameter. Please refer the below image.

![](Editing_images/Editing_img22.png)


### Delete Record:

Using `removeUrl` property, you can specify the controller action mapping URL to perform delete operation at server side.

The following code example describes the above behavior.

{% highlight cs %}
public ActionResult Remove(int key)
{
    OrderRepository.Delete(key);
    var data = OrderRepository.GetAllRecords();
    return Json(key, JsonRequestBehavior.AllowGet);
}
{% endhighlight %}

The deleted record primary key value is bound to the 'key' parameter. Please refer the below image.

![](Editing_images/Editing_img23.png)


### CRUD URL:

Instead of specifying separate controller action method for CRUD (insert, update and delete)operation, using `crudUrl` property you can specify the controller action mapping URL to perform all the CRUD operation at server side using single method.

The action parameter of `crudUrl` is used to get the corresponding CRUD action.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script> 
 {% endhighlight %}

 Create a JSX file and paste the following content

{% highlight javascript %}
        var data = ej.DataManager({
          url: "/Home/DataSource",
          adaptor: "UrlAdaptor",
          crudUrl : "Home/CrudUpdate"
        });
		var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true,showDeleteConfirmDialog:true};
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   

        ReactDOM.render(   
		  <EJ.Grid dataSource = {data} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="EmployeeID" />
                <column field="Freight" editType="numericedit" format="{0:C}" />
                <column field="ShipName" />
                <column field="ShipCountry" />
            </columns>  
          </EJ.Grid>,
          document.getElementById('Grid')
        );

{% endhighlight %}

{% highlight cs %}
public ActionResult CrudUpdate(EditableOrder value, string action,int key)
{
    if (action == "update")
        OrderRepository.Update(value);
    else if (action == "insert")
        OrderRepository.Add(value);
    else if (action == "remove")
        OrderRepository.Delete(key);
    return Json(value, JsonRequestBehavior.AllowGet);
}
{% endhighlight %}

Please refer the below image to know about the action parameter

![](Editing_images/Editing_img24.png)


N> If you specify `insertUrl` along with `CrudUrl` then while adding `insertUrl` only called.

### Batch URL:

The `batchUrl` property supports only for batch editing mode. You can specify the controller action mapping URL to perform Batch operation at server side.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
 {% endhighlight %}

Create a JSX file and paste the following content

 {% highlight javascript %}
         var data = ej.DataManager({
          url: "/Home/DataSource",
          adaptor: "UrlAdaptor",
          batchUrl : "Home/BatchUpdate"
        });
		var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true,showDeleteConfirmDialog:true};
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   

        ReactDOM.render(   
		  <EJ.Grid dataSource = {data} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="EmployeeID" />
                <column field="Freight" editType="numericedit" format="{0:C}" />
                <column field="ShipName" />
                <column field="ShipCountry" />
            </columns>  
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}


{% highlight cs %}
public ActionResult BatchUpdate(string action, List<EditableOrder> added, List<EditableOrder> changed, List<EditableOrder> deleted, int? key)
{
	if (changed != null)
        OrderRepository.Update(changed);
    if (deleted != null)
        OrderRepository.Delete(deleted);
    if (added != null)
        OrderRepository.Add(added);
    var data = OrderRepository.GetComplexRecords();
    return Json(new { changed = changed, added = added, deleted = deleted }, JsonRequestBehavior.AllowGet);
}

{% endhighlight %}


Please refer the below image for more information about batch parameters

![](Editing_images/Editing_img25.png)


## Adding New Row Position

To add new row in the top or bottom position of grid content, set [`rowPosition`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-rowposition "rowPosition") property of [`editSettings`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings "editSettings") depending on the requirement.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
		var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true, rowPosition:"bottom" };
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   

        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="ShipCity" />
                <column field="Freight" editType="numericedit" />
                <column field="ShipCountry" />
            </columns>   
          </EJ.Grid>,
          document.getElementById('Grid')
        );

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img26.png)


## Render with blank row for easy add new

The blank add new row is displayed in the grid content during grid initialization itself to add a new record easily. To enable show add new row by default, set [`showAddNewRow`](http://help.syncfusion.com/api/js/ejgrid#members:showaddnewrow "showAddNewRow") property of [`editSettings`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings "editSettings") as `true`.

The blank add new row is displayed either in the top or bottom of the corresponding page, its position is based on the [`rowPosition`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-rowposition "rowPosition") property of [`editSettings`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings "editSettings").

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
		var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true, showAddNewRow:true};
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   

        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="ShipCity" />
                <column field="Freight" editType="numericedit" />
                <column field="ShipCountry" />
            </columns>   
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img27.png)


N> 1. If it is remote, then the newly added record is placed based on the index from current view data. 
N> 2. If it is local, then the newly added record is added at the top of the page even if the added new [`rowPosition`](http://help.syncfusion.com/api/js/ejgrid#members:editsettings-rowposition "rowPosition") is mentioned as "bottom".


## Default column values on add new

While adding new record in grid, there is an option to set the default value for the columns. Using [`defaultValue`](http://help.syncfusion.com/api/js/ejgrid#members:columns-defaultvalue "defaultValue") property of [`columns`](http://help.syncfusion.com/api/js/ejgrid#members:columns "columns") you can set the default values for that particular column while editing or adding a new row.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script type="text/babel" src="app.jsx">
</script>
{% endhighlight %}

Create a JSX file and paste the following content

{% highlight javascript %}
		var editSettings = { allowEditing: true, allowAdding: true, allowDeleting: true };
        var toolbarItems = { showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel"] };   

        ReactDOM.render(   
                //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		  <EJ.Grid dataSource = {window.gridData} allowPaging = {true} editSettings={editSettings} toolbarSettings={toolbarItems}>
            <columns>
                <column field="OrderID" isPrimaryKey={true} />
                <column field="CustomerID" />
                <column field="ShipCity" defaultValue="Bern" />
                <column field="Freight" editType="numericedit" defaultValue={45} />
                <column field="ShipCountry" defaultValue="Brazil"/>
            </columns>   
          </EJ.Grid>,
          document.getElementById('Grid')
        );
{% endhighlight %}


The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img28.png)