---
layout: post
title: Legend
description: legend for ranges in the Circular Gauge 
platform: js
control: Circular Gauge
documentation: ug
api: /api/js/ejcirculargauge
---

# Legend

The legend contains the list of the ranges that appear in the circular gauge  

## Legend Visibility

By default, the legend will not be displayed in the circular gauge. You can enable or disable it by using the [`visible`](../api/ejcirculargauge#members:legend-visible) property of the legend.

{% highlight javascript %}

var legend = {
	visible: true
}
ReactDOM.render(
    <EJ.CircularGauge id="default"  legend={legend}
    >
	
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);



{% endhighlight %}

![](/js/CircularGauge/Legend_images/Legend_img1.png)


[Click](http://js.syncfusion.com/demos/web/#!/flatlight/radialgauge/legend) here to view the online demo sample for  legend in the circular Gauge.

### Legend Text

The text displayed in the legend can be customized by using the **legendText** property present in the ranges of the circular gauge. When the legendText is not specified in the ranges, then the legend item for that particular range will not displayed. By default the legendText value is **null** . 

{% highlight javascript %}

// ...             
var ranges= [{
     legendText:"Light air",			
}]
//...

// ... 
ReactDOM.render(
    <EJ.CircularGauge id="default"  ranges={ranges}
    >
	
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);

{% endhighlight %}


### Legend Fill and Opacity

You can change the opacity and fill color of legend text using `Opacity` and `Fill` property of legend. 

{% highlight javascript %}

var legend = {
	visible: true,
    fill:'blue',
    opacity:0.5
}
ReactDOM.render(
    <EJ.CircularGauge id="default"  legend={legend}
    >
	
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);



{% endhighlight %}

## Position and Align the Legend

By using the [`position`](../api/ejcirculargauge#members:legend-position) property, you can position the legend at *left*, *right*, *top* or *bottom* of the CircularGauge. The legend is positioned at the **bottom** of the circular gauge, by default.

{% highlight javascript %}

// ...             
var legend= {
    // ...  
    //Place the legend at top of the circular gauge
    position: 'top',

}
// ...      
ReactDOM.render(
    <EJ.CircularGauge id="default"  legend={legend}
    >
	
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}

![](/js/CircularGauge/Legend_images/Legend_img2.png)

### Legend Alignment

You can align the legend to the *center*, *far* or *near* based on its position by using the [`alignment`](../api/ejcirculargauge#members:legend-alignment) property.

{% highlight javascript %}


// ...             
var legend= {
    //...
    //The below two settings will place the legend at the top-right corner of the circular gauge.
    alignment: 'far',
    position: 'top', 
}
// ...      
ReactDOM.render(
    <EJ.CircularGauge id="default"  legend={legend}
    >
	
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}

![](/js/CircularGauge/Legend_images/Legend_img3.png)

## Customization

### Legend shape

To change the legend item shape, you have to specify the desired shape in the [`shape`](../api/ejcirculargauge#members:legend-shape) property of the legend. By default, the shape of the legend is **circle**.It also supports rectangle,diamond,triangle,slider,line,pentagon,trapezoid and wedge shapes.

{% highlight javascript %}


// ...             
var legend= {
    //...
    //Change legend shape
     shape: 'slider',
}
// ...      
ReactDOM.render(
    <EJ.CircularGauge id="default"  legend={legend}
    >
	
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}

![](/js/CircularGauge/Legend_images/Legend_img4.png)


### Legend Item Size and Border

You can change the size of the legend items by using the [`width`](../api/ejcirculargauge#members:legend-itemstyle-width) and [`height`](../api/ejcirculargauge#members:legend-itemstyle-height) properties in the **itemStyle**. To change the legend item border, use [`border`](../api/ejcirculargauge#members:legend-itemstyle-border) property of the legend itemStyle.

{% highlight javascript %}

// ...             
var legend= {
    //...
    //Change legend items border, height and width
    itemStyle: {width: 13, height: 13, border: { color: "#FF0000", width: 2 } },
}
// ...      
ReactDOM.render(
    <EJ.CircularGauge id="default"  legend={legend}
    >
	
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}

![](/js/CircularGauge/Legend_images/Legend_img5.png)

### Legend size

You can change the default legend size by using the **size** property of the legend.  

{% highlight javascript %}


// ...             
var legend= {
    //...
    //Change legend size
    size:{width: '350', height: '100'}
}
// ...      
ReactDOM.render(
    <EJ.CircularGauge id="default"  legend={legend}
    >
	
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}

![](/js/CircularGauge/Legend_images/Legend_img6.png)


### Legend Item Padding

You can control the spacing between the legend items by using the [`itemPadding`](../api/ejcirculargauge#members:legend-itempadding) option of the legend.  The default value is 20. 

{% highlight javascript %}


"use strict";

// ...             
var legend= {
    //...
    //Add space between each legend item
    itemPadding: 30,
}
// ...      
ReactDOM.render(
    <EJ.CircularGauge id="default"  legend={legend}
    >
	
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}

![](/js/CircularGauge/Legend_images/Legend_img7.png)

### Legend border

You can customize the legend border by using the [`border`](../api/ejcirculargauge#members:legend-border) option in the legend. 

{% highlight javascript %}


"use strict";

// ...             
var legend= {
    //...
    //Set border color and width to legend
    border: {color: "#FFC342", width: 2},
}
// ...      
ReactDOM.render(
    <EJ.CircularGauge id="default"  legend={legend}
    >
	
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}

![](/js/CircularGauge/Legend_images/Legend_img8.png)

### Font of the legend text

The font of the legend item text can be customized by using the [`font`](../api/ejcirculargauge#members:legend-font)  property in legend.


{% highlight javascript %}


// ...             
var legend= {
    //...
    //Customize the legend item text
    font: { fontFamily: 'Segoe UI', fontStyle: 'Normal', fontWeight: 'Bold', size: '15px' },
}
// ...      
ReactDOM.render(
    <EJ.CircularGauge id="default"  legend={legend}
    >
	
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}

![](/js/CircularGauge/Legend_images/Legend_img9.png)

## Events

### Legend Item Render

[`LegendItemRender`](../api/ejcirculargauge#events:legenditemrender) event triggers before rendering the legend items. This event is triggered for each legend item in Circular gauge. You can use this event to customize legend item shape or add custom text to legend item dynamically

{% highlight javascript %}

function onLegendRender(sender) {
    //Get legend item details before rendering
    var legendItem = sender.data;

}
ReactDOM.render(
    <EJ.CircularGauge id="default"  
    //Subscribe the legendItemRender event
    legendItemRender={onLegendRender}
    >
	
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);

{% endhighlight %}

### Legend Item Click

You can get the legend item details such as *RangeIndex, bounds and shape* by subscribing the [`legendItemClick`](../api/ejcirculargauge#events:legenditemclick) event of the circular gauge. When the legend item is clicked, it triggers the event and returns the legend information 

{% highlight javascript %}

$("#CircularGauge1").ejCircularGauge({
           
function onLegendClicked(sender) {
    //Get legend item details on legend item click.
    var legendItem = sender.data;
}
ReactDOM.render(
    <EJ.CircularGauge id="default"  
    //Subscribe the legend item click event
    legendItemClick={onLegendClicked}
    >
	
    </EJ.CircularGauge>,
		  document.getElementById('gauge')
);


{% endhighlight %}

