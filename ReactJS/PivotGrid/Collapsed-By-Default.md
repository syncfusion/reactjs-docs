---
title: Collapse by default
description: Collapse by default
platform: React JS
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Collapse by default

I> This feature is applicable only for Relational datasource.

Allows you to collapse all members displayed in the grid. You can enable collapsing all members by default in PivotGrid by setting [`enableCollapseByDefault`](/api/js/ejpivotgrid#members:enablecollapsebydefault) property to true.

{% highlight html %}
   
<script type="text/babel">
    //..
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="Relational" dataSource= {pivotdataSource} enableCollapseByDefault= {true}></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>

{% endhighlight %}

![](Collapsed-By-Default_images/Collapse-members.png)

