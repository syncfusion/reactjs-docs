---
layout: post
title: Chart legend
description: How to cutomize the legend in Essential JavaScript Chart.
platform: js
control: Chart
documentation: ug
api : /api/js/ejchart
---

# Legend

The legend contains the list of chart series and Trendlines that appear in a chart. 

## Legend Visibility

By default, the legend is enabled in the chart. You can enable or disable it by using the [`visible`](../api/ejchart#members:legend-visible) option of the legend.

{% highlight javascript %}

"use strict";
		// ...
        var legend= {
            //Visible chart legend
            visible: false
        };
        //...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			legend={legend}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Legend_images/Legend_img1.png)


[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/chartcustomization/legendposition) here to view the online demo sample for legend position.

## Legend title

To add the title to the legend, you have to specify the [`legend.title.text`](../api/ejchart#members:legend-title-text) option.

{% highlight javascript %}

"use strict";
        // ...             
          var legend= {
            //...
            title: {
               //Add title to the chart legend
	           text: "Countries",
		
		     }  };
        
        // ...     
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			legend={legend}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Legend_images/Legend_img2.png)


## Position and Align the Legend

By using the [`position`](../api/ejchart#members:legend-position) option, you can position the legend at *left*, *right*, *top* or *bottom* of the chart. The legend is positioned at the **bottom** of the chart, by default.

{% highlight javascript %}

"use strict";
        // ...             
          var legend= {
            // ...  
            //Place the legend at top of the chart
            position: 'top',
		  };
        
        // ...     
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			legend={legend}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Legend_images/Legend_img3.png)

**Legend Alignment**

You can align the legend to the *center*, *far* or *near* based on its position by using the [`alignment`](../api/ejchart#members:legend-alignment) option.

{% highlight javascript %}

"use strict";
        // ...             
          var legend= {
            //...
            //The below two settings will place the legend at the top-right corner of the chart.
            alignment: 'far',
            position: 'top', 
		  };
        
        // ...     
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			legend={legend}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Legend_images/Legend_img4.png)


## Arrange legend items in the rows and columns

You can arrange the legend items horizontally and vertically by using the [`rowCount`](../api/ejchart#members:legend-rowcount) and [`columnCount`](../api/ejchart#members:legend-columncount) options of the legend.

* When only the [`rowCount`](../api/ejchart#members:legend-rowcount) is specified, the legend items are arranged according to the [`rowCount`](../api/ejchart#members:legend-rowcount) and number of columns may vary based on the number of legend items.

* When only the [`columnCount`](../api/ejchart#members:legend-columncount) is specified, the legend items are arranged according to the [`columnCount`](../api/ejchart#members:legend-columncount) and number of rows may vary based on the number of legend items.

* When both the options are specified, then the one which has higher value is given preference. For example, when the [`rowCount`](../api/ejchart#members:legend-rowcount) is 4 and [`columnCount`](../api/ejchart#members:legend-columncount) is 3, legend items are arranged in 4 rows.

* When both the options are specified and have the same value, the preference is given to the [`columnCount`](../api/ejchart#members:legend-columncount) when it is positioned at the top/bottom position. The preference is given to the [`rowCount`](../api/ejchart#members:legend-rowcount) when it is positioned at the left/right position.
 

{% highlight javascript %}

"use strict";
        // ...             
          var legend= {
                //Arrange legend items in 4 rows and approximately 4 columns. Column couldn’t may vary based on number of items. 
                rowCount: 4,
                columnCount: 4 
		  };
        
        // ...     
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			legend={legend}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Legend_images/Legend_img5.png)


## Customization

### Legend shape

To change the legend icon shape, you have to specify the shape in the [`shape`](../api/ejchart#members:legend-shape) property of the legend. When you want the legend icon to display the prototype of the series, you have to set the **seriesType** as shape.

{% highlight javascript %}

"use strict";
        // ...             
          var legend= {
                //...
                //Change legend shape
                 shape: 'seriesType',
		  };
        
        // ...     
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			legend={legend}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Legend_images/Legend_img6.png)


### Legend items size and border

You can change the size of the legend items by using the [`itemStyle.width`](../api/ejchart#members:legend-itemstyle-width) and [`itemStyle.height`](../api/ejchart#members:legend-itemstyle-height) options. To change the legend item border, use [`border`](../api/ejchart#members:legend-border) option of the legend itemStyle.

{% highlight javascript %}

"use strict";
        // ...             
          var legend= {
                //...
                //Change legend items border, height and width
                itemStyle: {width: 13, height: 13, border: { color: "#FF0000", width: 1 } },
		  };
        
        // ...     
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			legend={legend}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Legend_images/Legend_img7.png)

### Legend size

By default, legend takes 20% of the **height** horizontally when it was placed on the top or bottom position and 20% of the **width** vertically while placing on the left or right position of the chart. You can change this default legend size by using the **size** option of the legend.  

{% highlight javascript %}

"use strict";
        // ...             
          var legend= {
                 //...
                 //Change legend size
                 size:{width: '550', height: '100'}
		  };
        
        // ...     
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			legend={legend}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Legend_images/Legend_img8.png)


### Legend Item Padding

You can control the spacing between the legend items by using the [`itemPadding`](../api/ejchart#members:legend-itempadding) option of the legend.  The default value is 10. 

{% highlight javascript %}

"use strict";
        // ...             
          var legend= {
                //...
                //Add space between each legend item
                itemPadding: 15,
		  };
        
        // ...     
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			legend={legend}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Legend_images/Legend_img9.png)

### Legend border

You can customize the legend border by using the [`border`](../api/ejchart#members:legend-border) option in the legend. 

{% highlight javascript %}

"use strict";
        // ...             
          var legend= {
                //...
                //Set border color and width to legend
                border: {color: "#FFC342", width: 2},
		  };
        
        // ...     
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			legend={legend}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Legend_images/Legend_img10.png)

### Scrollbar for legend

You can enable or disable the legend scrollbar by using the [`enableScrollbar`](../api/ejchart#members:legend-enablescrollbar) option of the legend. When you disable the scrollbar option, the legend does not consider the [`default size`](legend.html#legend-size) and chart draws in the remaining space. If you have specified the **size** to the legend with the scrollbar disabled, then the legends beyond this limit will get clipped. The default value of [`enableScrollbar`](../api/ejchart#members:legend-enablescrollbar) option is **true**.  

{% highlight javascript %}

"use strict";
        // ...             
          var legend= {
                //...
                //Enable scrollbar option in for legend
                enableScrollbar: true,
                size:{width: '430', height: '80'},
		  };
        
        // ...     
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			legend={legend}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Legend_images/Legend_img11.png)

### Customize the legend text

To customize the legend item text and title you can use the [`legend.font`](../api/ejchart#members:legend-font) and [`legend.title`](../api/ejchart#members:legend-title) options. You can change the legend title alignment by using the [`textAlignment`](../api/ejchart#members:legend-title-textAlignment) option of the legend title.

{% highlight javascript %}

"use strict";
        // ...             
          var legend= {
                //...
                //Customize the legend item text
                font: { fontFamily: 'Segoe UI', fontStyle: 'Normal', fontWeight: 'Bold', size: '15px' },
                title: {
                    //...
		            textAlignment: "center",
                    //Customize the legend title text
	                font: { fontFamily: 'Segoe UI', fontStyle: 'Italic', 
                                        fontWeight: 'Bold', size: '12px' },
	             }
		  };
        
        // ...     
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			legend={legend}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Legend_images/Legend_img12.png)

### LegendItems Text Overflow

**Trim**

You can trim the legend item text when its width exceeds the [`legend.textWidth`](../api/ejchart#members:legend-textWidth), by specifying [`textOverflow`](../api/ejchart#members:legend-textOverflow) as **"trim"**. The original text will be displayed on mouse hover.

{% highlight javascript %}

"use strict";
        // ...             
          var legend= {
               //trim the legend text
		        textOverflow: 'trim', 
		        textWidth: 34
		  };
        
        // ...     
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			legend={legend}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Legend_images/Legend_img13.png) 


**Wrap**

By specifying [`textOverflow`](../api/ejchart#members:legend-textOverflow) as **"wrap"**, you can wrap the legend text by word.

![](/js/Chart/Legend_images/Legend_img14.png)

**WrapAndTrim**

You can wrap and trim the legend text by specifying [`textOverflow`](../api/ejchart#members:legend-textOverflow) as **"wrapAndTrim"**. The original text will be displayed on mouse hover.

![](/js/Chart/Legend_images/Legend_img15.png)
   

## Handle the legend item clicked

You can get the legend item details such as *index*, *bounds*, *shape* and *series* by subscribing the [`legendItemClick`](../api/ejchart#events:legenditemclick) event on the chart. When the legend item is clicked, it triggers the event and returns the [`legend information`](../api/ejchart.html#events:legenditemclick). 

{% highlight javascript %}

"use strict";
        // ...             
          var legend= {
               //trim the legend text
		        textOverflow: 'trim', 
		        textWidth: 34
		  };
        
        // ...     
		function onLegendClicked(sender){
			var legendItem = sender.data;
		}
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			legend={legend}
			legendItemClick={onLegendClicked}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);}

{% endhighlight %}


## Series selection on legend item click

You can select a specific series or point while clicking on the corresponding legend item through disabling the [`toggleSeriesVisibility`](../api/ejchart#members:legend-toggleseriesvisibility) option of the legend. The default value of toggleSeriesVisibility option is **true**. To customize the series selection refer to the series [`selection`](../api/ejchart.html#members:series-selectionsettings).

{% highlight javascript %}

"use strict";
        // ...             
          var legend= {
                   //...
                   //Disable series collapsing on legend item clicked
                   toggleSeriesVisibility: false,
		  };
        
        // ... 
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			legend={legend}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);
      

{% endhighlight %}

![](/js/Chart/Legend_images/Legend_img16.png)



## Collapsing legend item

You can collapse the specific series/point legend item displaying in the chart, by setting the [`visibleOnLegend`](../api/ejchart.html#members:series-visibleonlegend) as *"hidden"* in the point or series.

{% highlight javascript %}

"use strict";
//Initializing Series
var series:[{
           points: [{ x: 'Albania', y: 60.1 },
                   //...
                   //Collapse the point's legend item in the legend collection
                   { x: 'New Zealand', y: 82.8, visibleOnLegend:'hidden' }]
    }];
var legend={visible:true};

		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			series={series}
			legend={legend}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);
      
{% endhighlight %}

![](/js/Chart/Legend_images/Legend_img17.png)