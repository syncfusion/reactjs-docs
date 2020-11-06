---
layout: post
title: Getting-started | RadioButton | ReactJS | Syncfusion
description: Getting started for RadioButton
platform: ReactJS
control: RadioButton
documentation: ug
---

# GettingStarted

This section discloses the details on how to render and configure RadioButton component in a ReactJS application.

## Create a RadioButton

Create an HTML page and refer the neccessary script and CSS dependency files in your application with the help of given [getting started documentation](http://help.syncfusion.com/reactjs)

With ReactJS, the components can be initialized in two ways. 

1. Using jsx Template
2. Without using jsx Template

### Using jsx Template

You can render EJ components by using JSX template, wherein this JSX file will be converted to its equivalent JS file. 

1. Create an HTML file and add a div element and give it an ID. 

{% highlight html %}

<body>
    <div id="container"></div>
</body>

{% endhighlight %}

2. Create a JSX file and initialize RadioButton component by using the below code snippet.

{% highlight html %}

    ReactDOM.render(   
       <div>
				 <br />
				   Category
				<br />
				<br />
				<table >
					<tr>
					<td>
						<EJ.RadioButton id="fresher" text="Fresher" name="category" value="fresher"></EJ.RadioButton>
					</td>
					<td  colspan="2">
						<EJ.RadioButton id="experienced" text="Experienced" name="category" value="experienced" checked={true}></EJ.RadioButton>
					</td>
					</tr>
				</table>
				 <br />
				 <br />
				  Experienced
				<br />
				<br />
				<table>
					<tr>
						<td>
						<EJ.RadioButton id="exp1" text="1+ years" name="experienced" value="1+ years" checked={true}></EJ.RadioButton>
						</td>
						<td colspan="2">
						<EJ.RadioButton id="exp2" text="2.5+ years" name="experienced" value="2.5+ years"></EJ.RadioButton>
						</td>
						<td colspan="2">
						<EJ.RadioButton id="exp5" text="2.5+ years" name="experienced" value="5+ years"></EJ.RadioButton>
						</twd>
					</tr>
				</table>
			 </div>,
        document.getElementById('container')
    );

{% endhighlight %}

3. Refer the JSX file created in last step in the HTML file as given below. 

 {% highlight html %}

<body>
    <div id="dtp"></div>

    <!-- Radiobutton.jsx created in previous step-->
    <script type="text/babel" src="RadioButton.jsx">
    </script>   
</body>

{% endhighlight %}

Now the jsx file will be compiled into its equivalent Javascript file by means of Babel. 

Execute the above code to render RadioButton component. 

![Create a RadioButton with using jsx Template](Getting-Started_images/RadiobuttonJSX.png)

### Without using jsx Template

The RadioButton component can be initialized without using JSX template. 

1. Create an HTML page and render a <div> element with an ID set to it. 

{% highlight HTML %}

Category
<table>
    <tr>
        <td>
            <div id="radio1"></div>
        </td>
        <td>
            <div id="radio2"></div>
        </td>
    </tr>
</table>

{% endhighlight %}

2. Render the RadioButton component by using the below mentioned code snippet.

{% highlight javascript %}

ReactDOM.render(
    React.createElement(EJ.RadioButton, {
        id: "radio_btn1",
        name: "category",
        value: "fresher",
        text: "Fresher", 
		checked: true
    }),
    document.getElementById('radio1')
);
ReactDOM.render(
    React.createElement(EJ.RadioButton, {
        id: "radio_btn2",
        name: "category",
        value: "experienced",
        text: "Experienced"
    }),
    document.getElementById('radio2')
);

{% endhighlight %}

Run the above code snippet to get the following output.

![Create a RadioButton without using jsx Template](getting-started_images/Radiobutton.png) 
