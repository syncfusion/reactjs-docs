---
layout: post
title: Getting-Started | Rating | JavaScript | Syncfusion
description: getting started
platform: React JS
control: Rating
documentation: ug
keywords: ejrating, rating, js rating 
---

# Getting Started

This section explains briefly about how to create a **Rating** control in your application with **JavaScript**. **Essential JavaScript** **Rating** helps to select the number of stars that represent Rating. Here, you can learn how to create **Rating** control in a real-time movie download application and also learn how to rate the application.

The following screenshot illustrates the functionality of a Rating widget with a Rating range of 0 to 5. 

![](Getting-Started_images/Getting-Started_img1.png) 

##Create a Rating Widget in React JS

**Essential JavaScript Rating** widget is provided with built-in features such as precision, orientation and flexible API’s. You can create the **Rating** widget by using input textbox element as follows:

You can create a React application and add necessary scripts and styles with the help of the given [React Getting Started Documentation.](https://help.syncfusion.com/reactjs/overview)

Define an HTML element for adding Rating in the application and refer the JSX file.

{% highlight html %}

<div id="rating-default"></div>
<script src="app/rating/default.js">

{% endhighlight %}

Create a JSX file for rendering Rating component using &lt;EJ.Rating&gt; syntax. Add required properties to it in &lt;EJ.Rating&gt; tag element

{% highlight js %}

var DefaultRating = React.createClass({
    render: function () {
        return (
        <div id="rating_default">
            <ej.tab width="100%">
                <ul>
                    <li><a href="#steelman">Man of Steel</a></li>
                    <li><a href="#woldwar">World War Z</a></li>
                    <li><a href="#unive">Monsters University</a></li>
                </ul>
                <div id="steelman">
                    <table>
                        <tr>
                            <td classname="movies-img" valign="top">
                                <img src="content/images/rating/mos.png" alt="mos" />
                            </td>
                            <td valign="top">
                                <div>
                                    <span classname="movie-header">Man of Steel</span><br />
                                    Rating :
                                    <br />
                                    <ej.rating value={3}></ej.rating><br />
                                    <span>Movie Info:</span>
                                    <p>
                                        A young boy learns that he has extraordinary powers and is not of this Earth.
                                    </p>
                                </div>
                            </td>
                        </tr>
                    </table>
                </div>
                <div id="woldwar">
                    <table>
                        <tr>
                            <td classname="movies-img" valign="top">
                                <img src="content/images/rating/wwz.png" alt="mos" />
                            </td>
                            <td valign="top">
                                <div>
                                    <span classname="movie-header">World War Z</span><br />
                                    Rating :
                                    <br />
                                    <ej.rating value={4}></ej.rating><br />
                                    <span>Movie Info:</span>
                                    <p>
                                        The story revolves around United Nations employee Gerry Lane (Pitt).
                                    </p>
                                </div>
                            </td>
                        </tr>
                    </table>
                </div>
                <div id="unive">
                    <table>
                        <tr>
                            <td classname="movies-img" valign="top">
                                <img src="content/images/rating/mu.png" alt="mos" />
                            </td>
                            <td valign="top">
                                <div>
                                    <span classname="movie-header">Monsters University</span><br />
                                    Rating :
                                    <br />
                                    <ej.rating value={4}></ej.rating><br />
                                    <span>Movie Info:</span>
                                    <p>
                                        Mike Wazowski and James P. Sullivan are an inseparable pair, but that wasn't always the case.
                                    </p>
                                </div>
                            </td>
                        </tr>
                    </table>
                </div>
            </ej.tab>
        </div>
        );
        }
        });
ReactDOM.render(
<defaultrating />, document.getElementById('rating-default'));

{% endhighlight %}


 Apply the following styles to show the Rating widget in the horizontal order.

{% highlight css %}

<style type="text/css" class="cssStyles">
    .movies-img {
        width: 125px;
    }
    
    .movie-header {
        font-size: 20px;
        font-weight: 600;
    }
</style>


{% endhighlight %}

 The following screenshot displays a Rating widget.

![](Getting-Started_images/Getting-Started_img2.png) 

##Set the Min and Max Value

In a real-time scenario, you can extend the range by using the properties **minValue** and **maxValue** in the **Rating** widget. 

{% highlight html %}

<div id="rating-default"></div>
<script src="app/rating/default.js">

{% endhighlight %}

{% highlight js %}

var DefaultRating = React.createClass({
    render: function () {
        return (
            <div id="rating_precision">
                
                <div class="frame">
                    <table id="table">
                        <tr>
                            <td valign="top">
                                Rate :
                            </td>
                            <td>
                                <EJ.Rating value={4} minValue={2} maxValue={10} ></EJ.Rating>
                            </td>
                        </tr> 
                        
                    </table>
                </div>
            </div>
        );
    }
});

ReactDOM.render(<DefaultRating />, document.getElementById('rating-default'));

{% endhighlight %}

The above code example displays the following output.

![](Getting-Started_images/Getting-Started_img3.png)

##Set Precision

In a real-time movie **Rating** scenario, you can set precision in between two whole numbers, such as 2.5 or 3.7 and it is done using the property **precision** by changing the value to **ej.Rating.Precision.Half** or **ej.Rating.Precision.Exact.**

{% highlight html %}

<div id="rating-precision"></div>
<script src="app/rating/default.js">

{% endhighlight %}

{% highlight js %}

var PrecisionRating = React.createClass({
    render: function () {
        return (
            <div id="rating_precision">
                
                <div class="frame">
                    <table id="table">
                        <tr>
                            <td valign="top">
                                Full Precision :
                            </td>
                            <td>
                                <EJ.Rating value={4} ></EJ.Rating>
                            </td>
                        </tr>
                        <tr>
                            <td valign="top">
                                Half Precision :
                            </td>
                            <td>
                                <EJ.Rating value={3.5} precision="half" ></EJ.Rating>
                            </td>
                        </tr>
                        <tr>
                            <td valign="top">
                                Exact Precision :
                            </td>
                            <td>
                                <EJ.Rating value={3.7} precision="exact" ></EJ.Rating>
                            </td>
                        </tr>
                    </table>
                </div>
</div>
        );
    }
});

ReactDOM.render(<PrecisionRating />, document.getElementById('rating-precision'));

{% endhighlight %}

The above code example displays the following output.

![](/js/Rating/Getting-Started_images/Getting-Started_img4.jpeg)

You can also add additional functionalities such as orientation, event tracer and API’s to the **Rating**. 

