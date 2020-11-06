---
layout: post
title: Getting-Started
description: getting started
platform: React JS
control: Tile
documentation: ug
---

# Getting Started

This section helps to get started with Essential ReactJS Tile component.

## Create a Tile

Refer the common ReactJS [Getting Started](https://help.syncfusion.com/reactjs/overview) Documentation to create an application and add necessary scripts and styles for rendering our ReactJS components.

Create a JSX file and use <EJ.Tile> syntax to render React Tile component. Add required properties to <EJ.Tile> tag element.

    {% highlight javascript %}

              ReactDOM.render(    
                 <EJ.Tile id="tileview">
                 </EJ.Tile>,
                 document.getElementById('tile')
              );
         
    {% endhighlight %}
    
Define an HTML element for adding Tile in the application and refer the JSX file created.

{% highlight html %}

       <div id="tile"></div> 
       <script type="text/babel" src="sample.jsx">
       
{% endhighlight %}
    
## Configuring properties

In the JSX, need to declare the Tile properties. Refer to the following code,

{% highlight javascript %}

          ReactDOM.render(    
              <EJ.Tile id="tileview" imagePosition="fill" tileSize="medium" text="People">
              </EJ.Tile>,
               document.getElementById('tile')
          );

{% endhighlight %}

![](Getting-Started_images\Getting-Started_img1.png)

You can easily design a home page using tile component for easy navigation. Therefore, you require many different sizes of tiles aligned in a grid-like manner. The tiles will be aligned automatically to define the necessary tile elements inside the wrapper element, that contains a column class. You can define all columns elements under the wrapper element with the tile group class to make ‘n’ number of tiles as a grouped tile. Add the below mentioned code to the corresponding view page.

{% highlight javascript %}

ReactDOM.render(
    <div align="center" className="tileCenter">
        <div className="e-tile-group" id="groupTile">
            <div className="e-tile-column">
                <EJ.Tile id="tile1" imagePosition="fill" caption-text="People" tileSize="medium"
                         imageUrl='http://js.syncfusion.com/ug/web/content/tile/people_1.png' text="People">
                </EJ.Tile>
                <div className="e-tile-small-col-2">
                    <EJ.Tile id="tile2" imagePosition="center" tileSize="small" imageUrl='http://js.syncfusion.com/ug/web/content/tile/alerts.png'>
                    </EJ.Tile>
                    <EJ.Tile id="tile3" imagePosition="center" tileSize="small" imageUrl='http://js.syncfusion.com/ug/web/content/tile/bing.png'>
                    </EJ.Tile>
                    <EJ.Tile id="tile4" tileSize="small" imageUrl='http://js.syncfusion.com/ug/web/content/tile/camera.png'>
                    </EJ.Tile>
                    <EJ.Tile id="tile5" tileSize="small" imagePosition="center" imageUrl='http://js.syncfusion.com/ug/web/content/tile/messages.png'>
                    </EJ.Tile>
                </div>
                <EJ.Tile id="tile6" tileSize="medium" imagePosition="center" imageUrl='http://js.syncfusion.com/ug/web/content/tile/games.png' text="Play">
                </EJ.Tile>
                <EJ.Tile id="tile7" tileSize="medium" imageUrl='http://js.syncfusion.com/ug/web/content/tile/map.png' text="Maps">
                </EJ.Tile>
                <EJ.Tile id="tile8" tileSize="wide" imageUrl='http://js.syncfusion.com/ug/web/content/tile/sports.png' text="Sports" imagePosition="fill">
                </EJ.Tile>
            </div>
            <div className="e-tile-column">
                <EJ.Tile id="tile9" tileSize="medium" imagePosition="fill" imageUrl='http://js.syncfusion.com/ug/web/content/tile/people_2.png' text="People">
                </EJ.Tile>
                <EJ.Tile id="tile10" tileSize="medium" imagePosition="center" imageUrl='http://js.syncfusion.com/ug/web/content/tile/pictures.png' text="Photo">
                </EJ.Tile>
                <EJ.Tile id="tile11" tileSize="wide" imagePosition="center" imageUrl='http://js.syncfusion.com/ug/web/content/tile/weather.png' text="Weather">
                </EJ.Tile>
                <EJ.Tile id="tile12" tileSize="medium" imagePosition="center" imageUrl='http://js.syncfusion.com/ug/web/content/tile/music.png' text="Music">
                </EJ.Tile>
                <EJ.Tile id="tile13" tileSize="medium" imagePosition="center" imageUrl='http://js.syncfusion.com/ug/web/content/tile/favs.png' text="Favorites">
                </EJ.Tile>
            </div>
        </div>
    </div>,
        document.getElementById('tile')
   );
 
{% endhighlight %}

Run the above code to get the following output.

![](Getting-Started_images\Getting-Started_img2.png)

## Template support with Tile Component  

To customize the Tile images with template feature by using imageTemplateId property of Tile component. Add the below mentioned code to the corresponding view page.

{% highlight html %}

 ReactDOM.render(  
    <div class="e-tile-group" id="groupTile">
       <div class="e-tile-column">  
           <EJ.Tile id="tileview" imagePosition="fill" tileSize="wide" imageTemplateId="imageTemplate" text="Windows Store">
           </EJ.Tile>
        </div>
        <div id="imageTemplate">
        <div id="appimage">
        </div>
        <div class="tileMargin">
            <span class="caption">Google Search</span><br />
            <span class="description">The world’s information</span><br />
            <span class="sub">Free</span>
        </div>
        </div>
    </div>,
      document.getElementById('tile')
 );

{% endhighlight %}

Add the following styles to customize the tile images with template support.

{% highlight css %}

 <style>
        #appimage {
            background-image: url("http://js.syncfusion.com/UG/mobile/content/google.png");
            background-position: center center;
            background-repeat: no-repeat;
            background-size: 50% auto;
            display: table-cell;
            width: 45%;
        }

        .tileMargin {
            display: table-cell;
            padding-top: 25px;
        }

        .e-tile-template {
            display: table;
            height: 100%;
            width: 100%;
        }
    </style>
   
{% endhighlight %}

Run the above code to get the following output.

![](Getting-Started_images\Getting-Started_img3.png)

N> To get the complete API list for all the Syncfusion component’s properties from the [API reference](https://help.syncfusion.com/api/js/ejtile)
