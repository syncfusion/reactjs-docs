---
layout: post
title: getting-started
description: getting started for PercentageTextbox
platform: reactjs
control: PercentageTextbox
documentation: ug
---

# Getting Started

This section helps to get started of the PercentageTextbox component in a React application 

## Create a PercentageTextbox

Refer the common React Getting Started Documentation to create an application and add necessary scripts and styles for rendering our ReactJS components.

Create a JSX file and use &lt;EJ.PercentageTextbox&gt; syntax to render React PercentageTextbox component. Add required properties to &lt;EJ.PercentageTextbox&gt; tag element. 

{% highlight html %}

    ReactDOM.render(   
        <EJ.PercentageTextbox>
        </EJ.PercentageTextbox>,
        document.getElementById('percent')  
    );

{% endhighlight %}

Define an HTML element for adding PercentageTextbox in the application and refer the JSX file created.

{% highlight html %}

    <div id="percent"></div>
    <script type="text/babel" src="sample.jsx"> 

{% endhighlight %}

This will render an empty PercentageTextbox component on executing.

## Configure Properties

In the JSX, need to declare the PercentageTextbox properties. Refer to the following code,.

{% highlight html %}

    ReactDOM.render(   
        <EJ.PercentageTextbox value={20} width="250px">
        </EJ.PercentageTextbox>,
        document.getElementById('percent')
    );

{% endhighlight %}


Run the above code to render the following output,

![](Getting-Started_images/Getting-Started_img1.jpeg)


> _Note:_ _You can find the PercentageTextbox properties from the_ [API reference](https://help.syncfusion.com/api/js/ejtextboxes) _document._

