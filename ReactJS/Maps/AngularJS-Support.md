---
layout: post
title: AngularJS-Support
description: angularjs support
platform: js
control: Maps
documentation: ug
---

# AngularJS Support

**AngularJS** is a **JavaScript** Framework added to a **HTML** page with a **&lt;script&gt;** tag. It extends **HTML** attributes with directives and binds data to **HTML** with expressions. **AngularJS** directives allow you to specify custom and reusable **HTML** tags that moderate the behavior of certain elements. **Angular binding** uses directives to plug its action into the page. Directives, all prefaced with ng-, are placed in **HTML** attributes. To know more about **Angular binding** refer  
to: <https://help.syncfusion.com/js/angularjs>

Apply the plugin and property assigning the Map element through the directive that starts with the letter “e-“.  The following code illustrates how to bind data to the Map component through Angular support.

{% highlight html %}

    //References to be added for angular support.
        
        <script src=" https:/ajax.googleapis.com/ajax/libs/angularjs/1.0.1/angular.min.js"></script>
        
        <script src=" http://cdn.syncfusion.com/js/ej.widget.angular-latest.min.js"></script>

    //Initializes controller
    
        <body ng-controller="Map">

    //Initializes Map
    
        <div id="map" style="height: inherit; min-height: 356px;" ej-map e-zoomsettings- enablezoom="nenablezoom">
            <div e-layers>
                <div e-layer e-shapedata="nshapedata" e-shapesettings-fill="nfill" e-shapesettings-strokeThickness="nstrokeThickness" e-shapesettings-stroke="nstroke">                                   
                </div>
            </div>
        </div>
         
    //Renders a textbox to change the color value
    
    <div>
        Shape Color:  <input type="text" id="Text11" ng-model="nfill" style="width: 110px">
    </div> 

    <script>
        angular.module('syncApp', ['ejangular'])
        .controller('Map', function ($scope) {                       
            $scope.nenablezoom = true,
            $scope.nshapedata = usMap;                    
            $scope.nfill = "#9CBF4E"; 
            $scope.nstrokeThickness ="0.5";
            $scope.nstroke = "White";
        });
    </script>     

{% endhighlight %}



![](/js/Maps/AngularJS-Support_images/AngularJS-Support_img1.png)





