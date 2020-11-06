---
layout: post
title: Chart Title
description: How to customize the chart title.
platform: js
control: Chart
documentation: ug
api : /api/js/ejchart
---

# Chart Title & Subtitle

## Title

By using the title option, you can add the [`text`](../api/ejchart.html#members:title-text) as well as customize its [`border`](../api/ejchart.html#members:title-border),  [`background`](../api/ejchart.html#members:title-background) color and [`font`](../api/ejchart.html#members:title-font).

{% highlight javascript %}

"use strict";
             // ... 
             var title= { 
                  //Adding text to chart title
                 text: 'Efficiency of oil-fired power production ', 
                  //Change the title text background color
                 background : "lightblue",
                  //Customizing Chart title border
                border: { 
                           color: "blue",
                           width: 2,
                           opacity: 0.5 ,
                           cornerRadius : 4
                         },
 
                  //Customizing Chart title font 
                 font:{ 
                         opacity: 1,
                         fontFamily: "Arial",
                         fontStyle: 'italic',
                         fontWeight: 'regular',
                         color: "#E27F2D",
                         size: '23px' 
                     },
               }; 
        // ... 
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			title={title}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);

{% endhighlight %}

![](/js/Chart/Chart-Title_images/Chart-Title_img1.png)


[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/chartcustomization/subtitle) here to view the Chart Title online demo sample.


We can trim, wrap and wrapAndTrim to the chart title using textOverflow property. The original text will be displayed as tooltip on mouse hover.


{% highlight javascript %}

"use strict";
             // ... 
             var title= { 
                 text: 'Efficiency of oil-fired power production ',
                 //To enable the title trim, wrap and wrapandtrim
                enableTrim: true,
                 //Setting maximum width to the title
                maximumWidth: 150,
                 //To trim the title
                textOverflow: "trim",
               }; 
        // ... 
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			title={title}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Chart-Title_images/Chart-Title_img5.png)


### Title Alignment

You can change the title alignment to *center*, *far* and *near* by using the [`textAlignment`](../api/ejchart.html#members:title-textalignment) property of the chart title. 

{% highlight javascript %}

"use strict";
        // ... 
        var title= {                
			//Change title text alignment
            textAlignment: "near",
            //...
        }; 
        // ... 
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			title={title}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %} 

![](/js/Chart/Chart-Title_images/Chart-Title_img2.png)


## Add Subtitle to the chart

By using the subTitle option, you can add the [`subTitle`](../api/ejchart.html#members:title-subtitle) to the chart title and customize its [`border`](../api/ejchart.html#members:title-subtitle-border),  [`background`](../api/ejchart.html#members:title-subtitle-background) color and [`font`](../api/ejchart.html#members:title-subtitle-font). 

{% highlight javascript %}

"use strict";
        // ... 
        var title={
              // ... 
             subTitle: { 
                       //Add subtitle to chart title 
                        text: "( in a week )", 
                      //Change the title text background color
                        background : "lightblue",
                      //Customizing Chart subtitle border
                        border: { 
                                  color: "blue",
                                  width: 2,
                                  opacity: 0.2 ,
                                  cornerRadius : 4
                       },
        
                       //Customizing Chart subtitle font 
                          font:{ 
                                 opacity: 1, 
                                 fontFamily: "Arial", 
                                 fontStyle: 'italic',
                                 fontWeight: 'regular', 
                                 color: "#E27F2D", 
                                 size: '12px' 
                            }, 
                          } 
                       } 
              // ... 
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			title={title}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);

{% endhighlight %}

![](/js/Chart/Chart-Title_images/Chart-Title_img3.png)

We can trim, wrap and wrapAndTrim to the chart subtitle using textOverflow property. The original text will be displayed as tooltip on mouse hover.

{% highlight javascript %}

"use strict";
        // ...

        var title= {
        
            // ...
            subTitle:{
                text: '( in a week )', 
                //To enable the sub-title trim, wrap and wrap and trim
                enableTrim: true,
                //Setting maximum width to the sub-title
                maximumWidth: 50,
                //To trim the sub-title
                textOverflow: "wrap",
            },
        };
        
        //  ...
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			title={title}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Chart-Title_images/Chart-Title_img6.png)

### Subtitle Alignment

You can change the subtitle alignment to *center*, *far* and *near* by using the [`textAlignment`](../api/ejchart.html#members:title-subtitle-textalignment) property of the subTitle.

{% highlight javascript %}

"use strict";
        //  ...  
        var title= {                
             // ...
             subTitle:{
                 //Change subtitle to text aligment
                 textAlignment: "center",		
                 // ...
               }
         };
            
        //  ... 
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			title={title}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Chart-Title_images/Chart-Title_img4.png)

