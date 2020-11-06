---
title: Named Set
description: named set
platform: React JS
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Named Sets

Named sets is a multidimensional expression (MDX) that returns a set of dimension members, which can be created by combining cube data, arithmetic operators, numbers and functions.

You can bind the Named Sets in PivotGrid by setting it's unique name in the [`fieldName`](/api/js/ejpivotgrid#members:datasource-rows-fieldname) property either in row or column axis and [`isNamedSets`](/api/js/ejpivotgrid#members:datasource-columns-isnamedsets) boolean property to "true".

{% highlight html %}

<!--Create a tag which acts as a container for PivotGrid-->
 <div id="PivotGrid1" style="height: 350px; width: 100%; overflow: auto"></div>
<script type="text/babel">
    var Olap_dataSource={
        data: "http://bi.syncfusion.com/olap/msmdpump.dll", 
        catalog: "Adventure Works DW 2008 SE", //"Adventure Works DW 2008 SEtandard Edition
        cube: "Adventure Works", rows: [{ fieldName: "[Date].[Fiscal]" }], columns: [{ fieldName: "[Core Product Group]", isNamedSets: true }],
        values: [{ measures: [{ fieldName: "[Measures].[Internet Sales Amount]" }, axis: "columns" }]    
    };
    $(function(){
        ReactDOM.render(
            <EJ.PivotGrid id="Olap" dataSource= {Olap_dataSource}></EJ.PivotGrid>,
            document.getElementById('PivotGrid1')
        );
    });
</script>

{% endhighlight %}

![](KPI_images/namedset.png)
