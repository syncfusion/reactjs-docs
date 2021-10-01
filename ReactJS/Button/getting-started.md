---
layout: post
title: Getting Started with ReactJS Button Control | Syncfusion
description: Learn here about getting started with Syncfusion Essential ReactJS Button Control, its elements, and more.
platform: ReactJS
control: Button
documentation: ug
---

# Getting Started with ReactJS Button

This section explains briefly about how to create a Button in your application with ReactJS.

You can create a React JS application and add necessary scripts and styles with the help of the given [link](https://help.syncfusion.com/reactjs/overview)

Define an HTML element to rendering as the Button in the application and refer the JSX file. Please check with the below code example,


{% highlight html %}

   <body>	
    <!--Add React JS components-->
    <div id="btn"></div>

    <!-- Button.jsx created in previous step-->
    <script type="text/babel" src="Button.jsx">
    </script>
   </body>

{% endhighlight %}

## Control Initialization  with react js
Control can be initialized in two ways.
* Using JSX Template. 
* Without using JSX Template

### Using  JSX Template
With the JSX template concept, we need to create the html file and JSX file. The .jsx file can be convert to .js file and it can be referred in html page.
Create a JSX file for rendering Button component with below code.


{% highlight html %}

ReactDOM.render(   
		  <EJ.Button id="btn" text="Button">
</EJ.Button>,
document.getElementById('btn')
);


{% endhighlight %}


Run the above code to render the following output.



![getting-started_images1](getting-started_images/getting-started_img1.jpg)

#### Configuring Button

This section encompasses the details on how you can configure the Button control in your application and customize it with various properties such as various size, resize the  Button and rounded corner according  to your requirement.
To render the text and size properties add the following code example in your JS  file.

{% highlight html %}

ReactDOM.render(   
		  <EJ.Button id="btn" text="Button" showRoundedCorner={true} size="large" text="Click here">

</EJ.Button>,
document.getElementById('btn')
);




{% endhighlight %}

The following screenshot illustrates the Button control with text, size and rounded corner properties.


## Create a Button without using JSX template
 The Button can be created from a normal script section without using JSX template file also. Please check with the below code example,

{% highlight html %}

    <script>
    ReactDOM.render(
    React.createElement(EJ.Button, { id: "container",text:"Button" }
    ),
    document.getElementById('container')
    );
</script>

    
{% endhighlight %}

## Configure Properties

This section encompasses the details on how you can configure the Button control in your application and customize it with various properties such as various size, rename and rounded corner for Button according to your requirement.
 To render the text, size and rounded corner properties add the following snippet in your HTML file.


{% highlight javascript %}

<script>
    ReactDOM.render(
    React.createElement(EJ.Button, { id: "container",text:"Button",showRoundedCorner:true,size:"large",text:"Click here" }
    ),
    document.getElementById('container')
    );
</script>

{% endhighlight %}




