---
layout: post
title: getting-started
description: getting started for CurrencyTextbox
platform: reactjs
control: CurrencyTextbox
documentation: ug
---

# Getting Started

This section helps to get started of the CurrencyTextbox component in a React application 

## Create a CurrencyTextbox

Refer the common React Getting Started Documentation to create an application and add necessary scripts and styles for rendering our ReactJS components.

Create a JSX file and use &lt;EJ.CurrencyTextbox&gt; syntax to render React CurrencyTextbox component. Add required properties to &lt;EJ.CurrencyTextbox&gt; tag element. 

{% highlight html %}

    ReactDOM.render(   
        <EJ.CurrencyTextbox>
        </EJ.CurrencyTextbox>,
        document.getElementById('currency')  
    );

{% endhighlight %}

Define an HTML element for adding CurrencyTextbox in the application and refer the JSX file created.

{% highlight html %}

    <div id="currency"></div>
    <script type="text/babel" src="sample.jsx"> 

{% endhighlight %}

This will render an empty CurrencyTextbox component on executing.

## Configure Properties

In the JSX, need to declare the CurrencyTextbox properties. Refer to the following code,.

{% highlight html %}

    ReactDOM.render(   
        <EJ. CurrencyTextbox value={10} width="250px">
        </EJ. CurrencyTextbox >,
        document.getElementById('currency')
    );

{% endhighlight %}


Run the above code to render the following output,

![](Getting-Started_images/Getting-Started_img1.jpeg)


> _Note:_ _You can find the CurrencyTextbox properties from the_ [API reference](https://help.syncfusion.com/api/js/ejtextboxes) _document._

