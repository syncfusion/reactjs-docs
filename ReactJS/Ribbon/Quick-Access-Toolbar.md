---
layout: post
title:  Quick Access Toolbar
description: quick access toolbar
documentation: ug
platform: React JS
keywords: quick access toolbar,ribbon quick access toolbar
---

# Quick Access Toolbar

Quick Access Toolbar provides the shortcuts to the most commonly used commands by placing the controls at the Quick Access Toolbar section. It can be placed at the top or bottom of the Ribbon.

Set [`showQAT`](http://help.syncfusion.com/api/js/ejribbon#members:showqat) as true to enable Quick Access Toolbar in Ribbon. It supports the Button, Split Button, Toggle Button controls. The [`quickAccessMode`](http://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-content-groups-quickaccessmode) is used to change the controls state in Quick Access Toolbar through options as `toolbar`,`menu` and `none`. Default value is `none` and QAT toolbar is created with specified controls added in Toolbar.

The `toolbar` option used to set controls visibility in Quick Access Toolbar.The `menu` option shows the controls in Quick Access Menu and does not show controls in Quick Access Toolbar.

Once the controls are visible in Toolbar , then controls state will be set as ticked in Quick Access Menu and vice versa.  

The client side event for Quick Access Toolbar menu click is [`qatMenuItemClick`](http://help.syncfusion.com/api/js/ejribbon#events:qatmenuitemclick) and it will be triggered with QAT menu item click.

`More Commands` command provides with Quick Access Menu. This can be customized using [`qatMenuItemClick`](http://help.syncfusion.com/api/js/ejribbon#events:qatmenuitemclick) event, such as to show popup dialog. 

{% highlight html %}

     <div id="ribbon-quickaccesstoolbar"></div>
     <script src="app/ribbon/quickaccesstoolbar.js"></script>

{% endhighlight %}

{% highlight html %}

	    "use strict"; 
     ReactDOM.render(
    <div>
    <ul id="ribbonmenu3">
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
    <ul id="pasteSplit3">
    <li><a>Paste</a></li>
    </ul>
    <EJ.Ribbon width="100%" allowResizing={true} applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu3" applicationTab-menuSettings-openOnClick={false} showQAT={true}>
      <tabs>
        <tab id="home" text="HOME">
           <groups>
		     
			  <group text="splitbutton" alignType="columns">
                <content>
                    <content defaults-type="splitbutton" defaults-width={60} defaults-height={70}>
                       <groups>
                           <group id="paste" text="Paste" quickAccessMode="toolbar" customTooltip-prefixIcon="e-pastetip" splitButtonSettings-contentType="imageonly" splitButtonSettings-prefixIcon="e-icon e-ribbon e-ribbonpaste" splitButtonSettings-targetID="pasteSplit3" splitButtonSettings-buttonMode="dropdown" splitButtonSettings-arrowPosition="bottom" splitButtonSettings-click="executeAction">
                           </group>
                        </groups>
                      </content>
                    
                        </content>
                     </group>
                     <group text="button" alignType="rows">
                        <content>
					
                          <content defaults-isBig={false}>
                             <groups>
							 <group id="italic" type="togglebutton" quickAccessMode="toolbar" toggleButtonSettings-contentType="imageonly" toggleButtonSettings-defaultText="Italic" toggleButtonSettings-activeText="Italic" toggleButtonSettings-defaultPrefixIcon="e-icon e-ribbon e-resitalic" toggleButtonsettings-activePrefixIcon="e-icon e-ribbon e-resitalic" toggleButtonSettings-click="executeAction"></group>
                             </groups>
                          </content>
					    </content>
                     </group>
					 <group text="togglebutton" alignType="rows">
                        <content>
                          <content defaults-isBig={false}>
                             <groups>
                                 <group id="bold" text="bold" type="togglebutton" quickAccessMode="toolbar" toggleButtonSettings-contentType="imageonly" toggleButtonSettings-defaultText="Bold" toggleButtonsettings-activeText="Bold" toggleButtonSettings-defaultPrefixIcon="e-icon e-ribbon e-resbold" toggleButtonSettings-activePrefixIcon="e-icon e-ribbon e-resbold" toggleButtonSettings-click="executeAction"></group>
                             </groups>
                          </content>
					    </content>
                     </group>
				</groups>  
        </tab>
      </tabs>
     </EJ.Ribbon>
    </div>,
    document.getElementById('ribbon-quickaccesstoolbar')
    );

{% endhighlight %}

![](/js/Ribbon/Quick-Access-Toolbar_images/Quick-Access-Toolbar_img1.png)
