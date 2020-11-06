---
layout: post
title: Qualitative-Range
description: qualitative range
platform: js
control: BulletGraph	
documentation: ug
api: /api/js/ejbulletgraph
---

# Qualitative Range

**Qualitative Range** represents the quality of a specific range in quantitative scale like good, bad and satisfactory. Color for each qualitative range is customized using **rangeStroke** property. The **rangeEnd** property specifies the ending point of the qualitative range. Minimum value of quantitative scale is considered as the starting point of first qualitative range and previous end points are considered as starting point for other qualitative ranges.

{% highlight javascript %}

"use strict";
  var quantitativeScaleSettings = {
        location: { x: 50, y: 20 },
        minimum: 0,
        maximum: 100,
        interval: 10,
        featureMeasures: [
            { value: 55, comparativeMeasureValue: 75, category: "Year 1" },
            { value: 65, comparativeMeasureValue: 70, category: "Year 2" },
            { value: 80, comparativeMeasureValue: 65, category: "Year 3" }
        ]
    };

    var qualitativeRanges = [
       { rangeEnd: 35, rangeStroke: 'darkred', rangeOpacity: 0.5 },
       { rangeEnd: 50, rangeStroke: 'red', rangeOpacity: 1 },
       { rangeEnd: 75, rangeStroke: 'blue', rangeOpacity: 0.7 },
       { rangeEnd: 90, rangeStroke: 'lightgreen', rangeOpacity: 1 },
       { rangeEnd: 100, rangeStroke: 'green', rangeOpacity: 1 }
    ];
ReactDOM.render(
            <ej.bulletgraph id="bulletgraph1"
                 qualitativeRanges={qualitativeRanges}
                 qualitativeRangeSize={80}
                 height={200}
                 quantitativeScaleSettings={quantitativeScaleSettings}>
            </ej.bulletgraph>,
            document.getElementById('bulletgraph')
            );


{% endhighlight %}



The following screenshot displays **Bullet Graph** with different qualitative ranges in different colors. In this image, range 0 to 35 represents bad performance, 35 to 50 represents average performance, 50 to 75 represents that the performance is above average, 75 to 90 represents good performance and above 90 represents excellent performance.

![](/js/BulletGraph/Qualitative-Range_images/Qualitative-Range_img1.png) 

