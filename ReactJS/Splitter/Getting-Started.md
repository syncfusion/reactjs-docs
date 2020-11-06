---
layout: post
title: Getting-Started
description: getting started
platform: reactjs
control: Splitter 
documentation: ug
---

# Getting Started

This section helps to get started of the Splitter component in a React application.

![](Getting_Started_images/Getting_Started_img1.png)

## Create a Splitter

Refer the common React JS [Getting Started Documentation](https://help.syncfusion.com/reactjs/overview#getting-started-with-react) to create an application and add necessary scripts and styles for rendering our React JS components.

Create a JSX file for rendering Splitter component using &lt;EJ.Splitter&gt; syntax. Add required properties to it in &lt;EJ.Splitter&gt; tag element.

{% highlight html %}

    "use strict";
    ReactDOM.render(
    <EJ.Splitter id="default_outerSplitter" width= "100%" height="100%" isResponsive={true}      orientation={ej.Orientation.Vertical}>
    </EJ.Splitter>,
    document.getElementById(splitter-default')
    );

{% endhighlight %}

Define an HTML element for adding Rotator in the application and refer the JSX file created.

{% highlight html %}

    <div id="splitter-default"></div>
    <script type="text/babel" src="sample.jsx"> 


{% endhighlight %}

This will render an empty Splitter component on executing.

> _Note:_ _You can find the Splitter properties from the_ [API reference](https://help.syncfusion.com/api/js/ejsplitter) _document___

## Configure Splitter Panes

To configure properties for Splitter component, define properties in the JSX.

{% highlight html %}

    <EJ.Splitter id="integration_outterSplitter" width= "100%" height="100%" isResponsive={true}>

    </EJ.Splitter>

{% endhighlight %}

Configure the Splitter panes with images. Save the images in the corresponding location.

{% highlight html %}

    <div id="samplecontrol" className="integrationContainer">
        <EJ.Splitter id="integration_outterSplitter" width= "100%" height="100%" isResponsive={true}>
            <div>
                <div className="cont">
                    <h3 className="h3">React JS</h3>                               
                </div>
            </div>
            <div>
            <div className="cont">
                <div className="_content">Select any product from the tree to show the description.</div>
                <div className="mobile spe">
                    <h3>Mobile</h3>
                    <img src="content/images/Splitter/mobile.jpeg" />
                </div>
                <div className="harddisk spe">
                    <h3>Harddisk</h3>
                    <img src="content/images/Splitter/harddisk.jpg" />
                </div>
                <div className="logo spe">
                    <h3>Logo</h3>
                <img src="content/images/Splitter/logo.png" />
                </div>
            </div>
            </div>
         </EJ.Splitter>
    </div>


{% endhighlight %}

## Configure Tree View 

For adding Treeview component, you have to use &lt;EJ.TreeView&gt; syntax to corresponding element. You need to use “nodeSelect” event handler to perform any action while selection the node in Tree view.

Add the following code example in JSX to configure Tree View.

{% highlight html %}

    <EJ.TreeView id="treeView" className="visibleHide" nodeSelect={this.treeClicked}>
        <li>Mobile
            <ul>
                <li id="mobile" className="_child">Galaxy</li>
            </ul>
        </li>
        <li>Harddisk
            <ul>
                <li id="harddisk" className="_child">Segate </li>
            </ul>
        </li>
        <li>Logo
            <ul>
                <li id="logo" className="_child">Amazon</li>
            </ul>
        </li>
    </EJ.TreeView>


{% endhighlight %}

## Set Actions

Add the nodeSelect event in JSX to set the action to view the images for “li” content of the Tree view.

{% highlight javascript %}

    treeClicked: function(e){
            if (e.currentElement.hasClass('_child')) {
                var content = $('.' + e.currentElement[0].id).html();
                $('._content').html(content);
            }
        }


{% endhighlight %}

You can render Splitter with Tree View using React JS, Please refer the below code in JSX.

{% highlight html %}

    ReactDOM.render(document.getElementById(splitter-default'));

{% endhighlight %}

