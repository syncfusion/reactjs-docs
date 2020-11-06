---
layout: post
title: UserInteraction
description: How to enable and cutomize the scrollbar, selection and highlighting in Essential JavaScript RangeNavigator.
platform: js
control: RangeNavigator
documentation: ug
---

# User Interactions

## Highlight

EjRangeNavigator provides highlighting supports to the intervals on mouse hover. To enable the highlighting option, set the [`enable`](../api/ejrangenavigator#members:navigatorstylesettings-highlightsettings-enable) property to true in the [`highlightSettings`](../api/ejrangenavigator#members:navigatorstylesettings-highlightsettings) of [`navigatorStyleSettings`](../api/ejrangenavigator#members:navigatorstylesettings).

{% highlight html %}

"use strict";
var rangeSettings = {
                    start: "2010/1/1", end: "2010/12/31"
};
var navigatorStyleSettings ={
                //...        
              highlightSettings:{
                   // enable the highlight settings
                   enable: true                                
              }    
              //...
};

ReactDOM.render(
            <EJ.RangeNavigator id="rangenavigator1" navigatorStyleSettings={navigatorStyleSettings} rangeSettings = {rangeSettings} ></EJ.RangeNavigator>,
                    
             document.getElementById('rangenavigator')
    );

{% endhighlight %}


![](/js/RangeNavigator/User-Interactions_images/User-Interactions_img1.png) 


[Click](http://js.syncfusion.com/demos/web/#!/azure/rangenavigator/highlight) here to view the highlight and selections online demo sample.

### Customize the highlight style

To customize the highlighted intervals, use color, border and opacity options in the [`highlightSettings`](../api/ejrangenavigator#members:navigatorstylesettings-highlightsettings).

{% highlight html %}

"use strict";
var rangeSettings = {
                    start: "2010/1/1", end: "2010/12/31"
};
var navigatorStyleSettings ={
                //...        
              highlightSettings:{
                   // enable the highlight settings
                   enable: true  ,
                     color: '#006fa0',       
                    border:{
                        color: 'red' , width: 2
                      } 
              }    
              //...
};

ReactDOM.render(                    
            <EJ.RangeNavigator id="rangenavigator1" navigatorStyleSettings={navigatorStyleSettings} rangeSettings = {rangeSettings}></EJ.RangeNavigator>,
                    
            document.getElementById('rangenavigator')
        );



{% endhighlight %}

![](/js/RangeNavigator/User-Interactions_images/User-Interactions_img2.png)


## Selection

EjRangeNavigator provides selection supports to the intervals by, clicking and dragging the highlighted intervals. To enable the selection option, set the [`enable`](../api/ejrangenavigator#members:navigatorstylesettings-selectionsettings-enable) property to true in the [`selectionSettings`](../api/ejrangenavigator#members:navigatorstylesettings-selectionsettings).

{% highlight html %}
"use strict";
var rangeSettings = {
                    start: "2010/1/1", end: "2010/12/31"
};
var navigatorStyleSettings ={
                //...        
         selectionSettings:{
                   // enable the selection settings
                   enable: true 			 
                             
              }  

              //...
};

ReactDOM.render(
            <EJ.RangeNavigator id="rangenavigator1" navigatorStyleSettings={navigatorStyleSettings} rangeSettings = {rangeSettings} ></EJ.RangeNavigator>,
                    
            document.getElementById('rangenavigator')
        );


{% endhighlight %}


![](/js/RangeNavigator/User-Interactions_images/User-Interactions_img3.png) 


[Click](http://js.syncfusion.com/demos/web/#!/azure/rangenavigator/highlight) here to view the highlight and selections online demo sample.

### Customize the selection style

To customize the selected intervals, use color, border and opacity options in the selectionSettings.

{% highlight html %}

"use strict";
var rangeSettings = {
                    start: "2010/1/1", end: "2010/12/31"
};
var navigatorStyleSettings ={
                //...        
         selectionSettings:{
                   // enable the selection settings
                   enable: true ,
			color: '#27e8e5',       
                    border:{
                         color: 'red' , width: 2
                       } 
                             
              }  

              //...
};

ReactDOM.render(
            <EJ.RangeNavigator id="rangenavigator1" navigatorStyleSettings={navigatorStyleSettings} rangeSettings = {rangeSettings} ></EJ.RangeNavigator>,
                    
            document.getElementById('rangenavigator')
);



{% endhighlight %}

![](/js/RangeNavigator/User-Interactions_images/User-Interactions_img4.png)


## Scrollbar

* To render the Scrollbar in RangeNavigator, you need to enable [`enableScrollbar`](../api/ejrangenavigator#members:enablescrollbar) option.
 
* [`scrollRangeSettings`](../api/ejrangenavigator#members:scrollrangesettings) of  rangenavigator [`start`](../api/ejrangenavigator#members:scrollrangesettings-start) and [`end`](../api/ejrangenavigator#members:scrollrangesettings-end) value is used to set the minimum and maximum datasource value to be added in the rangenavigator.
 
* Based on the scrollRangeSettings *start, end* value and dataSource *start, end* value scrollbar will be adjust.

* When you change the scrollbar position, [`scrollEnd`](../api/ejrangenavigator#events:scrollend) event returns the current position of start and end range value.

{% highlight html %}

"use strict";
var scrollRangeSettings= {
               start: new Date(2010, 0, 1),
               end: new Date(2011, 10, 31)
};
var rangeSettings = {
                    start: "2010/1/1", end: "2010/12/31"
};

ReactDOM.render(
            <EJ.RangeNavigator id="rangenavigator1" enableScrollbar =  {true}
            scrollRangeSettings = {scrollRangeSettings}  rangeSettings = {rangeSettings}></EJ.RangeNavigator>,
                    
            document.getElementById('rangenavigator')
);


{% endhighlight %}

![](/js/RangeNavigator/User-Interactions_images/User-Interactions_img5.png)

[Click](http://js.syncfusion.com/demos/web/#!/azure/rangenavigator/scrollbar) here to view scrollbar online demo sample.