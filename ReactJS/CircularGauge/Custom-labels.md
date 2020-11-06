---
layout: post
title: Custom-labels
description: custom labels
platform: js
control: Circular Gauge
documentation: ug
api: /api/js/ejcirculargauge
---

# Custom labels

Custom labels are the texts that you can use them in any location of the **Gauge**.

## Adding Custom Label Collection

Custom labels collection is directly added to the scale object. Refer the following code to add custom labels collection in a **Gauge** control.

{% highlight javascript %}

"use strict";
Adding Custom Label Collection
var scales = [{
        showCustomLabels: true,
        customLabels: [{
            color: "Red"
        }]                
    }];
ReactDOM.render(
            <ej.circulargauge id="circulargauge1" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );


{% endhighlight %}



**Basic Customization**

You can customize custom labels using the properties such as **textAngle**, **color** and **font**. **textAngle** attribute is used to display the custom labels in the specified angles and **color** attribute is used to display the custom labels in specified color. 

You can use **Value** attribute to set the text value in the custom labels. To display the custom labels, set **showCustomLabels** as ‘true’. To set the location of the custom label in **Circular Gauge**, **location** property is used. By using **x** and **y** axis you can adjust the position of the custom labels.

Font option is also available on  custom labels. The basic three properties of fonts such as size, family and style can be achieved by **size**, **fontStyle** and **fontFamily** attributes. 

{% highlight javascript %}

"use strict";
var scales = [{
        size: 10,
        shadowOffset: 10,
        showCustomLabels: true,
        showRanges: true,
        showScaleBar: true,
        radius: 150, size: 2,
        customLabels: [{
            //For setting custom label text angle
            textAngle: 10,
            //For setting custom label color
            color: "Red",
            //For setting custom label value
            value: "CustomLabel1",
            //For setting custom label font option
            font: {
                size: "18px",
                fontFamily: "Arial",
                fontStyle: "bold"
            },
            position: { x: 180, y: 100 }
        }]
    }];
ReactDOM.render(
            <ej.circulargauge id="circulargauge1" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );



{% endhighlight %}




Execute the above code to render the following output.

![](/js/CircularGauge/Custom-labels_images/Custom-labels_img1.png)

## Multiple Custom Labels

You can set multiple custom labels in a single **Circular Gauge** by adding an array of custom label objects. Refer the following code example for multiple custom label functionality.

{% highlight javascript %}

"use strict";
var scales = [{
        size: 10,
        shadowOffset: 10,
        showCustomLabels: true,
        showRanges: true,
        showScaleBar: true,
        radius: 150, size: 2,
        customLabels: [
        //custom label1
        {
            textAngle: 10,
            color: "Red",
            value: "CustomLabel1",
            font: {
                size: "18px",
                fontFamily: "Arial",
                fontStyle: "bold"
            },
            position: { x: 180, y: 100 }
        },
        //custom label2
        {
            textAngle: 10,
            color: "Green",
            value: "CustomLabel2",
            font: {
                size: "18px",
                fontFamily: "Arial",
                fontStyle: "bold"
            },
            position: { x: 180, y: 250 }
        }]        
    }];
ReactDOM.render(
            <ej.circulargauge id="circulargauge1" scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );



{% endhighlight %}


Execute the above code to render the following output.

![](/js/CircularGauge/Custom-labels_images/Custom-labels_img2.png)

## Outer Custom Label

**Outer Custom Label** is used to show custom labels outside the **gauge** control. The **Outer Custom Label** can be positioned with API called **outerCustomLabelPosition.** The value for this API is enumerable type and its possible values are,

* Right

* Left

* Top

* Bottom

When a custom label is to be displayed as an **Outer Custom Label**, set the API **customLabelType** as Outer. Refer to the following code example to get the **Outer Custom Label**.


{% highlight javascript %}

"use strict";
var scales = [{
        showLabels: true,
        radius: 150,
        // Customizes the custom label options.
        customLabels: [{
            value: "Average Speed",
            position: { x: 360, y: 30 },
            color: "Red",
            font: {
                size: "18px",
                fontFamily: "Arial",
                fontStyle: "bold"
            },
            positionType: "outer",
        }],
        pointers: [{
            value: 60,
            length: 100,
        }]
    }];
    var tooltip = {
        // Enables the custom label tooltip.
        showCustomLabelTooltip: true,
    };
ReactDOM.render(
            <ej.circulargauge id="circulargauge1" tooltip={tooltip} outercustomlabelposition="right"
                              scales={scales}></ej.circulargauge>,

            document.getElementById('circulargauge')
            );


{% endhighlight %}



Execute the above code to render the following output.

![](/js/CircularGauge/Custom-labels_images/Custom-labels_img3.png)

