---
layout: post
title:  Scrolling
description: Scrolling
documentation: ug
platform: React JS
keywords: scrolling,kanban scrolling
---

# Scrolling

Scrolling can be enabled by setting [`allowScrolling`](https://help.syncfusion.com/api/js/ejkanban#members:allowscrolling) as true. The height and width can be set to Kanban by using the properties [`scrollSettings-height`](https://help.syncfusion.com/api/js/ejkanban#members:scrollsettings-height) and [`scrollSettings-width`](https://help.syncfusion.com/api/js/ejkanban#members:scrollsettings-width) respectively.

N> The height and width can be set in percentage and pixel. The default value for [`height`](https://help.syncfusion.com/api/js/ejkanban#members:scrollsettings-height) and [`width`](https://help.syncfusion.com/api/js/ejkanban#members:scrollsettings-width) in [`scrollSettings`](https://help.syncfusion.com/api/js/ejkanban#members:scrollsettings) is 0 and auto respectively.

## Set width and height in pixel

To specify the [`scrollSettings-width`](https://help.syncfusion.com/api/js/ejkanban#members:scrollsettings-width) and [`scrollSettings-height`](https://help.syncfusion.com/api/js/ejkanban#members:scrollsettings-height) in pixel, by set the pixel value as integer.

The following code example describes the above behavior.

{% highlight html %}

var data = ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(20));
var scrollSetting={
	        width: 900,
            height: 450
};
ReactDOM.render(
<EJ.Kanban dataSource={data} keyField="Status" fields-content="Summary" fields-primaryKey="Id" fields-tag="Tags" allowScrolling={true} scrollSettings={scrollSetting}>
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

![](Scrolling_images/scroll_img1.png)

## Set height and width in percentage

To specify the [`scrollSettings-width`](https://help.syncfusion.com/api/js/ejkanban#members:scrollsettings-width) and [`scrollSettings-height`](https://help.syncfusion.com/api/js/ejkanban#members:scrollsettings-height) in percentage, by set the percentage value as string.

The following code example describes the above behavior.


{% highlight html %}

var data = ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(20));
var scrollSetting={
	        width: "70%", height: "70%"
};
ReactDOM.render(
<EJ.Kanban dataSource={data} keyField="Status" fields-content="Summary" fields-primaryKey="Id" fields-tag="Tags" allowScrolling={true} scrollSettings={scrollSetting}>
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

![](Scrolling_images/scroll_img2.png)

## Set width as auto

Specify [`width`](https://help.syncfusion.com/api/js/ejkanban#members:scrollsettings-width) property of [`scrollSettings`](https://help.syncfusion.com/api/js/ejkanban#members:scrollsettings) as auto, then the scrollbar is rendered only when the Kanban width exceeds the browser window width.

The following code example describes the above behavior.

{% highlight html %}

var data = ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(20));
var scrollSetting={
	        width: "auto", height: 300
};
ReactDOM.render(
<EJ.Kanban dataSource={data} keyField="Status" fields-content="Summary" fields-primaryKey="Id" fields-tag="Tags" allowScrolling={true} scrollSettings={scrollSetting}>
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

![](Scrolling_images/scroll_img3.png)

## Enabling freeze swim lane

Set [`scrollSettings-allowFreezeSwimlane`](https://help.syncfusion.com/api/js/ejkanban#members:scrollsettings-allowfreezeswimlane) as true. This enables scrolling with freezing of swim lane until you scroll to the next Swim lane, which helps user to aware of current swim lane target.

The following code example describes the above behavior.

{% highlight html %}

var data = ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(20));
var scrollSetting= { width: "auto", height: 500,allowFreezeSwimlane: true };
ReactDOM.render(
<EJ.Kanban dataSource={data} keyField="Status" fields-content="Summary" fields-primaryKey="Id" fields-swimlaneKey="Assignee" fields-tag="Tags" allowScrolling={true} scrollSettings={scrollSetting}>
    <columns>
		<column headerText="Backlog" key="Open"></column>
		<column headerText="In Progress" key="InProgress"></column>
		<column headerText="Testing" key="Testing"></column>
	    <column headerText="Done" key="Close"></column>
	</columns>
</EJ.Kanban>,
   document.getElementById('kanbanboard-default')
);

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Scrolling_images/scroll_img4.png)

N> `allowFreezeSwimlane` is applicable when swim lane grouping enabled by setting `swimlaneKey`.

