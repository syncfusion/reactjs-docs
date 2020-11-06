---
layout: post
title: getting-started
description: getting started for MaskEdit
platform: reactjs
control: MaskEdit
documentation: ug
---

# Getting Started

This section helps to get started of the MaskEdit component in a React application 

## Create a MaskEdit

Refer the common React Getting Started Documentation to create an application and add necessary scripts and styles for rendering our ReactJS components.

Create a JSX file and use &lt;EJ.MaskEdit&gt; syntax to render React MaskEdit component. Add required properties to &lt;EJ.MaskEdit&gt; tag element. 

{% highlight html %}

    ReactDOM.render(   
        <EJ.MaskEdit>
        </EJ.MaskEdit>,
        document.getElementById('mask')  
    );

{% endhighlight %}

Define an HTML element for adding MaskEdit in the application and refer the JSX file created.

{% highlight html %}

    <div id="mask"></div>
    <script type="text/babel" src="sample.jsx"> 

{% endhighlight %}

This will render an empty MaskEdit component on executing.

## Configure Properties

In the JSX, need to declare the MaskEdit properties. Refer to the following code,.

{% highlight html %}

    ReactDOM.render(   
	<EJ.MaskEdit value="4242422424" maskFormat="99 999-99999">
	</EJ.MaskEdit>,
        document.getElementById('mask')
    );

{% endhighlight %}


Run the above code to render the following output,

![](Getting-Started_images/Getting-Started_img1.jpeg)


> _Note:_ _You can find the MaskEdit properties from the_ [API reference](https://help.syncfusion.com/api/js/ejmaskedit) _document._
