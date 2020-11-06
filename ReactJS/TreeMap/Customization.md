---
layout: post
title: Customization
description: customization
platform: js
control: TreeMap
documentation: ug
---

# Customization

**TreeMap** control supports color customization to determine the exact combination of colors for tree nodes displayed in **TreeMap** and tooltip support to display additional information of treemap data.

## Color

You can customize the colors of the leaf nodes of **TreeMap** using the ColorMapping support of the **TreeMap**. 

ColorMapping is categorized into three different types such as,

* uniColorMapping
* rangeBrushColorMapping
* desaturationColorMapping

### Uni Color Mapping

You can color, all the leaf nodes with the same color by setting the `color` value of the `uniColorMapping` property of the **TreeMap**.

{% highlight js %}

"use strict";

var uniColorMapping = { color: "Crimson" };

ReactDOM.render(
    <EJ.TreeMap id="treemap1" uniColorMapping = {uniColorMapping}> </EJ.TreeMap>,
    document.getElementById('treemaps')
);



{% endhighlight %}



![](/js/TreeMap/Customization_images/Customization_img1.png)

### Range Color Mapping

You can group the leaf nodes based on the range of the data’s color values. You can set a unique color for every ranges. To achieve this, specify the `to` and `from` values as range bound and `color` value to fill the leaf nodes of the particular range, through the `rangeColorMapping` property of the **TreeMap**.

{% highlight js %}

"use strict";

var rangeColorMapping = [
                        { color: "#77D8D8", from: "0", to: "1" },
                        { color: "#AED960", from: "0", to: "2" },
                        { color: "#FFAF51", from: "0", to: "3" },
                        { color: "#F3D240", from: "0", to: "4" }
];
ReactDOM.render(
    <EJ.TreeMap id="treemap1" rangeColorMapping = {rangeColorMapping}></EJ.TreeMap>,
    document.getElementById('treemaps')
);



{% endhighlight %}



![](/js/TreeMap/Customization_images/Customization_img2.png)

### Desaturation Color Mapping

You can differentiate all the leaf nodes using the `desaturationColorMapping` property of the **TreeMap**. Differentiation is achieved, even though same color is applied for all the leaf nodes by varying the opacity of the leaf nodes based on the color value specified in the color value range using `rangeMinimum` and `rangeMaximum` value of the data collection. You can also bound the opacity range by setting `from` and `to` property of the `desaturationColorMapping`.

{% highlight js %}


"use strict";
var desaturationColorMapping = {
                        color: "DeepSkyBlue", from: "1", to: "0.2", rangeMinimum: "0",  
                        rangeMaximum: "4"                        
};
ReactDOM.render(
    <EJ.TreeMap id="treemap1" desaturationColorMapping = {desaturationColorMapping}></EJ.TreeMap>,
    document.getElementById('treemaps')
);





{% endhighlight %}



![](/js/TreeMap/Customization_images/Customization_img3.png)

## Tooltip

You can enable the tooltip support for the TreeMap by setting the `showTooltip` property to true. By default, it takes the property of the bound object that is referred to in the groupPath and displays its content when the corresponding node is tapped. The `tooltipTemplate` is a **HTML** element that is used to expose the custom template for the tooltip.

## Leaf Item Setting

You can customize the **Leaf level TreeMap items** using `leafItemSettings`. The Label and tooltip values take the property of bound object that is referred in the `labelPath` when defined.

You can specify the border color using `BorderBrush` property.

* For customizing border thickness, you can use `BorderThickness` property.

* To customize the gap between the leaf items, you can use `Gap` property.

* You can specify the label template for the leaf item using `ItemTemplate` property.

* The Label and tooltip values take the property of bound object that is referred in the `LabelPath` when defined.

* You can specify the position of the leaf labels using `LabelPosition` property.

* You can control the mode of label visibility of the labels using `LabelVisibilityMode` property.

* To show or hide the visibility of the leaf item labels you can use `ShowLabels` property.

* For specifying over flow action of left item labels you can use `TextOverflow` property.


{% highlight js %}
   
"use strict";
var leafItemSettings = { labelPath: "Region" };
ReactDOM.render(
    <EJ.TreeMap id="treemap1" leafItemSettings = {leafItemSettings} 
    showTooltip = {true}></EJ.TreeMap>,
    document.getElementById('treemaps')
);

   
{% endhighlight %}



![](/js/TreeMap/Customization_images/Customization_img4.png)


### Border Brush

You can able to customize the border color of the treemap using the property `BorderBrush`. 

{% highlight js %}

"use strict";
ReactDOM.render(
    <EJ.TreeMap id="treemap1" borderBrush = "white"></EJ.TreeMap>,
    document.getElementById('treemaps')
);

{% endhighlight %}

### Border Thickness

For customizing the border thickness of the treemap, you can use the `BorderThickness` property.

{% highlight js %}

"use strict";
ReactDOM.render(
    <EJ.TreeMap id="treemap1" borderThickness = {1}></EJ.TreeMap>,
    document.getElementById('treemaps')
);

{% endhighlight %}

## Dock Position

You can position the legend at top, bottom, left and right side of the treemap as per your requirement. For changing the position as per your requirement, you can use `DockPosition` property.

<ts name="ej.datavisualization.TreeMap.DockPosition"/>
Specifies the dockPosition for legend



{% highlight js %}

 "use strict";
ReactDOM.render(
    <EJ.TreeMap id="treemap1" dockPosition = "top"></EJ.TreeMap>,
    document.getElementById('treemaps')
);

{% endhighlight %}

### Clicking and Dragging

You can select the single treemap element on click and drag. To click and drag treemap items, you have to enable the `draggingOnSelection` property.

{% highlight js %}

"use strict";
ReactDOM.render(
    <EJ.TreeMap id="treemap1" draggingOnSelection = {false}></EJ.TreeMap>,
    document.getElementById('treemaps')
);

{% endhighlight %}

For selecting the group element of treemap while clicking and dragging, you can use `draggingGroupOnSelection` property.

{% highlight js %}

"use strict";
ReactDOM.render(
    <EJ.TreeMap id="treemap1" draggingGroupOnSelection = {false}></EJ.TreeMap>,
    document.getElementById('treemaps')
);

{% endhighlight %}

### Fill with Gradient

You can customize that whether gradient color have to be applied for treemap or not. This can be customized using the property `enableGradient`.

{% highlight js %}

"use strict";
ReactDOM.render(
    <EJ.TreeMap id="treemap1" enableGradient = {true}></EJ.TreeMap>,
    document.getElementById('treemaps')
);

{% endhighlight %}

### Responsive Treemap

You can customize whether treemap have to be responsive or not while resizing the container. For making treemap responsive you can use `enableResize` or `isResponsive` property.

{% highlight js %}

"use strict";
ReactDOM.render(
    <EJ.TreeMap id="treemap1" enableResize = {true}></EJ.TreeMap>,
    document.getElementById('treemaps')
);

{% endhighlight %}

### GroupColorMapping

You can customize the color of the each group using `GroupColorMapping` property. To use group color mapping, kindly specify `GroupID` and `RangeColorMapping` inside the `GroupColorMapping`. 

{% highlight js %}

"use strict";
var groupColorMapping={
//..
};
ReactDOM.render(
    <EJ.TreeMap id="treemap1" groupColorMapping = {groupColorMapping}></EJ.TreeMap>,
    document.getElementById('treemaps')
);
  
{% endhighlight %}

### GroupSelectionMode

You can specifies the selection mode of the treemap using `groupSelectionMode` property. You can set either group selection mode value as `Default` or  `Multiple`. 

{% highlight js %}

"use strict";
ReactDOM.render(
    <EJ.TreeMap id="treemap1" groupSelectionMode = {true}></EJ.TreeMap>,
    document.getElementById('treemaps')
);

{% endhighlight %}

### Header

You can specify the header for the parent item using the property `Header`. This is applicable only for hierarchical data source. 

{% highlight js %}

"use strict";
ReactDOM.render(
    <EJ.TreeMap id="treemap1" header = ""></EJ.TreeMap>,
    document.getElementById('treemaps')
);

{% endhighlight %}

### Specifying HierarchicalDatasource

You can specify whether data source bound for the treemap is hierarchical or not using the property `IsHierarchicalDatasource`.

{% highlight js %}

"use strict";
ReactDOM.render(
    <EJ.TreeMap id="treemap1" isHierarchicalDatasource = {true}></EJ.TreeMap>,
    document.getElementById('treemaps')
);

{% endhighlight %}

### Treemap Items

You can specify the treemap items which you want to display in the treemap using the property `TreeMapItems`.

{% highlight js %}

"use strict";
var treeMapItems={
//..
};
ReactDOM.render(
    <EJ.TreeMap id="treemap1" treeMapItems = {treeMapItems}></EJ.TreeMap>,
    document.getElementById('treemaps')
);

{% endhighlight %}


