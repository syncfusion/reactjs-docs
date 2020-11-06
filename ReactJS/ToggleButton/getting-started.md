---
layout: post
title: Getting-started 
description: Getting started for ToggleButton
platform: ReactJS
control: ToggleButton
documentation: ug
---

# Getting Started

Using the following steps, you can create a React ToggleButton component. The basic rendering of React ToggleButton can be achieved with default functionality.

## Create an ToggleButton

You can create a React application and add necessary scripts and styles with the help of the given [React Getting Started Documentation.](https://help.syncfusion.com/reactjs/overview)

Create a JSX file for rendering ToggleButton component using &lt;EJ.ToggleButton&gt; syntax. Add required properties to it in &lt;EJ.ToggleButton&gt; tag element

{% highlight html %}

    ReactDOM.render(   
        <EJ.ToggleButton>
        </EJ.ToggleButton>,
        document.getElementById('togglebtn')  
    );

{% endhighlight %}

Define an HTML element for adding ToggleButton in the application and refer the JSX file created.

{% highlight html %}

    <div id="togglebtn"></div>
    <script type="text/babel" src="sample.jsx"> 

{% endhighlight %}

This will render an empty ToggleButton component on executing.

## Configure Properties

In the JSX, need to declare the ToggleButton properties. Refer to the following code,

{% highlight html %}

    ReactDOM.render(   
	<EJ.ToggleButton id="togglebtn" ejHtmlAttributes={{type:"checkbox"}} size={ej.ButtonSize.Large} showRoundedCorner={true} contentType={ej.ContentType.TextAndImage} defaultPrefixIcon="e-icon e-mediaplay" activePrefixIcon="e-icon e-mediapause" defaultText="Play" activeText="Pause"></EJ.ToggleButton>,
        document.getElementById('togglebtn')
    );

{% endhighlight %}


Run the above code to render the following output,

![](Getting-Started_images/Getting-Started_img1.JPG)

![](Getting-Started_images/Getting-Started_img2.JPG)


> _Note:_ _You can find the ToggleButton properties from the_ [API reference](https://help.syncfusion.com/api/js/ejtogglebutton) _document._



