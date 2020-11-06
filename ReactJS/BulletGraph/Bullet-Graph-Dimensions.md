---
layout: post
title: Bullet-Graph-Dimensions
description: bullet graph dimensions
platform: js
control: BulletGraph	
documentation: ug
api: /api/js/ejbulletgraph
---

# Bullet Graph Dimensions

This section explains you on how to change the dimensions of the **Bullet Graph**. You can change various dimensions and properties of **Bullet Graph** like width, height, quantitative scale length, qualitative range size etc. By default, **Bullet Graph** uses 595 pixel width and 90 pixel height. You can customize width and height of a **Bullet Graph** using **width** and **height** properties of **Bullet Graph** respectively.

## Size

{% highlight javascript %}

"use strict";

ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	width={850}
	height={540}
    >        
            
    </EJ.BulletGraph>,
	document.getElementById('bulletgraph')
);



{% endhighlight %}



In the above code example, width is set as 500 pixel and height is set as 100 pixel. The output of the above code example with dimension 500 * 100 is as follows.

![](/js/BulletGraph/Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img1.png) 

## Value for performance bar

The feature measure bar value is customized using the **value** property. Default value of this property is 0.

{% highlight javascript %}

"use strict";

ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	value={5}
    >        
            
    </EJ.BulletGraph>,
		  document.getElementById('bulletgraph')
);


{% endhighlight %}



The following screenshot displays **Bullet Graph** with a performance measure value of 5.

![](/js/BulletGraph/Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img2.png)

## Comparative measure value

The **Comparative measure value** is set using **comparativeMeasureValue** property. The default value of this property is 0.

{% highlight javascript %}

"use strict";

ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	comparativeMeasureValue= {5}
    >        
            
    </EJ.BulletGraph>,
		  document.getElementById('bulletgraph')
);



{% endhighlight %}



The following screenshot displays **Bullet Graph** with comparative measure value of 5.

![](/js/BulletGraph/Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img3.png)

## Theme

**Bullet Graph Theme** is customized using **theme** property. Default value is **flatlight. Bullet Graph** supports **flatlight** and **flatdark** themes. **Flatdark** theme improves **Bullet Graph** appearance when background of **Bullet Graph** container uses dark color like black.

{% highlight javascript %}

"use strict";

ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	theme = {"flatdark"}
    >        
            
    </EJ.BulletGraph>,
		  document.getElementById('bulletgraph')
); 



{% endhighlight %}



The following screenshot displays **Bullet Graph** with **flatdark** theme

![](/js/BulletGraph/Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img4.png)

## Orientation

Bullet Graph is oriented either horizontally or vertically using orientation property. Default value of this property is horizontal.

{% highlight javascript %}

"use strict";

ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
    orientation={'vertical'}
    width={100}
    height={550}
    flowDirection={'backward'}
    >        
            
    </EJ.BulletGraph>,
		  document.getElementById('bulletgraph')
);



{% endhighlight %}

## Flow direction

The Flow direction of Bullet Graph is customized using flowDirection property. Default value of this property is forward. Setting forward renders Bullet Graph left to right and backward renders from right to left.

{% highlight javascript %}

"use strict";

ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	comparativeMeasureValue={2}
        flowDirection={'backward'}
    >        
            
    </EJ.BulletGraph>,
		  document.getElementById('bulletgraph')
);



{% endhighlight %}



The following screenshot displays **Bullet Graph** in a backward direction.

![](/js/BulletGraph/Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img5.png) 

## Qualitative range size

Size of the Qualitative range is customized using qualitativeRangeSize property. Default value of this property is 32.

{% highlight javascript %}

"use strict";

ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	qualitativeRangeSize={50}
    >        
            
    </EJ.BulletGraph>,
		  document.getElementById('bulletgraph')
);


{% endhighlight %}



The following screenshot displays **Bullet Graph** with Qualitative range of size 50

![](/js/BulletGraph/Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img6.png) 

## Quantitative scale length

Length of the **Quantitative****scale** is customized using **quantitativeScaleLength** property. Default value of this property is 475.

{% highlight javascript %}

"use strict";

ReactDOM.render(
    <EJ.BulletGraph id="bulletCore0"
	quantitativeScaleLength={500}
    >        
            
    </EJ.BulletGraph>,
		  document.getElementById('bulletgraph')
);
{% endhighlight %}



The following screenshot displays **Bullet Graph** with Quantitative scale length of 500.

![](/js/BulletGraph/Bullet-Graph-Dimensions_images/Bullet-Graph-Dimensions_img7.png) 

