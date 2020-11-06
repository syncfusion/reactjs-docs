---
layout: post
title: Customizing the appearance of Essential JavaScript Chart
description: Learn how to customize the appearance of Chart using palettes, themes, color, background and animation. 
platform: js
control: Chart
documentation: ug
api : /api/js/ejchart
---

# Appearance

## Custom Color Palette

The Chart displays different series in different colors by default. You can customize the color of each series by providing a custom color palette of your choice by using the [`palette`](../api/ejchart#members:palette) property. 

{% highlight javascript %}

"use strict";
		//Providing a custom palette
        var palette= [ "grey", "skyblue", "orange", ];

        // ...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			palette={palette}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Appearance_images/Appearance_img1.png)


N> The Color palette is applied to the points in accumulation type series

## Built-in Themes

Following are the built-in themes available in the Chart

* flatlight
* flatdark
* gradientlight
* gradientdark
* azure
* azuredark
* lime
* limedark
* saffron
* saffrondark
* gradient-azure
* gradient-azuredark
* gradient-lime
* gradient-limedark
* gradient-saffron
* gradient-saffrondark


You can set your desired theme by using the [`theme`](../api/ejchart#members:theme) property. Flat light is the default theme used in the Chart.

{% highlight javascript %}

"use strict";
        //Using gradient theme
        var theme= "gradientlight";
        
        // ...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			theme={theme}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Appearance_images/Appearance_img2.png)


## Point level customization

Marker, data label and fill color of each point in a series can be customized individually by using the [`points`](../api/ejchart#members:series-points) collection.

{% highlight javascript %}

"use strict";
        var series= [{
             //Customizing marker and fill color of a point
                  points: [
                      {  
                         x : 0,
                         y: 210, 
                         fill: "#E27F2D",
                         marker: { 
                              visible: true,
                              // ...
                            }
                      },
                    // ...
                   ],         
              // ...
         }];
         // ...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			series={series}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Appearance_images/Appearance_img3.png)

## Series border customization

To customize the series border color, width and dashArray, you can use [`series.border`](../api/ejchart#members:series-border) option. 

N> Series border can be applied to all the series (except Line, Spline, HiLo, HiLoOpenClose and StepLine series).

{% highlight javascript %}

"use strict";
        //...
        var series= [{
               
             //Change the color, width and dashArray to customize the border of series
             border: { color: "blue", width: 2, dashArray: "5,3" }
             //...
        }];
        
        //...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			series={series}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Appearance_images/Appearance_img4.png)

## Chart area customization

### Customize chart background

The Chart background can be customized by using the [`background`](../api/ejchart#members:background) property of the Chart. To customize the chart border, use [`border`](../api/ejchart#members:border) option of the chart. 

{% highlight javascript %}

"use strict";
        // ...
        
        //Customizing Chart background
        var background= "skyblue";
          
        //Customize the chart border and opacity
        var border= {color: "#FF0000", width: 2, opacity: 0.35};
                  
        // ...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			background={background}
			border={border}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %} 

![](/js/Chart/Appearance_images/Appearance_img5.png)


**Chart Margin**

The Chart [`margin`](../api/ejchart#members:margin) property is used to add the margin to the chart area at the left, right, top and bottom position.

{% highlight javascript %}

"use strict";
        // ...
        
        //Change chart margin to left, right, top and bottom
        var margin= { left: 40, right: 40, top: 40, bottom: 40 };
                  
        // ...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			margin={margin}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %} 

![](/js/Chart/Appearance_images/Appearance_img6.png)

**Setting background image**

Background image can be added to the chart by using the [`backGroundImageUrl`](../api/ejchart#members:backgroundimageurl) property.

{% highlight javascript %}

"use strict";
        // ...
        
        //Setting an image as Chart background 
        var backGroundImage= "images/chart/wheat.png";
                  
        // ...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			backGroundImageUrl={backGroundImage}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %} 

![](/js/Chart/Appearance_images/Appearance_img7.png)

[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/chartcustomization/tooltiptemplate) here to view our online demo sample for setting Chart background image.


**Chart area background**

The Chart area background can be customized by using the [`background`](../api/ejchart#members:chartarea-background) property in the chart area. 

{% highlight javascript %}

"use strict";
        var chartArea= {            
              //Setting background for Chart area
              background: "skyblue"
        };    
                   
         // ...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			chartArea={chartArea}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %} 

![](/js/Chart/Appearance_images/Appearance_img8.png)


### Customize chart area grid bands

You can provide different color for alternate grid rows and columns formed by the grid lines in the chart area by using the [`alternateGridBand`](../api/ejchart#members:primaryxaxis-alternategridband) property of the axis. The properties [`odd`](../api/ejchart#members:primaryxaxis-alternategridband-odd) and [`even`](../api/ejchart#members:primaryxaxis-alternategridband-even) are used to customize the grid bands at odd and even positions respectively. 

{% highlight javascript %}

"use strict";
        // ...
        
        //Creating horizontal grid bands in chart area
        var primaryYAxis= {            
        
           //Customizing horizontal grid bands at even position
           alternateGridBand: {                 
               even: {
                        fill: "#A7A9AB", 
                        opacity: 0.1,
                      }  }
               // ...               
        };
        // ...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			primaryYAxis={primaryYAxis}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %} 

![](/js/Chart/Appearance_images/Appearance_img9.png)

[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/chartaxes/alternategridband) here to view the alternate grid band online demo sample.


### Animation

You can enable animation by using the [`enableAnimation`](../api/ejchart#members:series-enableanimation) property of the series. This animates the chart series on two occasions – when the chart is loaded for the first time or whenever you change the series type by using the type property.

{% highlight javascript %}

"use strict";
        // ...
        
        var series = [{
        
             //Enabling animation of series
             enableAnimation: true,    
        
             // ...    
        }];
        // ...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			series={series}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

However, you can force the chart to animate series by calling the animate method as illustrated in the following code example,

{% highlight javascript %}

"use strict";
        // ...
        
        var series = [{
        
             //Enabling animation of series
             enableAnimation: true,    
        
             // ...    
        }];
        // ...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			series={series}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);

      //Dynamically animating Chart
      function animateChart(){

           //Calling the animate method for dynamic animation
           $("#chartcontainer").ejChart("animate");      
        
      }


{% endhighlight %}

### Control the Speed of animation

To control the speed of animation, you can use the [`animationDuration`](../api/ejchart#members:series-animationduration) property in the series. 

{% highlight javascript %}

"use strict";
        // ...
        
        var series = [{
        
             //Enabling animation of series
             enableAnimation: true, 
             animationDuration:"2000"   
        
             // ...    
        }];
        // ...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			series={series}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}


