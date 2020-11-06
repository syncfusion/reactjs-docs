---
layout: post
title: MVVM
description: mvvm
platform: js
control: Digital Gauge
documentation: ug
---

# MVVM

**AngularJS**

**Digital Gauge** contains AngularJS support. It is possible to add object as well as array object in the **Digital Gauge**. The two way binding support is given to the **value** for displaying the text.

## Rendering the Digital Gauge

**ej-DigitalGauge** is the control tag, where ej is tag prefix and **DigitalGauge** is the control name.**Digital Gauge** is rendered with the following code example.

{% highlight html %}

<!--To Render the Digital gauge-->
<!doctype html>
<html ng-app="syncApp">
   <head>
      <!—Refer the necessary script here-->
   </head>
   <body ng-controller="DigitalGauge">
      <ej-digitalgauge id="digitalCore" e-height="500" e-load="loadGaugeTheme">
      </ej-digitalgauge>
      <script type="text/javascript">
         <!—binding the value to the scope variables in application controller-->
         angular.module('syncApp', ['ejangular'])
         .controller('DigitalGauge', function ($scope) {
             $scope.nvalue = “text”;
         });
      </script>
   </body>
</html>



{% endhighlight %}



Execute the above code to render the following output.

![](/js/DigitalGauge/MVVM_images/MVVM_img1.png)

## Adding the Digital Gauge Items

**Digital Gauge** is rendered with the following code example. You can extend the Object in the array collection such as, **position**, **characterSetting**, **segmentSetting**, etc. with hyphen in the same tag.

**Example**: e-position-x. 

{% highlight html %}

<!--To Render the Digital gauge-->
<ej-digitalgauge id="digitalCore">
   <!--Adding Item collection to the digital gauge-->
   <e-items>
      <e-item e-segmentSettings-width="1" e-segmentSettings-spacing="0"
         e-value="Syncfusion" e-characterSetting-opacity="0.8"
         e-position-x="52" e-position-y="52"></e-item>
   </e-items>
</ej-digitalgauge>



{% endhighlight %}

Finally while running the above codes, the following output will be rendered.

![](/js/DigitalGauge/MVVM_images/MVVM_img2.png)

## Two Way Binding

**Digital Gauge** supports the two way biding for the property **value** as mentioned earlier. Following code example explains how to achieve the two way binding to the **Digital Gauge**.

{% highlight html %}

<!doctype html>
<html ng-app="syncApp">
   <head>
      <meta charset="utf-8">
      <!—Refer the necessary script here-->
   </head>
   <body ng-controller="DigitalGauge">
      Type here <input type="text" id="txtValue" **ng-model="nvalue"** Style="width:110px"/>
      <ej-digitalgauge id="digitalCore" e-height="200" e-load="loadGaugeTheme">
         <e-items>
            <e-item e-segmentSettings-width="1" e-segmentSettings-spacing="0"
               e-characterSetting-opacity="0.8" e-position-x="52"
               e-value="nvalue" e-position-y="52"></e-item>
         </e-items>
      </ej-digitalgauge>
      <script type="text/javascript">
         <!--binding the value to the scope variables in application controller-->
         angular.module('syncApp', ['ejangular'])
         .controller('DigitalGauge', function ($scope) {
             $scope.nvalue = "Syncfusion";
         });
      </script>
   </body>
</html>


{% endhighlight %}

Execute the above code to render the following output.

![](/js/DigitalGauge/MVVM_images/MVVM_img3.png)



## KnockoutJS Binding

KnockoutJS support allows you to bind the HTML elements against any of the available data models.Two types of KnockoutJS binding is supported as of AngularJS,

  * one-way binding

  * two-way binding

**One way binding** refers to the process of applying observable values to all the available properties of the **Digital Gauge** control, but the changes made in it does not reflect and trigger in turn to the observable collection. This kind of binding applies to all the properties of the **Digital Gauge** control.

**Two-way binding** supports both the processes – it applies the observable values to the **Digital Gauge** properties as well as the changes made in it is also reflected back and triggered within the observable collections. Only **Value** of the schedule properties support two-way binding.



{% highlight html %}


<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
   <head>
      <title>Essential JavaScript for Knockout</title>
   </head>
   <body>
      <div id="digitalCore" style="width: 100%" data-bind="ejDigitalGauge:({load:'loadGaugeTheme',value:samplevalue,height:305,items:[{position: { x: 52, y: 52 }}]})"></div>
      <script type="text/javascript">
         $(function () {
             window.viewModel = {
                 value: ko.observable("SyncFusion"),
             };
             $(function () {
                 ko.applyBindings(viewModel);
             });
         });
      </script>
   </body>
</html>


{% endhighlight %}

Execute the above code to render the following output.

![](/js/DigitalGauge/MVVM_images/MVVM_img4.png)

