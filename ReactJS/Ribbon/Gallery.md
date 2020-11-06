---
layout: post
title: Gallery
description: gallery
documentation: ug
platform: React JS
keywords: gallery,ribbon gallery
---

# Gallery

Galleries are used to display items that can be arranged in a grid-type layout. Items in the gallery can be customized as `button`/`menu` to display images, text, or both images and text. You can set `type` of group as `gallery`.

## Gallery Items

`Gallery items` are collection of the items to be included in the main gallery. You can set `text` and `toolTip` to gallery item which can also be customized with `buttonSettings`.
 
Number of `columns` to display in gallery for each row should be specified and the Number of columns in Expanded State `(expandedColumns)` can be customized, if not set, `columns` count will be set as default. 

N> The `itemHeight` and `itemWidth` for gallery item can be set, if not set default values will be used.


{% highlight html %}

    <div id="ribbon-default"></div>
    <script src="app/ribbon/default.js"></script>
    <ul id="ribbonmenu1">
    <li><a>FILE</a>
       <ul>
         <li><a>New</a></li>
         <li><a>Open</a></li>
         <li><a>Save</a></li>
         <li><a>Save As</a></li>
         <li><a>Print</a></li>
	   </ul>
    </li>
    </ul>
     <style type="text/css">
        .e-gallerycontent1 {
            background-position: 0 -105px;
        }
        .e-gallerycontent2 {
            background-position: -69px -105px;
        }
        .e-gallerycontent3 {
            background-position: -136px -105px;
        }
        .e-gallerycontent4 {
            background-position: 0 -53px;
        }
        .e-gbtnposition {
            margin-top: 5px;
        }
        .e-gbtnimg {
            background-image: url("content/ej/themes/common-images/ribbon/homegallery.png");
            background-repeat: no-repeat;
            height: 64px;
            width: 64px;
        }
    </style>
{% endhighlight %}

{% highlight html %}

    ReactDOM.render(
    <div>
     <EJ.Ribbon width="500px" applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu1" applicationTab-menuSettings-openOnClick={false}>
      <tabs>
        <tab id="home" text="HOME">
           <groups>
					 <group text="Gallery" alignType="rows">
                           <content>
                                                    <content>
                                                        <groups>
                                                            <group id="Gallery" columns={2} itemHeight={54} itemWidth={68} expandedColumns="3" type="gallery">
                                                                <galleryItems>
                                                                    <galleryItem text="GalleryContent1" buttonSettings-contentType="imageonly" buttonSettings-prefixIcon="e-icon e-gallerycontent1 e-gbtnimg" buttonSettings-cssClass="e-gbtnposition"></galleryItem>
                                                                    <galleryItem text="GalleryContent2"  buttonSettings-contentType="imageonly" buttonSettings-prefixIcon="e-icon e-gallerycontent2 e-gbtnimg" buttonSettings-cssClass="e-gbtnposition"></galleryItem>
                                                                    <galleryItem text="GalleryContent3"  buttonSettings-contentType="imageonly" buttonSettings-prefixIcon="e-icon e-gallerycontent3 e-gbtnimg" buttonSettings-cssClass="e-gbtnposition"></galleryItem>
                                                                    <galleryItem text="GalleryContent4"  buttonSettings-contentType="imageonly" buttonSettings-prefixIcon="e-icon e-gallerycontent4 e-gbtnimg" buttonSettings-cssClass="e-gbtnposition"></galleryItem>
                                                                </galleryItems>
                                                            </group>
                                                        </groups>
                                                    </content>
                                                </content>
                                            </group>
				</groups>  
        </tab>	
      </tabs>
    </EJ.Ribbon>
    </div>,
    document.getElementById('ribbon-default')
    );

{% endhighlight %}


![](/js/Ribbon/Gallery_images/Gallery_img1.png)

Ribbon Gallery.
{:.caption}


![](/js/Ribbon/Gallery_images/Gallery_img2.png)

Gallery at Expanded State
{:.caption}

## Custom Gallery Items

`Custom gallery items` are the additional items to be displayed at gallery expanded state. You can set `customItemType` as `button` or `menu`, Default is `button`.

You can also set `text` and `toolTip` to custom gallery item which can also be customized with `buttonSettings`/`menuSettings` based on the `customItemType` specified.


{% highlight html %}

    <div id="ribbon-default"></div>
    <script src="app/ribbon/default.js"></script>
    <ul id="ribbonmenu1">
    <li><a>FILE</a>
       <ul>
         <li><a>New</a></li>
         <li><a>Open</a></li>
         <li><a>Save</a></li>
         <li><a>Save As</a></li>
         <li><a>Print</a></li>
	   </ul>
    </li>
    </ul>
     <style type="text/css">
        .e-gallerycontent1 {
            background-position: 0 -105px;
        }
        .e-gallerycontent2 {
            background-position: -69px -105px;
        }
        .e-gallerycontent3 {
            background-position: -136px -105px;
        }
        .e-gallerycontent4 {
            background-position: 0 -53px;
        }
        .e-gbtnposition {
            margin-top: 5px;
        }
        .e-gbtnimg {
            background-image: url("content/ej/themes/common-images/ribbon/homegallery.png");
            background-repeat: no-repeat;
            height: 64px;
            width: 64px;
        }
    </style>


{% endhighlight %}


{% highlight html %}

     ReactDOM.render(
    <div>
     <EJ.Ribbon width="500px" applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu1" applicationTab-menuSettings-openOnClick={false}>
      <tabs>
        <tab id="home" text="HOME">
           <groups>
					 <group text="Gallery" alignType="rows">
                           <content>
                                                    <content>
                                                        <groups>
                                                            <group id="Gallery" columns={2} itemHeight={54} itemWidth={68} expandedColumns="3" type="gallery">
                                                                <galleryItems>
                                                                    <galleryItem text="GalleryContent1" buttonSettings-contentType="imageonly" buttonSettings-prefixIcon="e-icon e-gallerycontent1 e-gbtnimg" buttonSettings-cssClass="e-gbtnposition"></galleryItem>
                                                                    <galleryItem text="GalleryContent2"  buttonSettings-contentType="imageonly" buttonSettings-prefixIcon="e-icon e-gallerycontent2 e-gbtnimg" buttonSettings-cssClass="e-gbtnposition"></galleryItem>
                                                                    <galleryItem text="GalleryContent3"  buttonSettings-contentType="imageonly" buttonSettings-prefixIcon="e-icon e-gallerycontent3 e-gbtnimg" buttonSettings-cssClass="e-gbtnposition"></galleryItem>
                                                                    <galleryItem text="GalleryContent4"  buttonSettings-contentType="imageonly" buttonSettings-prefixIcon="e-icon e-gallerycontent4 e-gbtnimg" buttonSettings-cssClass="e-gbtnposition"></galleryItem>
                                                                </galleryItems>
																  <customGalleryItems>
                                                                    <customGalleryItem customItemType="menu" menuId="extramenu" menuSettings-openOnClick={false}></customGalleryItem>
                                                                    <customGalleryItem text="Clear Formatting" toolTip="Clear Formatting" customItemType="button" buttonSettings-cssClass="e-extrabtnstyle"></customGalleryItem>
                                                                </customGalleryItems>
                                                            </group>
                                                        </groups>
                                                    </content>
                                                </content>
                                            </group>
				</groups>  
        </tab>
      </tabs>
      </EJ.Ribbon>
     </div>,
    document.getElementById('ribbon-default')
    );
    
{% endhighlight %}

![](/js/Ribbon/Gallery_images/Gallery_img3.png)