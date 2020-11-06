---
layout: post
title: Map-Providers
description: map providers
platform: js
control: Maps
documentation: ug
---

# Map Providers

**Map** control support map providers such as OpenStreetMap that can be added to any layers in maps.

## Open Street Map

OpenStreetMap is a map of the entire world. The OpenStreetMap allows you to view, edit and use geographical data in a collaborative way from any place on the Earth.

### Enable OSM

You can enable this feature by setting the `layerType` property value as "OSM".

{% highlight javascript %}

"use strict";

 var layers= [{
                layerType: 'osm',
                urlTemplate:'http://a.tile.openstreetmap.org/level/tileX/tileY.png'              
}]; 
            
        
 
ReactDOM.render(                  
                <EJ.Map id="map1" layers = {layers} ></EJ.Map>,
                    
                document.getElementById('maps')
);


{% endhighlight %}

### URL Template

The `urlTemplate` property determines the format of tile map. You can specify the template for the tile layer. 

![](/js/Maps/Map-Providers_images/Map-Providers_img1.png)

## Bing Map

Bing Map is a key feature in accessing the external geospatial imagery services for deep-zoom satellite view. 

### Enable Bing Maps

You can enable this feature by defining the `layerType` as “bing”.

{% highlight javascript %}

"use strict";

 var layers= [{
                layerType: 'bing',
                bingMapType:"AerialWithLabel",   
                key:'// …bingMapKey'             
}]; 
            
        
 
ReactDOM.render(                  
                <EJ.Map id="map1" layers = {layers} ></EJ.Map>,
                    
                document.getElementById('maps')
);



{% endhighlight %}

### Key

The bing Map key is provided as input to this `key` property. The Bing Map key can be obtained from [http://www.microsoft.com/maps/create-a-bing-maps-key.aspx](http://www.microsoft.com/maps/create-a-bing-maps-key.aspx).

![](/js/Maps/Map-Providers_images/Map-Providers_img2.png)

