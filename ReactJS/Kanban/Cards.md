---
layout: post
title:  Cards
description: Cards
documentation: ug
platform: React JS
keywords: cards,kanban cards
---

# Cards

## Customization

Cards can be customized with appropriate mapping fields from the database. The customizable mapping properties are listed as follows 

<table>
<tr>
<th>
Mapping Fields</th><th>
Description</th></tr>
<tr>
<td>
{{ '[fields-content](https://help.syncfusion.com/api/js/ejkanban#members:fields-content)' | markdownify }} </td><td> Map the column name to use as content to cards.</td></tr>
<tr>
<td>
{{ '[fields-tag](https://help.syncfusion.com/api/js/ejkanban#members:fields-tag)' | markdownify }} </td><td>
Map the column name to use as tag. Multiple tags can be given with comma separated.  E.g. "API","SQL, Database".</td></tr>
<tr>
<td>
{{ '[fields-color](https://help.syncfusion.com/api/js/ejkanban#members:fields-color)' | markdownify }} </td><td>
 Map the column name to use as colors to highlight cards left border.</td></tr>
<tr>
<td>
{{ '[cardSettings-colorMapping](https://help.syncfusion.com/api/js/ejkanban#members:cardsettings.colormapping)' | markdownify }} </td><td>
Map the colors to use with column values which is mapped with `fields-color`.</td></tr>
<tr>
<td>
{{ '[fields-imageUrl](https://help.syncfusion.com/api/js/ejkanban#members:fields-imgurl)' | markdownify }} </td><td>
Map the column name to use as image to cards.</td></tr>
<tr>
<td>
{{ '[fields-primaryKey](https://help.syncfusion.com/api/js/ejkanban#members:fields-primarykey)' | markdownify }} </td><td>
Map the column name to use as primary key to cards.</td></tr>
<tr>
<td>
{{ '[fields-priority](https://help.syncfusion.com/api/js/ejkanban#members:fields-priority)' | markdownify }} </td><td>
Map the column name to use as priority to cards.</td></tr>
<tr>
<td>
{{ '[fields-title](https://help.syncfusion.com/api/js/ejkanban#members:fields-title)' | markdownify }} </td><td>
Map the column name to use as title to cards. Default title is  `primaryKey`.</td></tr>
<tr>
<td>
{{ '[allowTitle](https://help.syncfusion.com/api/js/ejkanban#members:allowtitle)' | markdownify }} </td><td>
Set as true to enable title for card.</td></tr>
</table>

The following code example describes the above behavior.

{% highlight html %}

var data = ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(20));
var colormap = {
            "#cb2027": "Bug,Story",
            "#67ab47": "Improvement",
            "#fbae19": "Epic",
			"#6a5da8": "Others"
        };
ReactDOM.render(
<EJ.Kanban dataSource={data} keyField="Status" fields-content="Summary" fields-primaryKey="Id" fields-priority="RankId" fields-tag="Tags" fields-color="Type" fields-imageUrl="ImgUrl" cardSettings-colorMapping={colormap} allowTitle={true}>
    <columns>
		<column headerText="Backlog" key="Open"></column>
		<column headerText="In Progress" key="InProgress"></column>
	    <column headerText="Done" key="Close"></column>
	</columns>
</EJ.Kanban>,
   document.getElementById('kanbanboard-default')
);

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Cards_images/cards_img1.png)

## Template

Templates are used to create custom card layout as per the user convenient. HTML templates can be specified in the [`template`](https://help.syncfusion.com/api/js/ejkanban#members:cardSettings-template) property of the [`cardSettings`](https://help.syncfusion.com/api/js/ejkanban#members:cardsettings) as an ID of the template’s HTML element.

You can use JsRender syntax in the template. For more information about JsRender syntax, please refer this [`link`](https://www.jsviews.com/).

The following code example describes the above behavior.

{% highlight html %}

    <div id="kanbanboard-default"></div>
    <script src="app/kanbanboard/default.js"></script>

   <script id="cardtemplate" type="text/x-jsrender">             
        <table class="e-templatetable">
           <colgroup>
               <col width="10%">
               <col width="90%">
          </colgroup>
          <tbody>
           <tr>
            <td class="photo">
                <img src="content/images/kanban/{{:Priority}}.png">
            </td>            
            <td class="details">
                <table>
                    <colgroup>
                        <col width="10%">
                        <col width="90%">
                    </colgroup>
                    <tbody>
                        <tr>
                            <td class="CardHeader">   Assignee: </td>
                            <td>{{:Assignee}}</td>
                        </tr>                      
                        <tr>
                            <td class="CardHeader">   Summary: </td>
                            <td>{{:Summary}}</td>
                        </tr>
                        <tr>
                            <td class="CardHeader">   Type: </td>
                            <td>{{:Type}}</td>
                        </tr>                        
                    </tbody>
                </table>
            </td>
           </tr>
        </tbody>
    </table>     
    </script>

    <style type="text/css">  
        .e-templatetable {
            width: 100%;
        }
        .details >table {
            margin-left:2px;            
			border-collapse: separate;
            border-spacing: 2px;
            width: 100%;
        }
	    .details td {
	        vertical-align: top;
	    }
        .details {
            padding: 8px 8px 10px 0;
        }
        .photo {
            padding: 8px 6px 10px 6px;
            text-align: center;
        }
        .CardHeader {
            font-weight: bolder;
            padding-right: 10px;
        }
    </style>
            
{% endhighlight %}

{% highlight html %}

var data = ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(20));
var colormap = {
        "#cb2027": "Bug,Story",
        "#67ab47": "Improvement",
        "#fbae19": "Epic",
		"#6a5da8": "Others"
};
ReactDOM.render(
<EJ.Kanban dataSource={data} keyField="Status" fields-primaryKey="Id" fields-color="Type" cardSettings-template="#cardtemplate" cardSettings-colorMapping={colormap} allowTitle={true}>
    <columns>
		<column headerText="Backlog" key="Open"></column>
		<column headerText="In Progress" key="InProgress"></column>
	    <column headerText="Done" key="Close"></column>
	</columns>
</EJ.Kanban>,
   document.getElementById('kanbanboard-default')
);
    
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Cards_images/cards_img2.png)

## Tooltip

You can enable HTML tooltip for Kanban card elements by setting [`enable`](https://help.syncfusion.com/api/js/ejkanban#members:tooltipsettings-enable) property as true in [`tooltipSettings`](https://help.syncfusion.com/api/js/ejkanban#members:tooltipsettings).

The following code example describes the above behavior.

{% highlight html %}

ReactDOM.render(
<EJ.Kanban dataSource={data} keyField="Status" fields-content="Summary" fields-primaryKey="Id" fields-tag="Tags" tooltipSettings-enable={true}>
    <columns>
		<column headerText="Backlog" key="Open"></column>
		<column headerText="In Progress" key="InProgress"></column>
	    <column headerText="Done" key="Close"></column>
	</columns>
</EJ.Kanban>,
   document.getElementById('kanbanboard-default')
);

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Cards_images/cards_img3.png)

### Template

By making use of template feature with tooltip, all the field names that are mapped from the `dataSource` can be accessed to define the [`tooltipSettings-template`](https://help.syncfusion.com/api/js/ejkanban#members:tooltipsettings-template) tooltip for card. The [`tooltipSettings-enable`](https://help.syncfusion.com/api/js/ejschedule#members:tooltipsettings.enable) must be enabled first.

The following code example describes the tooltip template.

{% highlight html %}

    <script id="tooltipTemp" type="text/x-jsrender">
            <div class='e-kanbantooltiptemplate'>
                <table>
                    <tr>
                        <td class="photo">
                            <img src="{{:ImgUrl}}">
                        </td>
                        <td class="details">
                            <table>
                                <colgroup>
                                    <col width="30%">
                                    <col width="70%">
                                </colgroup>
                                <tbody>
                                    <tr>
                                        <td class="CardHeader">Assignee:</td>
                                        <td>{{:Assignee}}</td>
                                    </tr>
                                    <tr>
                                        <td class="CardHeader">Type:</td>
                                        <td>{{:Type}}</td>
                                    </tr>                                
                                    <tr>
                                        <td class="CardHeader">Estimate:</td>
                                        <td>{{:Estimate}}</td>
                                    </tr>                                
                                    <tr>
                                        <td class="CardHeader">Summary:</td>
                                        <td>{{:Summary}}</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                </table>
            </div>
    </script>
    <style> 
        .details >table {
            width: 100%;
            margin-left:2px;           
            border-collapse: separate;
            border-spacing: 1px;
        }
        .e-kanbantooltiptemplate {
            width: 250px;
            padding: 3px;
        }
        .e-kanbantooltiptemplate > table {
            width: 100%;
        }
        .e-kanbantooltiptemplate td {
            vertical-align: top;
        }
        td.details {
            padding-left: 10px;
        }
        .CardHeader {
            font-weight: bolder;
        }
    </style>

{% endhighlight %}

{% highlight html %}

var data = ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(20));
ReactDOM.render(
<EJ.Kanban dataSource={data} keyField="Status" fields-content="Summary" fields-primaryKey="Id" fields-tag="Tags" tooltipSettings-template="#tooltipTemp" tooltipSettings-enable={true}>
    <columns>
		<column headerText="Backlog" key="Open"></column>
		<column headerText="In Progress" key="InProgress"></column>
	    <column headerText="Done" key="Close"></column>
	</columns>
</EJ.Kanban>,
   document.getElementById('kanbanboard-default')
);

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Cards_images/cards_img4.png)