---
layout: post
title: Levels
description: Learn how to customize various levels in SunburstChart
platform: ts
control: SunburstChart
documentation: ug
---

## Levels

Sunburst chart is used to display hierarchical data. You can add more than one hierarchical data by using the [`levels`](../api/ejsunburstchart#members:levels) property of Sunburst chart. Each level of the hierarchy is represented by circle.
The following code snippet illustrates 

{% highlight js %}

"use strict";
 var levels = [
            {
                //... to represent the hierarchical data in different levels 
                   }
            ];
 ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    levels ={levels}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);



{% endhighlight %}

## GroupMemberPath

{% highlight js %}

"use strict";
var levels = [
        { groupMemberPath: "Level 1" },
            { groupMemberPath: "Level 2" },
            { groupMemberPath: "Level 3" },
            ];
ReactDOM.render(
    <EJ.SunburstChart id = "sunburst1"      
    levels ={levels}    
    >                  
    </EJ.SunburstChart>,
          document.getElementById('sunburst')
);


{% endhighlight %}

The following screenshot illustrates the Sunburst Chart with different levels



![](/js/SunburstChart/Levels_images/Levels_img1.png)
