---
layout: post
title: Data binding
description: Learn how to bind Chart with JSON data from a remote server or locally in client browser.
platform: js
control: Chart
documentation: ug
api : /api/js/ejchart
---

# Working with Data

## Local Data

There are two ways to provide local data to chart.

1. You can bind the data to the chart by using the [`dataSource`](../api/ejchart#members:series-datasource) property of the series and then you need to map the X and Y value with the [`xName`](../api/ejchart#members:series-xname) and [`yName`](../api/ejchart#members:series-yname) properties respectively.

N> For the **OHLC** type series, you have to map four dataSource fields ([`high`](../api/ejchart#members:series-high), [`low`](../api/ejchart#members:series-low), [`open`](../api/ejchart#members:series-open) and [`close`](../api/ejchart#members:series-close)) to bind the data source and for the **bubble** series you have to map the [`size`](../api/ejchart#members:series-size) field along with the [`xName`](../api/ejchart#members:series-xname) and [`yName`](../api/ejchart#members:series-yname). 


{% highlight javascript %}

     var chartData = [
          { month: 'Jan', sales: 35 }, { month: 'Feb', sales: 28 },  { month: 'Mar', sales: 34 },
          { month: 'Apr', sales: 32 },{ month: 'May', sales: 40 },{ month: 'Jun', sales: 32 },
          { month: 'Jul', sales: 35 },  { month: 'Aug', sales: 55 }, { month: 'Sep', sales: 38 },
          { month: 'Oct', sales: 30 }, { month: 'Nov', sales: 25 }, { month: 'Dec', sales: 32 }];

       var series=[
        {
	        dataSource: chartData,
	        xName: "month",
	        yName: "sales"	
        }
       ];
       ReactDOM.render(
    <EJ.Chart id="default_chart_sample_0"
    series={series}
    >
        
            
    </EJ.Chart>,
		  document.getElementById('chart-default')
    );


{% endhighlight %}

![](/js/Chart/Working-with-Data_images/Working-with-Data_img1.png)

[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/databinding/localdata) here to view the local data binding online demo sample.


2.You can also plot data to chart using [`points`](../api/ejchart.html#members:series-points) option in the series. Using this property you can customize each and every point in the data.

{% highlight javascript %}

    "use strict";
      var series = [{
               //Adding data points using x and y field of points
               points: [{ x: "John", y: 10000 }, { x: "Jake", y: 12000 }, { x: "Peter", y: 18000 },
                        { x: "James", y: 11000 }, { x: "Mary", y: 9700 }],
               // ...
           }];
    ReactDOM.render(
    <EJ.Chart id="chart1" series = {series} ></EJ.Chart>,
          document.getElementById('chart-default')
    );



{% endhighlight %}

![](/js/Chart/Working-with-Data_images/Working-with-Data_img2.png)

## Remote Data

You can bind the remote data to the chart by using the DataManager and you can use the [`query`](../api/ejchart#members:series-query) property of the series to filter the data from the dataSource.


{% highlight javascript %}

        "use strict";
     //Remote URL           
        var dataManger = new ej.DataManager({
            url: "http://mvc.syncfusion.com/Services/Northwnd.svc/"
        });
        // Query creation
        var query = ej.Query().from("Orders").take(6);
       var series = [{
                type: 'column',
                dataSource: dataManger,
                xName: "ShipCity",
                yName: "Freight",
                query: query,
            }];
           
           
    ReactDOM.render(
        <EJ.Chart id="chart1" series = {series} ></EJ.Chart>,
            document.getElementById('chart-default')
    );


{% endhighlight %}

![](/js/Chart/Working-with-Data_images/Working-with-Data_img3.png)

[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/databinding/remotedata) here to view the remote data binding online demo sample.	


