---
layout: post
title: getting-started
description: getting started
platform: reactjs
control: Rotator
documentation: ug
---

# Getting Started

This section helps to get started with Essential ReactJS Rotator component. 

## Create a Rotator

Refer the common React Getting Started Documentation to create an application and add necessary scripts and styles for rendering our ReactJS components.

Create a JSX file and use &lt;EJ.Rotator&gt; syntax to render React Rotator component. Add required properties to &lt;EJ.Rotator&gt; tag element. 

{% highlight html %}

    ReactDOM.render(   
      <EJ.Rotator id="sliderContent" slideWidth="600px" slideHeight={330}>
      </EJ.Rotator>,
      document.getElementById('rotator-default')  
    );


{% endhighlight %}

Define an HTML element for adding Rotator in the application and refer the JSX file created.

{% highlight html %}

    <div id="rotator-default"></div>
    <script type="text/babel" src="sample.jsx"> 

{% endhighlight %}

This will render an empty Rotator component on executing.

## Configure data

To configure images for Rotator component, define data in an array and map corresponding fields to it.

{% highlight javascript %}

      var dataList = [
          { text: "Colorful Night", url: "http://js.syncfusion.com/demos/web/content/images/rotator/night.jpg" },
          { text: "Technology", url: "http://js.syncfusion.com/demos/web/content/images/rotator/tablet.jpg" },
          { text: "Nature", url: "http://js.syncfusion.com/demos/web/content/images/rotator/nature.jpg" },
          { text: "Snow Fall", url: "http://js.syncfusion.com/demos/web/content/images/rotator/snowfall.jpg" },
          { text: "Credit Card", url: "http://js.syncfusion.com/demos/web/content/images/rotator/card.jpg" },
          { text: "Beautiful Bird", url: "http://js.syncfusion.com/demos/web/content/images/rotator/bird.jpg" },
          { text: "Amazing Sculptures", url: "http://js.syncfusion.com/demos/web/content/images/rotator/sculpture.jpg" }
            ];
        var fieldset={text:"text",url:"url"};


{% endhighlight %}


In the JSX you have to assign the values for dataSource and fields as given below,

{% highlight html %}

    ReactDOM.render(   

      <EJ.Rotator id="sliderContent" slideWidth="600px" slideHeight={330} fields={fieldset}

        isResponsive={true} dataSource={dataList} navigateSteps={1} orientation={ej.Orientation.Horizontal} 

      showPager={true} enabled={true} showPlayButton={true} animationType="slide">

      </EJ.Rotator>,

      document.getElementById('rotator-default')  

    );

{% endhighlight %}

![](Getting-Started_images/Getting-Started_img1.png)



> _Note:_ _You can find the Rotator properties from the_ [API reference](https://help.syncfusion.com/api/js/ejrotator) _document._

