---
layout: post
title: Drill-Down-Support
description: drill down support
platform: js
control: TreeMap
documentation: ug
---

# Drill Down Support

**Treemap** enables drill down to expose the hierarchy achieved by clicking on a node and this results in enabling the **Treemap** to move to the next level or sub level and can return back to the normal **Treemap** view by clicking on the node header. Only a single level of the **Treemap** is visible at once.

## Enable Drill Down

**Treemap** elements can be drilled down by setting the `enableDrillDown` property to true. You can view the hierarchy of the **Treemap** by clicking on the treemap items and can move to the previous level by clicking on the drill down header. The header color can be customized by changing the values in the property `drillDownHeaderColor` and the selection color can be done by changing the `drillDownSelectionColor` property.

<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th></tr>
<tr>
<td>
enableDrillDown</td><td>
bool</td><td>
Gets or sets a value that indicates whether the drill down feature is enabled or not</td></tr>
<tr>
<td>
drillDownHeaderColor</td><td>
string</td><td>
Gets or sets a color for header during drill down</td></tr>
<tr>
<td>
drillDownSelectionColor</td><td>
string</td><td>
Gets or sets a color for highlighting tree map item during drill down.</td></tr>
</table>


{% highlight js %}

"use strict";
 var uniColorMapping = { color: "#CCDFE3" };
 var levels= [{ 
            groupPath: "Continent",
            groupGap:5,
            showLabels: true,
            headerHeight: 25, 
            showHeader: true 
}];
ReactDOM.render(
    <EJ.TreeMap id="treemap1" dataSource = {population_data}  enableDrillDown = {true} drillDownHeaderColor = "#199DAF" drillDownSelectionColor = "#199DAF" 
    uniColorMapping = {uniColorMapping}  weightValuePath = "Population" 
    levels = {levels}></EJ.TreeMap>,
    document.getElementById('treemaps')
);



{% endhighlight %}



![](/js/TreeMap/Drill-Down-Support_images/Drill-Down-Support_img1.png)

_Before Drill Down_

![](/js/TreeMap/Drill-Down-Support_images/Drill-Down-Support_img2.png)

_After Drill Down_

