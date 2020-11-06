---
layout: post
title: Getting-started
description: Getting started for SplitButton
platform: ReactJS
control: SplitButton
documentation: ug
---

# Getting Started

This section explains briefly about how to create a SplitButton in your application with ReactJS.

## Create a SplitButton

Refer the common ReactJS getting started documentation to create an application and add necessary scripts and styles for rendering our ReactJS components.

Create a JSX file and use &lt;EJ.SplitButton&gt; syntax to render ReactJS SplitButton component. Add required properties to &lt;EJ.SplitButton&gt; tag element. 

{% highlight html %}

    ReactDOM.render(   
        <EJ.SplitButton id="spltbutton21" targetID="Ul21" >login</EJ.SplitButton>
                                    <ul id="Ul21">
                                        <li><span>User</span></li>
                                        <li><span>Guest</span></li>
                                        <li><span>Admin</span></li>
                                    </ul>
       document.getElementById('button-splitbutton')  
    );

{% endhighlight %}

Define an HTML element for adding SplitButton in the application and refer the JSX file created.

{% highlight html %}

    <div id="button-splitbutton"></div>
	<script src="app/button/splitbutton.js"></script>

{% endhighlight %}

This will render SplitButton component on executing.

## Configure Properties

In the JSX, need to declare the SplitButton properties. Refer to the following code,.

{% highlight html %}

    ReactDOM.render(   
        <EJ.SplitButton id="spltbutton21" showRoundedCorner={true} targetID="Ul21" >login</EJ.SplitButton>
                                    <ul id="Ul21">
                                        <li><span>User</span></li>
                                        <li><span>Guest</span></li>
                                        <li><span>Admin</span></li>
                                    </ul>
         document.getElementById('button-splitbutton')
    );

{% endhighlight %}


Run the above code to render the following output,

![](Getting-Started_images/Getting-Started_img1.png)


> _Note:_ _You can find the SplitButton properties from the_ [API reference](https://help.syncfusion.com/api/js/ejsplitbutton) _document._
