---
title:  Frozen Header
description:  frozen header
platform: React JS
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Frozen Header

Allows you to freeze the header of the Grid so that it will be always visible when scrolling the content with a large number of rows or columns providing a precise view.

{% highlight html %}

<div id="PivotGrid1"></div>

<script type="text/babel">
    //...
    var frozenHeaderSettings= {enableFrozenHeaders : true}  //To Freeze the both Row and Column headers
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" frozenHeaderSettings={frozenHeaderSettings}></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>

{% endhighlight %}

![](FrozenHeader_images/row_col_freeze.png)

We can also freeze the row/column headers individually by setting the below properties.

{% highlight html %}

<script type="text/babel">
    //...
    var frozenHeaderSettings= {enableFrozenRowHeaders : true}  //To Freeze the Row headers only
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" frozenHeaderSettings={frozenHeaderSettings}></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>
    
{% endhighlight %}

![](FrozenHeader_images/row_freeze.png)

{% highlight html %}

<script type="text/babel">
    //...
    var frozenHeaderSettings= {enableFrozenColumnHeaders : true}  //To Freeze the Column headers only
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" frozenHeaderSettings={frozenHeaderSettings}></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>

{% endhighlight %}

![](FrozenHeader_images/col_freeze.png)