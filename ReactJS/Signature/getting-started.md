---
layout: post
title: getting started
description: getting started
platform: ReactJS
control: Signature
documentation: ug
---

# Getting Started

The ReactJS Signature simplifies creation of a signature capture in a browser, allowing a user to draw a signature using mouse or touch.

This section explains briefly about how to create a **Signature** component in your application with ReactJS by the following step-by-step instructions. The following screenshot demonstrates the functionality of Signature component.

![https://help.syncfusion.com/js/signature/Getting_Started_images/gettingstarted_img1.png](Getting_Started_images\gettingstarted_img1.png)

## Create a Signature component in ReactJS

You can create a React application and add necessary scripts and styles with the help of the given [React Getting Started Documentation.](https://help.syncfusion.com/reactjs/overview)

Create a JSX file for rendering AutoComplete component using &lt;EJ.Signature&gt; syntax. Add required properties to it in &lt;EJ. Signature &gt; tag element

{% highlight html %}

"use strict";

ReactDOM.render(   
<EJ.Signature id="mySignature" height={400}>
  </EJ.Signature>,
document.getElementById('signature-default')
);


{% endhighlight %}



Define an HTML element for adding AutoComplete in the application and refer the JSX file.

{% highlight html %}


<div id="'signature-default"></div>
 <script type="text/babel" src="signature.jsx"></script>


{% endhighlight %}



Run the above code to render the following output.

![https://help.syncfusion.com/js/signature/Getting_Started_images/createsignaturecontrol_img1.png](Getting_Started_images\createasignaturecomponentinreactjs_img1.png)


## Adjusting Signature Size

You can customize the width and height of the Signature by width and height properties. These properties completely depend on signature canvas. The width and height are adjusted within the signature canvas.

The following code example is used to render the Signature component with customized width and height.

{% highlight html %}

"use strict";

ReactDOM.render(   

&lt;EJ.Signature id="mySignature" isResponsive="true" height={300} width={200}&gt;

  &lt;/EJ.Signature&gt;,

document.getElementById('signature-default')

);
{% endhighlight %}

The following screenshot illustrates signature with customized width and height.

![https://help.syncfusion.com/js/signature/Getting_Started_images/adjustingsignaturesize_img1.png](Getting_Started_images\adjustingsignaturesize_img1.png)



