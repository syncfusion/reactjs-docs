---
layout: post
title: Populate-Data
description: Populate Data
platform: js
control: RangeNavigator
documentation: ug
---

### Populate Data

When you provide data to **RangeNavigator**, it produces limited set of data. You can populate the **RangeNavigator** with data using the **dataSource** and **series** properties.

#### Add series to the RangeNavigator

The **Series** property provides access to a collection of all series that are defined explicitly within a **RangeNavigator** control. Each series is assigned with type and name. It contains collection of data point, each point contains x value and y values. You can add data points to the series through **dataSource** property.



{% highlight html %}

"use strict";
var rangeSettings = {
                    start: "2010/1/1", end: "2010/12/31"
};        
var series = [{
                  type: 'line',                                     
                  opacity: 0.5, fill: '#69D2E7',
                  border: { color: 'transparent', width: 2 }
}];
                

ReactDOM.render(
            <EJ.RangeNavigator id="rangenavigator1" load = {onchartload} series={series} 
            rangeSettings = {rangeSettings} ></EJ.RangeNavigator>,
            document.getElementById('rangenavigator')
);
var data;
function onchartload(sender) {            
            data = GetData();
            sender.model.series[0].dataSource = data.Open;
            sender.model.series[0].xName= "XValue";
            sender.model.series[0].yName= "YValue";           
};
function GetData() {
            var series1 = [];       
            var value = 100;
            for (var i = 1; i < 360; i++) {
                if (Math.random() > .5) {
                    value += Math.random();                 
                } else {
                    value -= Math.random();           
                }
                var point1 = { XValue: new Date(2010, 0, i), YValue: value };               
                series1.push(point1);             
            }
            data = { Open: series1};
            return data;
};


{% endhighlight %}


The following screenshot illustrates the **RangeNavigator** that is populated with data using **dataSource** property in series.

![](/js/RangeNavigator/Populate-Data_images/Populate-Data_img1.png) 
