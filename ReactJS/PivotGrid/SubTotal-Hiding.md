---
title:  SubTotal Hiding
description: SubTotal Hiding
platform: React JS
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Sub Total Hiding

N> This feature is applicable only for Relational data source.

You can hide the **Sub Total** for respective fields in rows and columns by setting the property [`showSubTotal`](/api/js/ejpivotgrid#members:showSubTotal) to `false`

{% highlight html %}

<script type="text/babel">
        //..         
        var  pivotdataSource = {
            data: pivot_dataset,
            rows: [{ fieldName: "Country", fieldCaption: "Country", showSubTotal: false },{ fieldName: "State", fieldCaption: "State" }],
            columns: [{ fieldName: "Product", fieldCaption: "Product" }],
            values: [{ fieldName: "Amount", fieldCaption: "Amount" },{ fieldName: "Quantity", fieldCaption: "Quantity" }],
            filters: []
        };
        //..
    </script>

{% endhighlight %}

![](SubTotal-Hiding_images/SubTotal.png)
