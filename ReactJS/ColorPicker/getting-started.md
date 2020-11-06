---
layout: post
title: Getting-started 
description: Getting started for ColorPicker
platform: ReactJS
control: ColorPicker
documentation: ug
---

# Getting Started

Using the following steps, you can create a React ColorPicker component. The basic rendering of React ColorPicker can be achieved with default functionality.

## Create an ColorPicker

You can create a React application and add necessary scripts and styles with the help of the given [React Getting Started Documentation.](https://help.syncfusion.com/reactjs/overview)

Create a JSX file for rendering ColorPicker component using &lt;EJ.ColorPicker&gt; syntax. Add required properties to it in &lt;EJ.ColorPicker&gt; tag element

{% highlight html %}

    ReactDOM.render(   
        <EJ.ColorPicker>
        </EJ.ColorPicker>,
        document.getElementById('colorpick')  
    );

{% endhighlight %}

Define an HTML element for adding ColorPicker in the application and refer the JSX file created.

{% highlight html %}

    <div id="colorpick"></div>
    <script type="text/babel" src="sample.jsx"> 

{% endhighlight %}

This will render an empty ColorPicker component on executing.

## Configure Properties

In the JSX, need to declare the ColorPicker properties. Refer to the following code,

{% highlight html %}

    ReactDOM.render(   
	<EJ.ColorPicker value="#278787">
	</EJ.ColorPicker>,
        document.getElementById('colorpick')
    );

{% endhighlight %}


Run the above code to render the following output,

![](Getting-Started_images/Getting-Started_img1.PNG)


> _Note:_ _You can find the ColorPicker properties from the_ [API reference](https://help.syncfusion.com/api/js/ejcolorpicker) _document._



