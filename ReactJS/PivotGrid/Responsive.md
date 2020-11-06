---
layout: post
title: Responsive
description: responsive
platform: React JS
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Responsive

PivotGrid and PivotTable Field list control supports responsive rendering based on the target device (desktop & tablet) resolution. It supports resolution upto 1024x600. You can enable responsiveness in PivotGrid by setting [`isResponsive`](/api/js/ejpivotgrid#members:isresponsive) property to true. 

On resizing the browser, the PivotTable Field list will get collapse and an icon will appear on the left-hand side of the browser. User can toggle its view and perform UI interaction.

{% highlight html %}

<script type="text/babel">
    //..
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" isResponsive={true}></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>

{% endhighlight %}

![](Responsive_images/normal.png)

_Normal PivotGrid_
{:.caption}

![](Responsive_images/responsive.png)

_Responsive PivotGrid_
{:.caption}

![](Responsive_images/res-schema.png)

_Responsive PivotTable Field List - Collapsed_
{:.caption}

![](Responsive_images/res-schema1.png)

_Responsive PivotTable Field List - Expanded_
{:.caption}

