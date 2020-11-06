---
layout: post
title: getting-started
description: getting started
platform: reactjs
control: Dialog
documentation: ug
---

# Getting Started

This section helps you to understand the getting started of the Dialog component with the step-by-step instructions.

## Create a simple Dialog

Refer the common React’s Getting Started Documentation to create an application and add necessary scripts and styles for rendering our React JS components.

Create a JSX file for rendering Dialog component using &lt;EJ.Dialog&gt; syntax. Add required properties to it in &lt;EJ.Dialog&gt; tag element

{% highlight javascript %}

    ReactDOM.render(   
        <EJ.Dialog id="basicDialog">
        </EJ.Dialog>,
        document.getElementById('Dialog-default')  
    );


{% endhighlight %}


Define an HTML element for adding Dialog in the application and refer the JSX file created with script type “text/babel”.

{% highlight html %}

    <div id="Dialog-default"></div>
    <script type="text/babel" src="sample.jsx">


{% endhighlight %}

This will render an empty Dialog component on executing.

## Add content to Dialog

Add the below code to render Dialog Component with content

{% highlight javascript %}

    ReactDOM.render(   
        <EJ.Dialog id="basicDialog">
        <p>This is a simple dialog</p>
        </EJ.Dialog>,
        document.getElementById('Dialog-default')  
    );


{% endhighlight %}

Any content can be added inside of &lt;EJ.Dialog&gt; &lt;/EJ.Dialog&gt; which will be available in Dialog content area on rendering.


![](Getting-Started_Images/getting-started_img1.png)

## Set header text

You can set Dialog component header using the **title** property.

{% highlight javascript %}

    ReactDOM.render(   
        <EJ.Dialog id="basicDialog" title="Dialog">
        <p>This is a simple dialog</p>
        </EJ.Dialog>,
        document.getElementById('Dialog-default')  
    );


{% endhighlight %}


Run the above code and your output will be,

![title](Getting-Started_Images/getting-started_img2.png)

## Open Dialog dynamically

In most cases, the Dialog components are needed only in dynamic actions like showing some messages on clicking a button, to provide alert, etc. So the Dialog component provides “open” and “close” methods to open/close the dialogs dynamically.

The Dialog Component can be hidden on initialize using **showOnInit** property which should be set to false.

Define click action for the button and the dialog will be opened on clicking the Button component.

{% highlight javascript %}

    var DefaultDialog = React.createClass({
        onOpen: function (e) {
            $("#basicDialog").ejDialog("open");
        },
        onDialogClose: function (e) {
            $("#btnOpen").show();
        },
        render: function () {
            return (   
            <div id="dialog_default">  
                <EJ.Button id="btnOpen" size="medium" type="button" height={30} width={150} text="Open Dialog" click={this.onOpen}>
                </EJ.Button> 
                <EJ.Dialog id="basicDialog" title="Dialog" showOnInit={false} allowDraggable={true} target="#Dialog-default" close={this.onDialogClose}>
                    <p>This is a simple dialog</p>
                </EJ.Dialog>
            </div>
            );
        }
    });  
    ReactDOM.render(<DefaultDialog />, document.getElementById('Dialog-default'));


{% endhighlight %}


Your output will be,

![](Getting-Started_Images/getting-started_img3.png)

> _Note:_ _You can find the Dialog properties from the_ [API reference](https://help.syncfusion.com/api/js/ejdialog) _document._