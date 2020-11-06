---
layout: post
title: Getting-Started
description: getting started
platform: React JS
control: TagCloud
documentation: ug
keywords: ejtagcloud, tagcloud, js tagcloud
---

# Getting Started

This section explains briefly about how to create a **TagCloud** in your application with **JavaScript**. The **TagCloud** can be easily configured to the div element in which the tags are placed. The following screenshot illustrates the functionality of a **TagCloud** widget with a list of the topmost search engines. 

![](Getting-Started_images/Getting-Started1.jpg)

## Create TagCloud widget in React JS

You can create a React application and add necessary scripts and styles with the help of the given [React Getting Started Documentation.](https://help.syncfusion.com/reactjs/overview)

Create a JSX file for rendering TagCloud component using &lt;EJ.TabCloud&gt; syntax. Add required properties to it in &lt;EJ.TagCloud&gt; tag element

{% highlight javascript %}

"use strict";

var websiteCollection = [
              { text: "Google", url: "http://www.google.co.in", frequency: 20 },
              { text: "a2zwebhelp", url: "http://www.a2zwebhelp.com", frequency: 3 },
              { text: "Arts Technica", url: "http://arstechnica.com/", frequency: 8 },
              { text: "Bxslider", url: "http://bxslider.com/examples", frequency: 2 },
              { text: "Yahoo", url: "http://in.yahoo.com/", frequency: 12 },
              { text: "Facebook", url: "https://www.facebook.com/", frequency: 5 },
              { text: "Blogspot", url: "http://www.blogspot.com/", frequency: 8 },
              { text: "Microsoft", url: "http://www.microsoft.com/", frequency: 20 },
              { text: "Amazon.com", url: "http://www.amazon.com/", frequency: 1 },
              { text: "MSN", url: "http://www.msn.com/", frequency: 3 },
              { text: "Engadget", url: "http://www.engadget.com/", frequency: 5 },
              { text: "LinkedIn", url: "http://www.linkedIn.com/", frequency: 9 },
              { text: "Twitter", url: "http://www.Twitter.com/", frequency: 0 },
              { text: "Menucool", url: "http://www.menucool.com", frequency: 3 },
              { text: "BBC", url: "http://www.bbc.co.uk/", frequency: 11 },
              { text: "Valleywag", url: "http://valleywag.gawker.com/", frequency: 6 },
              { text: "WOWslider", url: "http://wowslider.com", frequency: 9 },
              { text: "W3schools", url: "http://www.w3schools.com/", frequency: 2 }

              ];

ReactDOM.render(
    <EJ.TagCloud width="100%" cssClass="alignc" titleText= "Tech Sites" dataSource={websiteCollection}>
    </EJ.TagCloud>,
document.getElementById('tagcloud-default')
);

{% endhighlight %}

Define an HTML element for adding TabCloud in the application and refer the JSX file.

{% highlight html %}

<div id="tagcloud-default"></div>
<script src="app/tagcloud/default.js">

{% endhighlight %}

The following screenshot displays the output of the above code example.

![](Getting-Started_images/Getting-Started1.jpg) 

## Set Min and Max Font Size

In the above code example, the **frequency** properties are used to set the min and max font size to the **TagCloud** list item.

{% highlight javascript %}
   
var websiteCollection = [
              { text: "Google", url: "http://www.google.co.in", frequency: 20 },
              { text: "a2zwebhelp", url: "http://www.a2zwebhelp.com", frequency: 3 },
              { text: "Arts Technica", url: "http://arstechnica.com/", frequency: 8 },
              { text: "Bxslider", url: "http://bxslider.com/examples", frequency: 2 },
              { text: "Yahoo", url: "http://in.yahoo.com/", frequency: 12 },
              { text: "Facebook", url: "https://www.facebook.com/", frequency: 5 },
              { text: "Blogspot", url: "http://www.blogspot.com/", frequency: 8 },
              { text: "Microsoft", url: "http://www.microsoft.com/", frequency: 20 },
              { text: "Amazon.com", url: "http://www.amazon.com/", frequency: 1 },
              { text: "MSN", url: "http://www.msn.com/", frequency: 3 },
              { text: "Engadget", url: "http://www.engadget.com/", frequency: 5 },
              { text: "LinkedIn", url: "http://www.linkedIn.com/", frequency: 9 },
              { text: "Twitter", url: "http://www.Twitter.com/", frequency: 0 },
              { text: "Menucool", url: "http://www.menucool.com", frequency: 3 },
              { text: "BBC", url: "http://www.bbc.co.uk/", frequency: 11 },
              { text: "Valleywag", url: "http://valleywag.gawker.com/", frequency: 6 },
              { text: "WOWslider", url: "http://wowslider.com", frequency: 9 },
              { text: "W3schools", url: "http://www.w3schools.com/", frequency: 2 }

              ];

ReactDOM.render(
    <EJ.TagCloud width="100%" cssClass="alignc" titleText= "Tech Sites" dataSource={websiteCollection}>
    </EJ.TagCloud>,
document.getElementById('tagcloud-default')
);
 
{% endhighlight %}

In the above code, the min font size is 0 and max font size is 20.

## Set event to perform an operation

Here, you can set the **TagCloud** events such as create, mouseover, mouseout, click.

{% highlight html %}

<div id="tagcloud-default"></div>
<script src="app/tagcloud/default.js">

{% endhighlight %}

{% highlight javascript %}

var websiteCollection = [
              { text: "Google", url: "http://www.google.co.in", frequency: 12 },
              { text: "a2zwebhelp", url: "http://www.a2zwebhelp.com", frequency: 3 },
              { text: "Arts Technica", url: "http://arstechnica.com/", frequency: 8 },
              { text: "Bxslider", url: "http://bxslider.com/examples", frequency: 2 },
              { text: "Yahoo", url: "http://in.yahoo.com/", frequency: 12 },
              { text: "Facebook", url: "https://www.facebook.com/", frequency: 5 },
              { text: "Blogspot", url: "http://www.blogspot.com/", frequency: 8 },
              { text: "Microsoft", url: "http://www.microsoft.com/", frequency: 20 },
              { text: "Amazon.com", url: "http://www.amazon.com/", frequency: 1 },
              { text: "MSN", url: "http://www.msn.com/", frequency: 3 },
              { text: "Engadget", url: "http://www.engadget.com/", frequency: 5 },
              { text: "LinkedIn", url: "http://www.linkedIn.com/", frequency: 9 },
              { text: "Twitter", url: "http://www.Twitter.com/", frequency: 0 },
              { text: "Menucool", url: "http://www.menucool.com", frequency: 3 },
              { text: "BBC", url: "http://www.bbc.co.uk/", frequency: 11 },
              { text: "Valleywag", url: "http://valleywag.gawker.com/", frequency: 6 },
              { text: "WOWslider", url: "http://wowslider.com", frequency: 9 },
              { text: "W3schools", url: "http://www.w3schools.com/", frequency: 2 }

             ];
var DefaultTagcloud = React.createClass({
    componentDidMount: function () { 
    $scope.oncreate=function(){
        alert();
    }
    $scope.onmouseover=function(){
        alert();
	}
    $scope.onmouseout=function(){
	    alert();
    }
    $scope.onclick=function(){
	   alert();
	}
},
render: function () {
return (  
    <EJ.TagCloud width="100%" cssClass="alignc" titleText= "Tech Sites" dataSource={websiteCollection} create={oncreate} mouseOver={onmouseover} mouseOut={onmouseout} click={onclick}>
    </EJ.TagCloud>,
	   );
	}
});
ReactDOM.render(<DefaultTagcloud />, document.getElementById('tagcloud-default'));

{% endhighlight %}

In the above code example, the **alert()** function is used  to show the events that happened.

