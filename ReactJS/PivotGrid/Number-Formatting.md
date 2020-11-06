---
title: Number format
description: Number format
platform: React JS
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Number Format 

Allows us to specify the required number format that PivotGrid should use in its values by setting the `format` option. Following number formats that are supported:

* number
* decimal
* currency
* percentage
* date
* time
* scientific
* accounting
* fraction

## RELATIONAL

{% highlight js %}

<script type="text/babel">
    var pivot_dataset = []; // data source
    var  pivotdataSource = {
        data: pivot_dataset, 
        //...
        values: [
                    { fieldName: "Amount", fieldCaption: "Amount", format: "currency" },
                    { fieldName: "Quantity", fieldCaption: "Quantity", format: "decimal" }
                ]
    };
</script>

{% endhighlight %}

![](Number-Format_images/RelationalClient.png)

## OLAP

{% highlight html %}

<script type="text/babel">
    var Olap_dataSource={
        //...
        values: [{ measures: [{ fieldName: "[Measures].[Internet Sales Amount]",
                                format: "percent" //Specify the format here 
                            }], 
                    axis: "columns" 
                }]    
    };  
</script>

{% endhighlight %}

![](Number-Format_images/OlapClient.png)