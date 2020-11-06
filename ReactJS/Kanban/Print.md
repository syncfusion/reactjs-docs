---
layout: post
title:  Print with Kanban widget for Syncfusion Essential JS
description: How to enable print option in Kanban
documentation: ug
platform: React JS
---

# Print

 Set [‘allowPrinting’](https://help.syncfusion.com/api/js/ejkanban#members:allowprinting) as true, to enable Print icon in the Kanban toolbar.  You can use [‘print()’](https://help.syncfusion.com/api/js/ejkanban#methods:print) method from Kanban instance to print the Kanban.

The following code example describes the above behavior.

{% highlight html %}

var data = ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(20));
ReactDOM.render(
<EJ.Kanban dataSource={data} keyField="Status" fields-content="Summary" fields-primaryKey="Id" allowPrinting={true}>
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

![](Printing_images/print_img1.png)


