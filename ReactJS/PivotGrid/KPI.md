---
title: Key-Performance-Indicator-KPI
description: key performance indicator (KPI)
platform: React JS
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# KPI

Key Performance Indicators (KPIs) are business metric that help to figure out the progress of an enterprise in meeting its business goals.

The different indicators available in KPI are:

* KPI Value: A physical measure or a calculated measure.
* KPI Goal: Defines the target for the measure.
* KPI Status: Evaluates the current status of the value compared to the goal.
* KPI Trend: Evaluate the current trend of the value compared to the goal.

The **“KpiElements”** class in OLAP Base library holds the KPI name and when its object is added to an OlapReport, you can view the resultant information in PivotGrid.

{% highlight html %}

<!--Create a tag which acts as a container for PivotGrid-->
 <div id="PivotGrid1" style="height: 350px; width: 100%; overflow: auto"></div>
<script type="text/babel">
    var Olap_dataSource={
        data: "http://bi.syncfusion.com/olap/msmdpump.dll", 
        catalog: "Adventure Works DW 2008 SE", //"Adventure Works DW 2008 SEtandard Edition
        cube: "Adventure Works", rows: [{ fieldName: "[Date].[Fiscal]" }], columns: [{ fieldName: "[Product].[Product Categories]" }],
        values: [{ measures: [{ fieldName: "[Measures].[Internet Sales Amount]" },{ fieldName: "[Measures].[Growth in Customer Base Trend]" }], axis: "columns" }]    
    };
    $(function(){
        ReactDOM.render(
            <EJ.PivotGrid id="Olap" dataSource= {Olap_dataSource}></EJ.PivotGrid>,
            document.getElementById('PivotGrid1')
        );
    });
</script>

{% endhighlight %}

![](KPI_images/ClientSideKPI.png)
