---
layout: post
title: Using Essential JavaScript Chart in real-time scenario 
description: Learn how to update the chart dynamically with real-time data. 
platform: js
control: Chart
documentation: ug
api : /api/js/ejchart
---

# Real-Time Chart 

Chart can be updated dynamically with the real time data. Whenever you add a point or remove a point from the dataSource, you can call the [`redraw`](../api/ejchart#members:redraw) method to request the chart to redraw its content.    

N> You can get the chart **instance** using instance method.

{% highlight javascript %}

"use strict";
	window.setInterval(updateChart, 200);
        var series= [ 
                {  points: [ ] }
        ]; 
		    //Function that updates chart dynamically
	function updateChart(){

	        //Creating chart instance
		var chart =  $("#default_chart_sample_0").ejChart("instance");      
			
		if (chart.model.series[0].points.length > 10)
			chart.model.series[0].points.splice(0, 1);
		
		var point = chart.model.series[0].points;
		var xValue = point.length > 0 ? point[point.length - 1].x + 1 : 1;
		point[point.length] = { x:  xValue, y: getRandomNum( 1000 ) }
				
		//Update Chart dynamically using redraw option
		//chart.redraw() can also be used here instead of redraw option
		$("#default_chart_sample_0").ejChart("redraw");      
       }
        // ...
	ReactDOM.render(
		<EJ.Chart id="default_chart_sample_0"		
			
		>      
		</EJ.Chart>,
			document.getElementById('chart')
	);

{% endhighlight %}

[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/live) here to view the online demo sample for real-time Chart.


