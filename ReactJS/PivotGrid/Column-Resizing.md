---
title:  Column Resizing
description: column resizing
platform: React JS
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Column Resizing

Allows you to resize the column by changing its width while holding and dragging the column border using the mouse.

You can enable column resizing option in PivotGrid by setting the [`enableColumnResizing`](/api/js/ejpivotgrid#members:enablecolumnresizing) property to true.

{% highlight html %}

<script type="text/babel">
    //...
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" enableColumnResizing= {true}></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>

{% endhighlight %} 

![](Column-Resizing_images/columnresizing.png)