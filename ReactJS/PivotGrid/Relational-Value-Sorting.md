---
title: Value-Sorting
description: value Sorting
platform: React JS
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Value Sorting

I> This feature is applicable for Relational datasource only at Client Mode.

Value Sorting allows to sort columns and rows based on value fields.

The headers of the column to be sorted is given in the 'headerText' property under 'valueSortSettings' in field wise order separated by a string.  The string which is used to separate the headers is given in the property 'headerDelimiters'.

{% highlight html %}

<script type="text/babel">
        var pivot_dataset = []; // data source          
        var  pivotdataSource = {
            data: pivot_dataset,
            rows: [{ fieldName: "Country", fieldCaption: "Country" },{ fieldName: "State", fieldCaption: "State" }],
            columns: [{ fieldName: "Product", fieldCaption: "Product" }],
            values: [{ fieldName: "Amount", fieldCaption: "Amount" },{ fieldName: "Quantity", fieldCaption: "Quantity" }],
            filters: []
        };            
        var valueSort = {
            headerText: "Bike##Quantity",
            headerDelimiters: "##",
            sortOrder: ej.PivotAnalysis.SortOrder.Descending
        };
        $(function(){
            ReactDOM.render(
            <EJ.PivotGrid id="Relational" dataSource= {pivotdataSource} valueSortSettings= {valueSort}></EJ.PivotGrid>,
            document.getElementById('PivotGrid1')
            );
        });
    </script>

{% endhighlight %}

![](Value-Sorting_images/Before.png) 

![](Value-Sorting_images/After.png) 



