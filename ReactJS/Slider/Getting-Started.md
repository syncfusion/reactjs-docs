---
layout: post
title: getting-started
description: getting started for Slider
platform: reactjs
control: Slider
documentation: ug
---

# Getting Started

This section helps to get started of the Slider component in a React application 

## Create a Slider

Refer the common React Getting Started Documentation to create an application and add necessary scripts and styles for rendering our ReactJS components.

Create a JSX file and use &lt;EJ.Slider&gt; syntax to render React Slider component. Add required properties to &lt;EJ.Slider&gt; tag element. 

{% highlight html %}

    ReactDOM.render(   
        <EJ.Slider>
        </EJ.Slider>,
        document.getElementById('default-slider')  
    );

{% endhighlight %}

Define an HTML element for adding Slider in the application and refer the JSX file created.

{% highlight html %}

    <div id="default-slider"></div>
    <script type="text/babel" src="sample.jsx"> 

{% endhighlight %}

This will render an default Slider component on executing.

## Configure Properties

In the JSX, need to declare the Slider properties. Refer to the following code,.

{% highlight html %}

    ReactDOM.render(   
        <EJ.Slider value={20} >
        </EJ.Slider>,
        document.getElementById('default-slider')
    );

{% endhighlight %}


Run the above code to render the following output,

![](Getting-Started_images/Getting-Started_img1.jpg)


> _Note:_ _You can find the Slider properties from the_ [API reference](https://help.syncfusion.com/api/js/ejslider) _document._

