---
layout: post
title: Chart Striplines
description: Learn how to add horizontal or vertical lines in Chart.                                                  
platform: js
control: Chart
documentation: ug
api : /api/js/ejchart
---

# Striplines

EjChart supports horizontal and vertical striplines. 

## Horizontal Stripline

You can create horizontal stripline by adding the [`stripline`](../api/ejchart#members:primaryyaxis-stripline) in the **vertical axis** and set [`visible`](../api/ejchart#members:primaryxaxis-stripline-visible) option to **true**. Striplines are rendered in the specified **start** to **end** range and you can add more than one stripline for an axis.


{% highlight javascript %}

"use strict";
          //Initializing Primary Y Axis
        var primaryYAxis= {
               // ...
                stripLine: [
                     //Create horizontal Stripline using vertical Axis
                     {
                       //Enable Stripline
                       visible: true,
                       start: 30,
                       end: 40,
                      },
                      // ...
                   ],
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

![](/js/Chart/Striplines_images/Striplines_img1.png)


[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/chartaxes/striplines) here to view the Striplines online demo sample.


## Vertical Stripline

You can create vertical stripline by adding the [`stripline`](../api/ejchart#members:primaryxaxis-stripline) in the **horizontal axis** and set [`visible`](../api/ejchart#members:primaryyaxis-stripline-visible) option to **true**.  


{% highlight javascript %}

"use strict";
          // ...

          //Initializing Primary X Axis
          var primaryXAxis: {
               // ...
                stripLine: [
                     //Create vertical Stripline using horizontal Axis
                       {
                         //Enable Stripline
                         visible: true,
                         start: 3,
                         end: 7,
                       },
                     // ...
                     ],
                };

             // ...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			primaryXAxis={primaryXAxis}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Striplines_images/Striplines_img2.png)


## Customize the Text

To customize the stripLine text, use the [`text`](../api/ejchart#members:primaryyaxis-stripline-text) and [`font`](../api/ejchart#members:primaryyaxis-stripline-font) options. 

{% highlight javascript %}

"use strict";
          // ...

          //Initializing Primary Y Axis
          var primaryYAxis= {
               // ...
                stripLine: [{
                  //Customize the stripLine text and font styles
                   text: 'High Temperature',
                   font: { size: '18px', color: 'white' }      
                   // ...                         
               }],
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

![](/js/Chart/Striplines_images/Striplines_img3.png)
	

**Text Alignment**

Stripline text can be aligned by using the [`textAlignment`](../api/ejchart#members:primaryyaxis-stripline-textalignment) property.  

{% highlight javascript %}

"use strict";
        // ...

        //Initializing Primary Y Axis
        var primaryYAxis= {
               // ...
                stripLine: [{
                    //Set stripLine text alignment to top position
                    textAlignment: 'middletop',        
                   // ...                         
               }]
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

![](/js/Chart/Striplines_images/Striplines_img4.png)


## Customize the Stripline

To customize the stripLine styles, use the [`color`](../api/ejchart#members:primaryyaxis-stripline-color), [`opacity`](../api/ejchart#members:primaryyaxis-stripline-opacity), [`borderWidth`](../api/ejchart#members:primaryyaxis-stripline-borderwidth) and [`borderColor`](../api/ejchart#members:primaryyaxis-stripline-bordercolor) properties. 

{% highlight javascript %}

"use strict";
        //Initializing Primary Y Axis
        var primaryYAxis= {
               // ...
                stripLine: [{
                         //Customize the StripLine rectangle
                         color: '#33CCFF',
                         borderWidth: 2,
                         opacity: 0.5,
                         borderColor: 'red',  
                         // ...
                       }],
           };
        // ...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			primaryYAxis={primaryYAxis}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		)


{% endhighlight %}

![](/js/Chart/Striplines_images/Striplines_img5.png)


## Change the Z-order of the stripline

Stripline [`zIndex`](../api/ejchart#members:primaryyaxis-stripline-zindex) property is used to display the stripLine either behind or over the series.  

{% highlight javascript %}

"use strict";
          // ...

        //Initializing Primary Y Axis
        var primaryYAxis= {
               // ...
                stripLine: [{
                        //Change stripLine zIndex
                        zindex: 'over',
                        // ...
                       }],
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

![](/js/Chart/Striplines_images/Striplines_img6.png)
