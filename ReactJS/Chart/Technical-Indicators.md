---
layout: post
title: Technical Indicators
description: What are the different types of technical indicators supported in Essential Chart for financial analysis.
platform: js
control: Chart
documentation: ug
api : /api/js/ejchart
---

# Technical Indicators

EjChart control supports 10 types of technical indicators. 

## Bind data to render the indicator

You can bind the series [`dataSource`](../api/ejchart#members:indicators-datasource) to the indicator by setting the specific series name to the indicator by using the [`indicators.seriesName`](../api/ejchart#members:indicators-seriesname) property.

{% highlight javascript %}

"use strict";
        //  ...
        //Initializing Series
        var series=[{
            dataSource: chartData,
            xName: "xDate",
            high: "High",
            low: "Low",
            open: "Open",
            close: "Close", 
            //Set name to series
            name: 'Hilo',
            //  ...
        }];

        //Initializing Indicators    
        var indicators= [{
            //Set Hilo series dataSource to indicator using seriesName
            seriesName: "Hilo",
            //  ...
	    }];
            //  ...	
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			series={series}
			indicators={indicators}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);

{% endhighlight %}


Also, you can add data to the indicator directly by using the [`dataSource`](../api/ejchart#members:indicators-datasource) option of the indicator.  

{% highlight javascript %}

"use strict";
        //Initializing Indicators    
        var indicators= [{
            /Add dataSource to indicator directly
            dataSource: chartData,
            xName: "xDate",
            high: "High",
            low: "Low",
            open: "Open",
            close: "Close",                
            //  ...
	    }];
            //  ...	
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			indicators={indicators}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);

{% endhighlight %}

	
## Indicator Types

### Accumulation Distribution

To create an Accumulation Distribution indicator, set the [`indicators.type`](../api/ejchart#members:indicators-type) as **"accumulationdistribution"**. Accumulation Distribution require **‘volume’** field additionally with the [`dataSource`](../api/ejchart#members:indicators-datasource) to calculate the signal line.

{% highlight javascript %}

"use strict";
        //  ...
        //Initializing Series
        var series=[{
            name: "Hilo",
            dataSource: chartData,
            xName: "xDate",
            high: "High",
            low: "Low",
            open: "Open",
            close: "Close",
            //Add additional volume field to data source for accumulation distribution
            volume: "Volume",
            //  ...
        }];

        //Initializing Indicators    
        var indicators= [{
            seriesName: "Hilo",
            //Set indicator type
            type: "accumulationdistribution", 
            //  ...
	    }];
            //  ...	
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			indicators={indicators}
			series={series}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Technical-Indicators_images/Technical-Indicators_img1.png)

[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/technicalindicators/accumulationdistribution) here to view the Accumulation Distribution indicator online demo sample.


### Average True Range (ATR)

You can create an ATR indicator by setting the [`indicators.type`](../api/ejchart#members:indicators-type) as **"atr"** in the [`indicators`](../api/ejchart#members:indicators). 

{% highlight javascript %}

"use strict";
        //Initializing Indicators    
        var indicators= [{
			//Set indicator type
            type: "atr", 
            //  ...
	    }];
            //  ...	
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			indicators={indicators}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Technical-Indicators_images/Technical-Indicators_img2.png)

[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/technicalindicators/atr) here to view the ATR indicator online demo sample.


### Bollinger Band 

Bollinger Band indicator is created by setting the [`indicators.type`](../api/ejchart#members:indicators-type) as **"bollingerband"**. It contains three lines, namely upper band, lower band and signal line. Bollinger Band default value of the period is 14 and standardDeviations is 2.

{% highlight javascript %}

"use strict";
        //Initializing Indicators    
        var indicators= [{
			//Set indicator type
            type: "bollingerband", 
            //  ...
	    }];
            //  ...	
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			indicators={indicators}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Technical-Indicators_images/Technical-Indicators_img3.png)

[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/technicalindicators/bollingerband) here to view the Bollinger Band indicator online demo sample.


### Exponential Moving Average (EMA)

To render an EMA indicator, you have to set the [`indicators.type`](../api/ejchart#members:indicators-type) as **"ema"**.  

{% highlight javascript %}

"use strict";
        //Initializing Indicators    
        var indicators= [{
			//Set indicator type
            type: "ema", 
            //  ...
	    }];
            //  ...	
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			indicators={indicators}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Technical-Indicators_images/Technical-Indicators_img4.png)

[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/technicalindicators/ema) here to view the EMA indicator online demo sample.


### Momentum 

Momentum Technical indicator is created by setting the [`indicators.type`](../api/ejchart#members:indicators-type) as **"momentum"**. The momentum indicator renders two lines, namely upper band and signal line. Upper band always rendered at the value 100 and the signal line is calculated based on the momentum of the data.

{% highlight javascript %}

"use strict";
        //Initializing Indicators    
        var indicators= [{
			//Set indicator type
            type: "momentum", 
            //  ...
	    }];
            //  ...	
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			indicators={indicators}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Technical-Indicators_images/Technical-Indicators_img5.png)

[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/technicalindicators/momentum) here to view the Momentum indicator online demo sample.


### Moving Average Convergence Divergence (MACD)

To render an MACD indicator, you have to set the [`indicators.type`](../api/ejchart#members:indicators-type) as **"macd"**.  MACD indicator contains MACD line, Signal line and Histogram column. Histogram is used to differentiate MACD and signal line.

{% highlight javascript %}

"use strict";
        //Initializing Indicators    
        var indicators= [{
			//Set indicator type
            type: "macd", 
            //  ...
	    }];
            //  ...	
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			indicators={indicators}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Technical-Indicators_images/Technical-Indicators_img6.png)


[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/technicalindicators/macd) here to view the MACD indicator online demo sample.


#### macdType

By using the [`macdType`](../api/ejchart#members:indicators-macdtype) enumeration property, you can change the MACD rendering as *line*, *histogram* or *both*. 

{% highlight javascript %}

"use strict";
        //Initializing Indicators    
        var indicators= [{
			//Set indicator type
            type: "macd", 
            //Set macd draw type
            macdType: "histogram", 
            //  ...
	    }];
            //  ...	
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			indicators={indicators}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Technical-Indicators_images/Technical-Indicators_img7.png)


### Relative Strength Index (RSI)

To render the RSI indicator, set the [`indicators.type`](../api/ejchart#members:indicators-type) as **"rsi"**. It contains three lines, namely upper band, lower band and signal line. Upper and lower band always render at value 70 and 30 respectively and signal line is calculated based on the **RSI** formula.

{% highlight javascript %}

"use strict";
        //Initializing Indicators    
        var indicators= [{
			//Set indicator type
            type: "rsi",
            //  ...
	    }];
            //  ...	
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			indicators={indicators}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}


![](/js/Chart/Technical-Indicators_images/Technical-Indicators_img8.png)


[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/technicalindicators/rsi) here to view the RSI indicator online demo sample.


### Simple Moving Average (SMA)

To render the SMA indicator, you should specify the [`indicators.type`](../api/ejchart#members:indicators-type) as **"sma"**.  

{% highlight javascript %}

"use strict";
        //Initializing Indicators    
        var indicators= [{
			//Set indicator type
            type: "sma",
            //  ...
	    }];
            //  ...	
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			indicators={indicators}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Technical-Indicators_images/Technical-Indicators_img9.png)


[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/technicalindicators/sma) here to view the SMA indicator online demo sample.


### Stochastic 

For the Stochastic indicator, you need to set the [`indicators.type`](../api/ejchart#members:indicators-type) as **"stochastic"**. The Stochastic indicator renders four lines namely, upper line, lower line, stochastic line and the signal line. Upper line always rendered at value 80 and the lower line is rendered at value 20. Stochastic and Signal Lines are calculated based on the stochastic formula.

{% highlight javascript %}

"use strict";
        //Initializing Indicators    
        var indicators= [{
			//Set indicator type
            type: "stochastic",
            //  ...
	    }];
            //  ...	
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			indicators={indicators}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Technical-Indicators_images/Technical-Indicators_img10.png)


[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/technicalindicators/stochastic) here to view the stochastic indicator online demo sample.


### Triangular Moving Average (TMA)

To render the TMA indicator, you should specify the [`indicators.type`](../api/ejchart#members:indicators-type) as **"tma"**. 

{% highlight javascript %}

"use strict";
        //Initializing Indicators    
        var indicators= [{
			//Set indicator type
            type: "tma",
            //  ...
	    }];
            //  ...	
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			indicators={indicators}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Technical-Indicators_images/Technical-Indicators_img11.png)


[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/technicalindicators/tma) here to view the TMA indicator online demo sample.


## Enable Tooltip 

To display the indicator tooltip, use [`visible`](../api/ejchart#members:indicators-tooltip) option of the [`indicators.tooltip`](../api/ejchart#members:indicators-tooltip). Also, you can change and customize the tooltip color, border, format and font properties similar to the series tooltip.

{% highlight javascript %}

"use strict";
        //Initializing Indicators    
        var indicators= [{
            //  ...
            tooltip: {
                 //Enable tooltip for indicator
                 visible: true
            },
	    }];
            //  ...	
		ReactDOM.render(
			<EJ.Chart id="default_chart_sample_0"
			indicators={indicators}
			>        
            
			</EJ.Chart>,
				document.getElementById('chart')
		);


{% endhighlight %}

![](/js/Chart/Technical-Indicators_images/Technical-Indicators_img12.png)



