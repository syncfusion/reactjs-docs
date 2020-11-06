---
layout: post
title: User-Interaction
description: user interaction
platform: js
control: Maps
documentation: ug
---

# User Interaction

Options like zooming, panning, and map selection enables the effective interaction on Map elements.

## Map Selection

Each shape in the Map can be selected and deselected during interaction with the shapes. 

The `selectionColor` property is used to get or set the selected shape color. The `selectionStroke` and `selectionStrokeWidth` properties are used to customize the selected shape border.

You can select the shape by tapping the shape. The Single selection is enabled by the `enableSelection` property of shape layer. When `enableSelection` is set to false, the shapes cannot be selected. 

{% highlight javascript %}

"use strict";

 var layers = [{
               shapeData: usMap,
               shapeSettings: {
                            fill: "#9CBF4E",
                            strokeThickness: "0.5",
                            stroke: "White",
                            selectionStrokeWidth: 2,
                            selectionStroke:"white",
                            selectionColor: "#BC5353"
                        },
                        enableSelection: true
}];             
        
ReactDOM.render(
                    <EJ.Map id="map1" layers = {layers}></EJ.Map>,
                    
                     document.getElementById('maps')
);



{% endhighlight %}

{% include image.html url="/js/Maps/User-Interaction_images/User-Interaction_img1.png"%}

## MultiSelection


This feature enables you to select multiple Map shapes on mouse taps accompanied by the "**Control**" key press. To enable this feature, set the `selectionMode` property as "**multiple**" along with the `enableSelection` property.

{% highlight javascript %}

"use strict";

 var layers = [{
               shapeData: usMap,
                        // ...
                        enableSelection: true,
                        selectionMode: "multiple",
                        // ..
}];             
        
ReactDOM.render(
                     <EJ.Map id="map1" layers = {layers}></EJ.Map>,
                    
                     document.getElementById('maps')
);



{% endhighlight %}

{% include image.html url="/js/Maps/User-Interaction_images/User-Interaction_img5.png"%}


## Dragging On Selection

This feature enables you to select the shapes by dragging over the shapes. While dragging over the shapes, a rectangle is generated and the shapes that comes within the rectangle is selected.
You can enable this feature by setting the `draggingOnSelection` property in the `layers` to **true**.

{% highlight javascript %}

"use strict";

 var layers = [{
                        // ...                        
                        draggingOnSelection: true
                        // ...
}];             
        
ReactDOM.render(
                     <EJ.Map id="map1" layers = {layers}></EJ.Map>,
                    
                     document.getElementById('maps')
);



{% endhighlight %}


![](User-Interaction_images/User-Interaction_img1.png)


## Zooming

The zooming feature enables you to zoom in and out the Map to show in-depth information. It is controlled by the `level` property of the Map. When the zoom level of the Map control is increased, the Map is zoomed in. When the zoom level is decreased, then the Map is zoomed out.

### Properties

The following properties are related to the zooming feature of the **Maps** control:

1. level

2. enableZoom

3. minValue

4. maxValue

### Level

The `level` property determines the Map’s scale size when zooming. The default value of `level` is 1. 

N> level cannot be less than 1

### EnableZoom

The `enableZoom` property enables or disables the zooming feature. 

### MinValue

The `minValue` property is used to set the minimum zoom level of the Map. 

### MaxValue

The `maxValue` property is used to set the maximum zoom level of the Map.

{% highlight javascript %}

"use strict";

 var layers= [
                {
                    shapeData: usMap,
               shapeSettings: {
                            fill: "#9CBF4E",
                            strokeThickness: "0.5",
                            stroke: "White",
                            selectionStrokeWidth: 2,
                            selectionStroke:"white",
                            selectionColor: "#BC5353"
                        },
                      
                }]; 
var zoomSettings = {
                    enableZoom: true,
                    minValue: 1,
                    maxValue: 20,
                    level: 1
                };
                
        
ReactDOM.render(
                    <EJ.Map id="map1" layers = {layers} zoomSettings = {zoomSettings}></EJ.Map>,
                    
                     document.getElementById('maps')
                     );
                      


{% endhighlight %}

### Additional Options to Zoom the Map

Maps can be zoomed by using the following options also,

* Zoom method.
* mouse scroll.
* mouse double tap.
* shape selection
* Position

### Zoom method

You can zoom the Maps by using `zoom` method. The `zoom` method contains parameter zoom value. The Map can be zoomed or scaled based on zoom value parameter.

{% highlight javascript %}
 
        $("#map").ejMap("zoom", 2);


{% endhighlight %}

### Mouse scroll

You can zoom the Map with mouse events by using mouse scroll. When the mouse is scrolled up, the Map is zoomed in and when the mouse is scrolled down, the Map is zoomed out.

### Mouse double tap

When the Map is double-tapped by using mouse, the zoom in operation is performed. 

![](User-Interaction_images/User-Interaction_img2.png)

### Shape Selection

Map shape is zoomed to the whole Map area on the shape selected. Animation can be applied for that zooming by using the `enableAnimation` property as true. 

You can enable this feature by setting `enableZoomOnSelection` property value as ‘_true_’. 

When `enableZoomOnSelection` property is set to true, then zooming by double click is muted.

{% highlight javascript %}

"use strict";

 var layers= [
                {
                    shapeData: usMap,
               shapeSettings: {
                            fill: "#9CBF4E",
                            strokeThickness: "0.5",
                            stroke: "White",
                            selectionStrokeWidth: 2,
                            selectionStroke:"white",
                            selectionColor: "#BC5353"
                        },
                      
}]; 
var zoomSettings = {
                    enableZoomOnSelection: true
                };
                
        
ReactDOM.render(
                    <EJ.Map id="map1" layers = {layers} zoomSettings = {zoomSettings></EJ.Map>,
                    
                     document.getElementById('maps')
                     );
                      


{% endhighlight %}

### Positioning

Depending on the latitude and longitude, you can zoom the Map to the exact position. All locations are considered as latitude and longitude values and the exact location is considered as Map coordinates.

The `navigateTo` is a method that allows you to zoom the Map control to the given location. This method contains three attributes as follows.

<table>
<tr>
<th>
Attribute</th><th>
Type</th><th>
Description</th></tr>
<tr>
<td>
Latitude</td><td>
Double</td><td>
Latitude point of the position </td></tr>
<tr>
<td>
Longitude</td><td>
Double</td><td>
Longitude point of the position</td></tr>
<tr>
<td>
level</td><td>
Double</td><td>
Zoom level of the map</td></tr>
</table>


{% highlight html %}

    <script type="text/javascript">
        function buttonClick() {
            $("#map").ejMap("navigateTo", 13, 80, 5);
        }
    </script> 

{% endhighlight %}

## Panning

The panning feature enables the Map navigation. The `enablePan` property is used to enable or disable the panning support.

{% highlight javascript %}

"use strict";

 var layers= [
                {
                    shapeData: usMap,
               shapeSettings: {
                            fill: "#9CBF4E",
                            strokeThickness: "0.5",
                            stroke: "White",
                            selectionStrokeWidth: 2,
                            selectionStroke:"white",
                            selectionColor: "#BC5353"
                        },
                       enablePan: true
                }]; 
                
        
ReactDOM.render(    
                    <EJ.Map id="map1" layers={layers} ></EJ.Map>,
                    
                     document.getElementById('maps')
);
	

{% endhighlight %}

### Factor

Specifies the zoom factor for map zoom value, you can use `factor` property.

{% highlight javascript %}

 ReactDOM.render(    
                    <EJ.Map id="map1" factor={1} ></EJ.Map>,
                    
                     document.getElementById('maps')
);


{% endhighlight %}


## Navigation Control

**Navigation** control is built-in with **Maps** control. With Navigation control, **Maps** can be panned in any direction and zoomed. It is possible to show or hide the NavigationControl by `enableNavigation` property.


![](User-Interaction_images/User-Interaction_img3.png)



{% highlight javascript %}

"use strict";

 var layers= [
                {
                    shapeData: usMap,
               shapeSettings: {
                            fill: "#9CBF4E",
                            strokeThickness: "0.5",
                            stroke: "White",
                            selectionStrokeWidth: 2,
                            selectionStroke:"white",
                            selectionColor: "#BC5353"
                        },
                       enablePan: true
                }]; 
 var navigationControl ={enableNavigation:true};
                
        
 
ReactDOM.render(                  
                    <EJ.Map id="map1" layers={layers} navigationControl = {navigationControl} ></EJ.Map>,
                    
                     document.getElementById('maps')
                     );
                      



{% endhighlight %}

### Positions

The Navigation control can be positioned in two ways.

* Absolute Position
* Dock Position

#### Absolute Position

Based on the margin values of X and Y-axes, the navigation control can be positioned with the help of the **x** and **y** properties available in `absolutePosition`. For positioning the navigation control based on margins corresponding to a Map, `dockPosition` value is set as ‘_none_’.

#### Dock Position

The navigation control can be positioned in the following locations within the container.

* topLeft
* topCenter
* topRight
* centerLeft
* center
* centerRight
* bottomLeft
* bottomRight
* bottomCenter
* bottomRight
* none

You can set this option by using `dockPosition` property in `navigationControl`.

{% highlight javascript %}

"use strict";

 var layers= [
                {
                    shapeData: usMap,
               shapeSettings: {
                            fill: "#9CBF4E",
                            strokeThickness: "0.5",
                            stroke: "White",
                            selectionStrokeWidth: 2,
                            selectionStroke:"white",
                            selectionColor: "#BC5353"
                        },
                       enablePan: true
                }]; 
 var navigationControl ={
     enableNavigation:true,
     orientation:'vertical',
     absolutePosition:{
         x:5,
         y:16
    },
     dockPosition:'none'
};
                
    
ReactDOM.render(                   
                    <EJ.Map id="map1" layers = {layers} 
                    navigationControl = {navigationControl} ></EJ.Map>,
                    
                     document.getElementById('maps')
                     );


{% endhighlight %}


#### Orientation

Set the `orientation` value for navigation control.


{% highlight javascript %}

var navigationControl ={
     enableNavigation:true,
     orientation:'vertical',
     absolutePosition:{
         x:5,
         y:16
    },
     dockPosition:'none'
};
                
    
ReactDOM.render(                   
                    <EJ.Map id="map1"  
                    navigationControl = {navigationControl} ></EJ.Map>,
                    
                     document.getElementById('maps')
                     );
   	
   
{% endhighlight %}

#### Content


Specifies the navigation control template for map, you can use `content` property.


{% highlight html %}
 
var navigationControl ={
     enableNavigation:true,
     orientation:'vertical',
     absolutePosition:{
         x:5,
         y:16
    },
     dockPosition:'none',
     content:''
};
                
    
ReactDOM.render(                   
                    <EJ.Map id="map1"  
                    navigationControl = {navigationControl} ></EJ.Map>,
                    
                     document.getElementById('maps')
                     );

{% endhighlight %}



### Animation

 **Animation** is enabled or disabled using `enableAnimation`property. 

{% highlight javascript %}

ReactDOM.render(                   
                    <EJ.Map id="map1"  
                    enableAnimation = {true} ></EJ.Map>,
                    
                     document.getElementById('maps')
                     );

{% endhighlight %}


#### Enable Layer Change Animation 

Enables or Disables the animation for layer change in map, you can use `enableLayerChangeAnimation` property and the default value is false.


{% highlight javascript %}
 


ReactDOM.render(                   
                    <EJ.Map id="map1"  
                    enableLayerChangeAnimation = {true} ></EJ.Map>,
                    
                     document.getElementById('maps')
                     );



{% endhighlight %}


### Responsiveness during browser resize

**Map** is made responsive when resizing the browser by using `isResponsive` property.

{% highlight javascript %}


ReactDOM.render(                   
                    <EJ.Map id="map1"  
                    isResponsive = {true} ></EJ.Map>,
                    
                     document.getElementById('maps')
                     );

{% endhighlight %}







