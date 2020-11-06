---
title: Getting Started for React JS Syncfusion Kanban
description: Getting-Started
platform: ReactJS
control: Kanban
documentation: Ug
keywords: 
---

# Getting Started

## Preparing HTML document

The Kanban control has the following list of external JavaScript dependencies.

* [`jQuery 1.7.1`](http://jquery.com) and later versions
* [`jsRender`](https://github.com/borismoore/jsrender) - to render the templates

The required ReactJS script dependencies as follows. And you can also refer [React](https://facebook.github.io/react/docs/getting-started.html) to know more about react js.

* `react.min.js` - [http://cdn.syncfusion.com/js/assets/external/react.min.js](http://cdn.syncfusion.com/js/assets/external/react.min.js)
* `react-dom.min.js` - [http://cdn.syncfusion.com/js/assets/external/react-dom.min.js](http://cdn.syncfusion.com/js/assets/external/react-dom.min.js)
* `ej.web.react.min.js` - [http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.web.react.min.js](http://cdn.syncfusion.com/14.3.0.49/js/common/ej.web.react.min.js)

Refer to the internal dependencies in the following table.

<table>
   <tr>
      <th>
         <b>Files</b>
      </th>
      <th>
         <b>Description/Usage </b>
      </th>
   </tr>
   <tr>
      <td>
         ej.core.min.js
      </td>
      <td>
        It is referred always before using all the JS controls.
      </td>
   </tr>
   <tr>
      <td>
         ej.data.min.js
      </td>
      <td>
         Used to handle data operation and is used while binding data to the JS controls.
      </td>
   </tr>
   <tr>
      <td>
        ej.touch.min.js 
      </td>
      <td>
          It is referred when using touch functionalities in Kanban.
      </td>
   </tr>
   <tr>
      <td>
        ej.draggable.min.js 
      </td>
      <td>
          It is referred when using drag and drop functionalities in Kanban.
      </td>
   </tr>
   <tr>
      <td>
        ej.kanban.min.js
      </td>
      <td>
        The Kanban’s main file.
      </td>
   </tr>
   <tr>
      <td>
        ej.globalize.min.js
      </td>
      <td>
       It is referred when using localization in Kanban.
      </td>
   </tr>
   <tr>
      <td>
         ej.scroller.min.js
      </td>
      <td>
         It is referred when scrolling is used in the Kanban. 
      </td>
   </tr>
   <tr>
      <td>
         ej.waitingpopup.min.js
      </td>
      <td>
        It is referred when waiting popup used.
      </td>
   </tr>
   <tr>
      <td>
        ej.dropdownlist.min.js
      </td>
      <td rowspan = "5">
         These files are used while enable the Editing feature in the Kanban.
      </td>
   </tr>
   <tr>
      <td>
         ej.dialog.min.js
      </td>
   </tr>
   <tr>
      <td>
        ej.button.min.js
      </td>
   </tr>
   <tr>
      <td>
         ej.datepicker.min.js
      </td>
   </tr>
   <tr>
      <td>
         ej.datetimepicker.min.js
      </td>
   </tr>
   <tr>
      <td>
         ej.editor.min.js
      </td>
   </tr>
   <tr>
      <td>
        ej.toolbar.min.js
      </td>
      <td>
        These files are used while enable the Filtering feature in the Kanban.
      </td>
   </tr>
    <tr>
      <td>
        ej.menu.min.js
      </td>
      <td rowspan = "2">
         These files are used while enable the context menu feature in the Kanban.
      </td>
   </tr>
   <tr>
      <td>
         ej.checkbox.min.js
      </td>
   </tr>
   <tr>
      <td>
        ej.rte.min.js
      </td>
      <td>
        These files are used while using the cell edit type as RTE in the Kanban.
      </td>
   </tr>
</table>


To get started, you can use the `ej.web.all.min.js` file that encapsulates all the `ej` controls and frameworks in one single file. So the complete boilerplate code is

{% highlight html %}

    <!DOCTYPE html>
    <html>
    <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Essential Studio for JavaScript">
    <meta name="author" content="Syncfusion">
    <title>Getting Started for Kanban React JS</title>
    <!-- Essential Studio for JavaScript  theme reference -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!-- Essential Studio for JavaScript  script references -->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
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

## Create a Kanban

Control can be initialized in two ways.

 * Using jsx Template
 * Without using jsx Template
 
## Using jsx Template

By using the jsx template, we can create the html file and jsx file. The `.jsx` file can be convert to `.js` file and it can be referred in html page.

Please refer to the code of HTML file.

{% highlight html %}

    <div id="kanbanBoard-default"></div>
    <script src="app/kanbanBoard/default.js"></script>

{% endhighlight %}

Kanban control can be initialized with the following in HTML document.

{% highlight html %}     
                
        ReactDOM.render(
            <EJ.Kanban >
                      <columns>
                          <column headerText="Backlog" />
                          <column headerText="In Progress" />
                          <column headerText="Done" />
                      </columns>
            </EJ.Kanban>,
            document.getElementById('kanbanBoard-default')
        );
    
{% endhighlight %}

![Getting Started](Getting-Started_images/Getting_Started_img1.png)

### Data Binding

`Data binding` in the Kanban is achieved by using the [`ej.DataManager`](http://help.syncfusion.com/js/datamanager/overview) that supports both RESTful JSON data services binding and local JSON array binding. To set the data source to Kanban, the `dataSource` property is assigned with the instance of the `ej.DataManger`. 

For demonstration purpose, [`Northwind OData service`](http://mvc.syncfusion.com/Services/Northwnd.svc/) is used in this tutorial. Refer to the following code example.

{% highlight html %}

        var dataManager = new ej.DataManager("http://mvc.syncfusion.com/Services/Northwnd.svc/Tasks");        
        ReactDOM.render(
            <EJ.Kanban dataSource = {dataManager} >
                      <columns>
                          <column headerText="Backlog" key="Open" />
                          <column headerText="In Progress" key="InProgress" />
                          <column headerText="Done" key="Close"/>
                      </columns>
            </EJ.Kanban>,
            document.getElementById('kanbanBoard-default')
        );

{% endhighlight %}

![Data Binding](Getting-Started_images/Getting_Started_img2.png)

N>  ODataAdaptor is the default adaptor used within DataManager. While binding to other web services, proper [`data adaptor`](http://help.syncfusion.com/js/datamanager/data-adaptors) needs to be set for `adaptor` option of DataManager.


### Mapping Values

In order to display cards in Kanban control, you need to map the database fields to Kanban cards and columns. The required mapping field are listed as follows

* `keyField` - Map the column name to use as `key` values to columns.
* `columns` -  Map the corresponding `key` values of `keyField` column to each columns
* `fields.content` - Map the column name to use as content to cards.
* `fields.primaryKey` - Map the column name to use as primary Key.

{% highlight html %}

        var dataManager = new ej.DataManager("http://mvc.syncfusion.com/Services/Northwnd.svc/Tasks");        
        ReactDOM.render(
            <EJ.Kanban dataSource = {dataManager} keyField = "Status" allowTitle={true} fields-content= "Summary" fields-primaryKey = "Id" allowSearching={true} fields-imageUrl="ImgUrl" allowSelection={false} >
                      <columns>
                          <column headerText="Backlog" key="Open" />
                          <column headerText="In Progress" key="InProgress" />
                          <column headerText="Done" key="Close"/>
                      </columns>
            </EJ.Kanban>,
            document.getElementById('kanbanBoard-default')
        );

{% endhighlight %} 

![Mapping Values](Getting-Started_images/Getting_Started_img3.png)

N>  `fields.primaryKey` field is mandatory for “Drag and Drop” ,”Selection” and “Editing” Features.


### Enable Swimlane

`Swimlane` can be enabled by mapping the `fields.swimlaneKey` to appropriate column name in `dataSource`. This enables the grouping of the cards based on the mapped column values.

{% highlight html %}

        var dataManager = new ej.DataManager("http://mvc.syncfusion.com/Services/Northwnd.svc/Tasks");        
        ReactDOM.render(
            <EJ.Kanban dataSource = {dataManager} keyField = "Status" allowTitle={true} fields-content= "Summary" fields-primaryKey = "Id" fields-swimlaneKey = "Assignee" allowSearching={true} fields-imageUrl="ImgUrl" allowSelection={false} >
                      <columns>
                          <column headerText="Backlog" key="Open" />
                          <column headerText="In Progress" key="InProgress" />
                          <column headerText="Done" key="Close"/>
                      </columns>
            </EJ.Kanban>,
            document.getElementById('kanbanBoard-default')
        );

{% endhighlight %} 

![Swim lane](Getting-Started_images/Getting_Started_img4.png)

### Adding Filters

Filters allows to filter the collection of cards from `dataSource` which meets the predefined `query` in the filters collection. To enable filtering, define `filterSettings` collection with display `text` and [`ej.Query`](http://help.syncfusion.com/js/datamanager/query).
 
{% highlight html %}

        var dataManager = new ej.DataManager("http://mvc.syncfusion.com/Services/Northwnd.svc/Tasks");
        var filter = [
                   { text: "Janet Issues", query: new ej.Query().where("Assignee", "equal", "Janet Leverling"), description: "Displays issues which matches the assignee as 'Janet Leverling'" },
                   { text: "Andrew Issues", query: new ej.Query().where("Assignee", "equal", "Andrew Fuller"), description: "Displays issues which matches the assignee as 'Andrew Fuller'" }
        ];
        ReactDOM.render(
            <EJ.Kanban dataSource = {dataManager} keyField = "Status" allowTitle={true} fields-content= "Summary" fields-primaryKey = "Id"  fields-swimlaneKey = "Assignee" allowSearching={true} fields-imageUrl="ImgUrl" allowSelection={false} filterSettings={filter}>
                      <columns>
                          <column headerText="Backlog" key="Open" />
                          <column headerText="In Progress" key="InProgress" />
                          <column headerText="Done" key="Close"/>
                      </columns>
            </EJ.Kanban>,
            document.getElementById('kanbanBoard-default')
        );

{% endhighlight %} 

![Filters](Getting-Started_images/Getting_Started_img5.png)

## Without using jsx Template

The Kanban can be created from a HTML `DIV` element with the HTML `id` attribute set to it. Refer to the following code example.

{% highlight html %}

    <body>
      <div id="kanbanboard-default"></div>
    </body>

{% endhighlight %}

Initialize the Kanban control by adding the following script code to the body section of the HTML document.

{% highlight html %}

    <div id="kanbanboard-default"></div>
    <script type="text/javascript">
        var dataManager = new ej.DataManager("http://mvc.syncfusion.com/Services/Northwnd.svc/Tasks");
        var filter = [
            { text: "Janet Issues", query: new ej.Query().where("Assignee", "equal", "Janet Leverling"), description: "Displays issues which matches the assignee as 'Janet Leverling'" },
            { text: "Open Issues", query: new ej.Query().where("Status", "equal", "Open"), description: "Displays issues which matches the status as 'Open'" }
        ];
        ReactDOM.render(
        React.createElement(EJ.Kanban,
            {
                dataSource: data,
                keyField: "Status",
                "fields-content": "Summary",
                "fields-primaryKey": "Id",
                "fields-swimlaneKey": "Assignee",
                filterSettings: filter
            },
            React.createElement("columns", null,
                            React.createElement("column", { headerText: "Backlog", key: "Open" }),
                            React.createElement("column", { headerText: "In Progress", key: "InProgress" }),
                            React.createElement("column", { headerText: "Done", key: "Close" })
                        )
             ),
             document.getElementById('kanbanBoard-default')
        );        
    </script>

{% endhighlight %}

![Without react template](Getting-Started_images/Getting_Started_img5.png)