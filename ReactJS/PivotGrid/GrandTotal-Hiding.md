---
title:  GrandTotal Hiding
description: GrandTotal Hiding
platform: React JS
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Grand Total Hiding

Grand Total Hiding can be classified into three categories.

* Row Grand Total Hiding
* Column Grand Total Hiding
* Both

## Row Grand Total Hiding

You can hide the **Grand Total** in row alone by setting the property [`enableRowGrandTotal`](/api/js/ejpivotgrid#members:enablerowgrandtotal) to `false`

{% highlight html %}

<script type="text/babel">
    //...
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" enableRowGrandTotal= {false}></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>

{% endhighlight %}

![](GrandTotal-Hiding_images/enableRowGrandTotal.png)

## Column Grand Total Hiding

You can hide the **Grand Total** in column alone by setting the property [`enableColumnGrandTotal`](/api/js/ejpivotgrid#members:enablecolumngrandtotal) to `false`


{% highlight html %}

<script type="text/babel">
    //...
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" enableColumnGrandTotal= {false}></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>

{% endhighlight %}

![](GrandTotal-Hiding_images/enableColumnGrandTotal.png)

## Both

You can hide the **Grand Total** in both row and column by setting the property [`enableGrandTotal`](/api/js/ejpivotgrid#members:enablegrandtotal) to `false`

{% highlight html %}

<script type="text/babel">
    //...
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" enableGrandTotal= {false}></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>

{% endhighlight %}

![](GrandTotal-Hiding_images/enableGrandTotal.png)