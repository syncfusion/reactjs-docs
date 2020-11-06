---
layout: post
title: Globalization-And-Localization
description: Globalization And Localization
platform: js
control: RangeNavigator
documentation: ug
---


### Globalization & Localization

**RangeNavigator** supports Localization and Globalization to customize the labels based on a culture specific to a country. The culture defines specific information for the number formats, week and month names, date and time formats etc. 

#### Localization

**Localization** is the process of customizing the user interface based on a culture specific to a particular country or region in order to display regional data.  The culture is represented by a unique string, for example, ―en-US‖ for U.S. English and ―fr-FR‖ for French (common), this is achieved by creating a JavaScript file “**rangeNavigatorSource.fr-FR.js**” and setting the equivalent word as illustrated in the following code sample.



{% highlight html %}

ej.datavisualization.RangeNavigator.locale["fr-FR"] = {

    intervals: {
        //string to display the intervals on RangeNavigator
        quarter: {longQuarters: "Trimestre", shortQuarters: "T"},
        week: { longWeeks: "Semaine", shortWeeks: "S" }
    }
}


{% endhighlight %}

**Localization** is the key feature that provides solutions globally with the help of localized control. 

{% highlight javascript %}
"use strict";
var rangeSettings = {
                    start: "2010/1/1", end: "2010/12/31"
};        

ReactDOM.render(
                <EJ.RangeNavigator id="rangenavigator1"  locale = 'fr-FR' 
                rangeSettings = {rangeSettings} ></EJ.RangeNavigator>,                    
                document.getElementById('rangenavigator')
);


{% endhighlight %}



![](/js/RangeNavigator/Globalization-And-Localization_images/Globalization-And-Localization_img1.png) 

#### RTL

**Right-to-Left** or **RTL** describes the ability of application to handle and responds you to communicate with a right-to-left language, like Arabic or Japanese. **enableRTL** property is used to change the rendering format  to **"Right to Left"**, by default it renders from **"Left to Right"** in **RangeNavigator**.

{% highlight html %}

"use strict";
var rangeSettings = {
                    start: "2010/1/1", end: "2010/12/31"
};        

ReactDOM.render(
            <EJ.RangeNavigator id="rangenavigator1" enableRTL ={true} locale = 'fr-FR' 
             rangeSettings = {rangeSettings} ></EJ.RangeNavigator>,                    
            document.getElementById('rangenavigator')
);




{% endhighlight %}



![](/js/RangeNavigator/Globalization-And-Localization_images/Globalization-And-Localization_img2.png) 



