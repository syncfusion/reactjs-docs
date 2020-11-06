---
layout: post
title: Highlight
description: What are the different modes of highlight present in the Sunburst Chart
platform: ts
control: Sunburst Chart
documentation: ug
---

# Highlight 
EjSunburstChart provides highlighting support for the points on mouse hover. To enable the highlighting , set the [`enable`](../api/ejsunburstchart#members:highlightsettings-enable) property to true in the [`highlightSettings`](../api/ejsunburstchart#members:highlightsettings). 

{% highlight js %}
"use strict";
 var highlightSettings = { enable: true };
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    highlightSettings ={highlightSettings}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);

{% endhighlight %}

![](/js/SunburstChart/Highlight_images/Highlight_img1.png)

 
## Highlight Display mode

 You can customize the highlighted segment appearance by using color or opacity. You can choose between color or opacity using the [`type`](../api/ejsunburstchart#members:highlightsettings-type) property in the highlight Settings.

*	HighlightByColor – To display the highlighted segment appearance using color.
*	HighlightByOpacity – To display the highlighted segment appearance using opacity.

{% highlight js %}

"use strict";
 var highlightSettings = { enable: true, type:"color",color:"red" };
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    highlightSettings ={highlightSettings}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);



 {% endhighlight %}

![](/js/SunburstChart/Highlight_images/Highlight_img2.png)

## Highlight Mode

Sunburst chart provides multiple options to represent the highlighted categories. You can highlight the segment categories by using the [`mode`](../api/ejsunburstchart#members:highlightsettings-mode) property in highlightSettings

*	Child – To highlight the child of selected parent.
*	All – To highlight the entire categories in group.
*	Parent – To highlight the parent of selected child.
*	Single - To highlight single item in the category.

### Child

The following code shows how to set the highlight type as child 

{% highlight js %}

"use strict";
 var highlightSettings = { enable: true,mode:"child" };
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    highlightSettings ={highlightSettings}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);

{% endhighlight %}

![](/js/SunburstChart/Highlight_images/Highlight_img3.png)
 
### Parent

The parent mode can be enabled by using the below code 

{% highlight js %}

"use strict";
 var highlightSettings = { enable: true,mode:"parent"};
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    highlightSettings ={highlightSettings}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);

{% endhighlight %}

![](/js/SunburstChart/Highlight_images/Highlight_img4.png)
 
### Point

To highlight the particular segment, the point mode of the highlight settings is used.

{% highlight js %}

"use strict";
 var highlightSettings = { enable: true,mode:"point"};
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    highlightSettings ={highlightSettings}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);

 {% endhighlight %}

![](/js/SunburstChart/Highlight_images/Highlight_img5.png)
 
### All

The following code snippet is used for the all mode of highlight settings

{% highlight js %}
"use strict";
var highlightSettings = { enable: true,mode:"all"};
ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    highlightSettings ={highlightSettings}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);



{% endhighlight %}

![](/js/SunburstChart/Highlight_images/Highlight_img6.png)

[Click](http://js.syncfusion.com/demos/web/#!/bootstrap/sunburst/selection) here to view the online demo sample of Highlight  in  the Sunburst Chart
