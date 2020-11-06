---
title: Grouping-Bar
description: grouping bar
platform: React JS
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Grouping Bar

## Initialization 
Grouping Bar allows user to dynamically alter the report by filter and remove operations in the PivotGrid control. Based on the OLAP datasource and report bound to the PivotGrid control, Grouping Bar will be automatically populated. You can enable Grouping Bar option in PivotGrid by setting the [`enableGroupingBar`](/api/js/ejpivotgrid#members:enablegroupingbar) property to true.

{% highlight html %}

<script type="text/babel">
    //...
    $(function(){
    ReactDOM.render(
        <EJ.PivotGrid id="Olap" dataSource= {Olap_dataSource} enableGroupingBar={true}></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
    );
    });
</script>

{% endhighlight %}

![](Grouping-Bar_images/olapclientgroupingbar.png)

## Drag and Drop

You can alter the report on fly through drag-and-drop operation.

![](Grouping-Bar_images/GBar_Olap.png)

## Context Menu

You can also alter the report by using context menu.

![](Grouping-Bar_images/CMenu_Olap.png)

## Searching Values
Search option available in Grouping Bar allows you to search a specific value that needs to be filtered from the list of values inside the filter pop-up window.

![](Grouping-Bar_images/OlapClntFiltering.png)

![](Grouping-Bar_images/olapclientsearching.png)

## Filtering Values
Filtering option available in Grouping Bar allows you to select a specific set of values that needs to be displayed in the PivotGrid control. At least one value needed to be in checked state while filtering otherwise “Ok” button will be disabled.

![](Grouping-Bar_images/OlapClntFiltering.png)

![](Grouping-Bar_images/olapclientfiltering.png)

## Removing Field
Remove option available in the Grouping Bar allows you to completely remove a specific field from the PivotGrid control. Remove operation can be either achieved by clicking remove icon available inside each field or by dragging and dropping field out of Grouping Bar region.

![](Grouping-Bar_images/Olapclientremove.png)

![](Grouping-Bar_images/OlapAFRemoving.png)


