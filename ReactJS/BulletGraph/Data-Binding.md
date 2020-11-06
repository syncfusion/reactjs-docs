---
layout: post
title: Data-Binding
description: data binding
platform: js
control: BulletGraph	
documentation: ug
api: /api/js/ejbulletgraph
---

# Data Binding

**Bullet Graph** supports binding JSON data from a remote server or data created in client-side. You can use the **fields** property to customize the data bound with **Bullet Graph**.

## Local Data

Data available in client-side (local data) can be bound with **Bullet Graph** using **fields** property. This property provides option to specify data source, fields representing progress measure bar value, comparative measure value and category value.

{% highlight javascript %}

"use strict";

var localData = [
    {
        value: 9.5, comparativeMeasureValue: 7.5,
        category: 2001
    },
    {
        value: 9.5, comparativeMeasureValue: 5,
        category: 2002
}];
var quantitativeScaleSettings= { location: { x:50, y:20 } };
var fields= {
    dataSource: localData, category: "category",
    featureMeasures: "value",
    comparativeMeasure: "comparativeMeasureValue"
};
ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	qualitativeRangeSize={60}
	quantitativeScaleSettings={quantitativeScaleSettings}
    >        
            
    </EJ.BulletGraph>,
		  document.getElementById('bulletgraph')
);



{% endhighlight %}



The following screenshot displays **Bullet Graph** with local data generated using JavaScript

![](/js/BulletGraph/Data-Binding_images/Data-Binding_img1.png) 

## Remote Data

**Bullet Graph** provides option to bind data from a remote server using **ejDataManager** as data source in **fields** property. A query object should also be passed to **query** property when using data manager as data source.

{% highlight javascript %}


"use strict";

    var dataManger = new ej.DataManager({
        url: "http://mvc.syncfusion.com/Services/Northwnd.svc/"
    });

    // Query creation
    var query = ej.Query().from("Order_Details").take(3).where("UnitPrice",     
        ej.FilterOperators.greaterThan, 18, false)
        .where("UnitPrice", ej.FilterOperators.lessThanOrEqual, 40, false)
        .where("Quantity", ej.FilterOperators.greaterThan, 5, false)
        .where("Quantity", ej.FilterOperators.lessThanOrEqual, 45, false);

    var fields = {
        dataSource: dataManger,
        query: query,
        category: "ProductID",
        featureMeasures: "UnitPrice",
        comparativeMeasure: "Quantity"
    };
    var qualitativeRanges = [{ rangeEnd: 25 }, { rangeEnd: 37 }, { rangeEnd: 45 }];

    var quantitativeScaleSettings = {
                        location: { x: 50, y: 20 },
                        minimum: 5,
                        maximum: 45,
                        interval: 10,
                    };
ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	qualitativeRanges ={qualitativeRanges}
    quantitativeScaleSettings ={quantitativeScaleSettings}  qualitativeRangeSize ={60} 
    fields ={fields}
    >        
            
    </EJ.BulletGraph>,
		  document.getElementById('bulletgraph')
);
              

{% endhighlight %}



The following screenshot displays a Bullet Graph bounded with data from a remote server

![](/js/BulletGraph/Data-Binding_images/Data-Binding_img2.png) 

