---
layout: post
title:  Screen Tips
description: screen tips
documentation: ug
platform: React JS
keywords: screen tips,ribbon screen tips
---

# Screen Tips

ScreenTip/Tooltip is used to reduce the controls related Help that are needed to the end user to do control related actions.

## HTML Tooltip

Standard `html tooltip` can be set using `tooltip` property of each group item.

{% highlight html %}

    <div id="ribbon-resize"></div>
    <script src="app/ribbon/resize.js"></script>
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

{% endhighlight %}


{% highlight html %}

    "use strict"; 
    ReactDOM.render(
    <EJ.Ribbon width="40%" applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu1" applicationTab-menuSettings-openOnClick={false}>
      <tabs>
        <tab id="home" text="HOME">
           <groups>
			  <group text="Clipboard" alignType="rows">
                <content>
                    <content defaults-type="button" defaults-width={60} defaults-height={70}>
                       <groups>
                         <group id="cut" text="Cut" toolTip="Remove the selection and put it on clipboard" buttonSettings-prefixIcon="e-icon e-ribbon e-ribboncut" buttonSettings-click="executeAction">
                              </group>
                              <group id="copy" text="Copy"  toolTip="Put a copy of selection on clipboard" buttonSettings-contentType="textandimage" buttonSettings-prefixIcon="e-icon e-ribbon e-ribboncopy" buttonSettings-click="executeAction">
                              </group>
                        </groups>
                      </content>
                        </content>
                     </group>
                    
				</groups>  
        </tab>
      </tabs>
     </EJ.Ribbon>,
    document.getElementById('ribbon-resize')
    );
    
{% endhighlight %}

![](/js/Ribbon/Screen-Tips_images/Screen-Tips_img1.png)

## Custom Tooltip

Custom Tooltip is used to set detailed help to the user about the controls. You can set `title`, `content` and `prefixIcon` class to customize the tooltip with icons.

### For Groups 

`Custom tooltip` for each group controls can be specified. Such as to the controls button, split button, dropdown list etc.

{% highlight html %}

    <div id="ribbon-resize"></div>
    <script src="app/ribbon/resize.js"></script>
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
        .e-pastetip {
            background-image: url("content/ej/themes/common-images/ribbon/paste.png");
            background-repeat: no-repeat;
            height: 64px;
            width: 64px;
        }
    </style>

{% endhighlight %}


{% highlight html %}

    "use strict"; 
    ReactDOM.render(
    <EJ.Ribbon width="40%" applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu1" applicationTab-menuSettings-openOnClick={false}>
      <tabs>
        <tab id="home" text="HOME">
           <groups>
			  <group text="Clipboard" alignType="rows">
                <content>
                    <content defaults-type="button" defaults-width={60} defaults-height={70}>
                       <groups>
                        <group id="paste" text="Paste" customToolTip-title="Paste"customToolTip-content="<h6>Paste the content.<br/><br/>Add content on the Clipboard to your document.</h6>" customTooltip-prefixIcon="e-pastetip" splitButtonSettings-contentType="imageonly" splitButtonSettings-prefixIcon="e-icon e-ribbon e-ribbonpaste">
                           </group>
                              <group id="copy" text="Copy"  toolTip="Put a copy of selection on clipboard" buttonSettings-contentType="textandimage" buttonSettings-prefixIcon="e-icon e-ribbon e-ribboncopy" buttonSettings-click="executeAction">
                              </group>
                        </groups>
                      </content>
                        </content>
                     </group>
                    
				</groups>  
        </tab>
      </tabs>
     </EJ.Ribbon>,
    document.getElementById('ribbon-resize')
    );

{% endhighlight %}

![](/js/Ribbon/Screen-Tips_images/Screen-Tips_img2.png)

### For Gallery

`Custom tooltip`for each `gallery` and `custom gallery` items button control can be specified. 

N> Custom gallery item `menu` is not supported to Custom tooltip.


{% highlight html %}
  
    <div id="ribbon-resize"></div>
    <script src="app/ribbon/resize.js"></script>
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

    <"use strict"; 
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
                                                                    <galleryItem text="Style 1" 
																	customToolTip-title="Style 1" customToolTip-content="<I>Style 1 to customize the table</I>"
																	buttonSettings-contentType="imageonly" buttonSettings-prefixIcon="e-icon e-gallerycontent1 e-gbtnimg" buttonSettings-cssClass="e-gbtnposition"></galleryItem>
                                                                    <galleryItem text="Style 2" 
                                                                    customToolTip-title="Style 2" customToolTip-content="<I>Style 2 to customize the table</I>"
																	buttonSettings-contentType="imageonly" buttonSettings-prefixIcon="e-icon e-gallerycontent2 e-gbtnimg" buttonSettings-cssClass="e-gbtnposition"></galleryItem>
                                                                    <galleryItem text="Style 3"  
																	customToolTip-title="Style 3" customToolTip-content="<I>Style 3 to customize the table</I>"
																	buttonSettings-contentType="imageonly" buttonSettings-prefixIcon="e-icon e-gallerycontent3 e-gbtnimg" buttonSettings-cssClass="e-gbtnposition"></galleryItem>
                                                                    <galleryItem text="GalleryContent4" 
                                                                     customToolTip-title="Style 4" customToolTip-content="<I>Style 4 to customize the table</I>"
																	buttonSettings-contentType="imageonly" buttonSettings-prefixIcon="e-icon e-gallerycontent4 e-gbtnimg" buttonSettings-cssClass="e-gbtnposition"></galleryItem>
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
    document.getElementById('ribbon-resize')
    );

{% endhighlight %}

![](/js/Ribbon/Screen-Tips_images/Screen-Tips_img3.png)

### For Expand Pin

Specifies the `custom tooltip` for expand pin in the Ribbon. 


{% highlight html %}

    <div id="ribbon-resize"></div>
    <script src="app/ribbon/resize.js"></script>
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
  
{% endhighlight %}


{% highlight html %}

    "use strict"; 
    ReactDOM.render(
    <div>
     <EJ.Ribbon width="500px" expandPinSettings-customToolTip-title="Collapse the Ribbon"
                     expandPinSettings-customToolTip-content="<h6>Click the icon to collapse the Ribbon.</h6>" 
            applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu1" applicationTab-menuSettings-openOnClick={false}>
      <tabs>
        <tab id="home" text="HOME">
           <groups>
					 <group text="New" alignType="rows">
			    <content>
				   <content defaults-type="button" defaults-width={60} defaults-height={60} defaults-isBig={false}>
				      <groups>
					     <group id="new" text="New" toolTip="New" buttonSettings-contentType="imageonly" buttonSettings-imagePosition="imagetop" buttonSettings-prefixIcon="e-icon e-ribbon e-new" buttonSettings-click="executeAction">
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
    document.getElementById('ribbon-resize')
    );

{% endhighlight %}

![](/js/Ribbon/Screen-Tips_images/Screen-Tips_img4.png)

### For Collapse Pin

Specifies the `custom tooltip` for collapse pin in the Ribbon. 

{% highlight html %}

    < <div id="ribbon-resize"></div>
    <script src="app/ribbon/resize.js"></script>
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

{% endhighlight %}

{% highlight html %}

    "use strict"; 
    ReactDOM.render(
    <div>
     <EJ.Ribbon width="500px" collapsePinSettings-customToolTip-title="Pin the Ribbon"
                     collapsePinSettings-customToolTip-content="<h6>Keep it open while you work</h6>" 
            applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu1" applicationTab-menuSettings-openOnClick={false}>
      <tabs>
        <tab id="home" text="HOME">
           <groups>
					 <group text="New" alignType="rows">
			    <content>
				   <content defaults-type="button" defaults-width={60} defaults-height={60} defaults-isBig={false}>
				      <groups>
					     <group id="new" text="New" toolTip="New" buttonSettings-contentType="imageonly" buttonSettings-imagePosition="imagetop" buttonSettings-prefixIcon="e-icon e-ribbon e-new" buttonSettings-click="executeAction">
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
    document.getElementById('ribbon-resize')
    );
{% endhighlight %}

![](/js/Ribbon/Screen-Tips_images/Screen-Tips_img5.png)

### For GroupExpander

`Custom tooltip` for each group expander can be specified.

{% highlight html %}

      <div id="ribbon-resize"></div>
    <script src="app/ribbon/resize.js"></script>
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
  
{% endhighlight %}

{% highlight html %}

    ReactDOM.render(
    <div>
    <EJ.Ribbon width="500px" applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu1" applicationTab-menuSettings-openOnClick={false}>
      <tabs>
        <tab id="home" text="HOME">
		 <groups>
           <group text="New" enableGroupExpander="true" groupExpanderSettings-customToolTip-title="Clipboard" groupExpanderSettings-customToolTip-content="<h6>Show a popup for the Clipboard group.</h6>" alignType="rows">
			    <content>
				   <content defaults-type="button" defaults-width={60} defaults-height={60} defaults-isBig={false}>
				      <groups>
					     <group id="new" text="New" toolTip="New" buttonSettings-contentType="imageonly" buttonSettings-imagePosition="imagetop" buttonSettings-prefixIcon="e-icon e-ribbon e-new" buttonSettings-click="executeAction">
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
    document.getElementById('ribbon-resize')
    );   

{% endhighlight %}

![](/js/Ribbon/Screen-Tips_images/Screen-Tips_img6.png)