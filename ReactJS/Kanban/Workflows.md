---
layout: post
title:  Workflows
description: Workflows
documentation: ug
platform: React JS
keywords: Workflows,kanban Workflows
---

# Workflows 

Workflows can be defined to set the flow of card moving between the Kanban column statuses and it is applicable to drag and drop and context menu features.

You can set [`workflows`](https://help.syncfusion.com/api/js/ejkanban#members:workflows) as array of Objects which consists of [`key`](https://help.syncfusion.com/api/js/ejkanban#members:workflows-key) and [`allowedTransitions`](https://help.syncfusion.com/api/js/ejkanban#members:workflows-allowedtransitions) properties. The `allowedTransitions` accepts more than one transition of the specific column key mentioned in `key` property.

If a card is to be dragged to not allowed transition columns , then not supported warning symbol will be displayed for denoting the error.
        
The following code example describes the above Workflow functionality.

{% highlight html %}

var data = ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(20));
var workflow =[                
				     { key:"Open",allowedTransitions:"InProgress"},
                     { key:"InProgress",allowedTransitions:"Testing,Close"}
				   ];
ReactDOM.render(
<EJ.Kanban dataSource={data} keyField="Status" fields-content="Summary" fields-primaryKey="Id" workflows={workflow} fields-imageUrl="ImgUrl" allowTitle={true}>
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

![](WorkFlows_images/workflows1.png)