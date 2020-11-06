---
layout: post
title: Globalization and Localization with Ribbon widget for Syncfusion Essential JS
description: How to use globalization and localization 
platform: React JS
control: Ribbon
documentation: ug
---
# Globalization and Localization

## Localization

The localization support allows to customize the display of text within the Ribbon in a user-specific culture and locale. The Ribbon control can be localized in specific culture using the common API [`locale`](http://help.syncfusion.com/api/js/ejribbon#members:locale) along with the collection of localized words defined for that culture using the ej.Ribbon.Locale [culture-code].Please find the table with list of properties and its value in locale object.

<table>
<tr>
<th>
Locale key words </th><th>
Text</th></tr>
<tr>
<td>
CustomizeQuickAccess</td><td>
Customize Quick Access Toolbar</td></tr>
<tr>
<td>
RemoveFromQuickAccessToolbar</td><td>
Remove from Quick Access Toolbar</td></tr>
<tr>
<td>
AddToQuickAccessToolbar</td><td>
Add to Quick Access Toolbar</td></tr>
<tr>
<td>
ShowAboveTheRibbon</td><td>
Show Above the Ribbon</td></tr>
<tr>
<td>
ShowBelowTheRibbon</td><td>
Show Below the Ribbon</td></tr>
<tr>
<td>
MoreCommands</td><td>
More Commands...</td></tr>
</table>

N> By default, the Ribbon control is localized in `en-US` culture.

For further information on – how to refer the required culture scripts into your application, refer [`here`](http://help.syncfusion.com/js/localization).

{% highlight html %}

    <div id="ribbon-resize"></div>
    <script src="app/ribbon/resize.js"></script>
    <ul id="ribbonmenu1">
    <li><a>FILE</a>
       <ul>
         <li><a>New</a></li>
         <li><a>Open</a></li>
         <li><a>Save</a></li>
	   </ul>
    </li>
    </ul>

{% endhighlight %}

{% highlight html %}

        "use strict"; 
        ej.Ribbon.Locale["es-ES"] = {
		CustomizeQuickAccess: "Agordu Rapida Aliro",
		RemovefromQuickAccessToolbar: "Forigu de Rapida Aliro Ilobreto",
		AddtoQuickAccessToolbar: "Aldoni al Rapida Aliro Ilobreto",
		ShowAbovetheRibbon: "Montru Super la Ribbona",
		ShowBelowtheRibbon: "Montru Sube la Ribbon",
		MoreCommands: "pli Komando"
	};
    ReactDOM.render(
    <div>
    <EJ.Ribbon width="100%" locale="es-ES" applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu3" applicationTab-menuSettings-openOnClick={false} showQAT={true}>
      <tabs>
        <tab id="home" text="HOME">
           <groups>
			  <group text="Clipboard" alignType="columns">
                <content>
                    <content defaults-type="splitbutton" defaults-width={60} defaults-height={70}>
                       <groups>
                           <group id="paste" text="Paste" quickAccessMode="toolbar" customTooltip-prefixIcon="e-pastetip" splitButtonSettings-contentType="imageonly" splitButtonSettings-prefixIcon="e-icon e-ribbon e-ribbonpaste" splitButtonSettings-targetID="pasteSplit3" splitButtonSettings-buttonMode="dropdown" splitButtonSettings-arrowPosition="bottom" splitButtonSettings-click="executeAction">
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
    document.getElementById('ribbon-quickaccesstoolbar')
    );

{% endhighlight %}

![](Globalizationandlocalization_images/Globalizationandlocalization._img1.png)

## Right to Left - RTL

By default, Ribbon render its content and layout from left to right. To customize Ribbon direction, you can change direction from LTR to RTL by using [`enableRTL`](http://help.syncfusion.com/api/js/ejribbon#members:enablertl) as true.

{% highlight html %}

    <div id="ribbon-resize"></div>
    <script src="app/ribbon/resize.js"></script>
    <ul id="ribbonmenu1">
    <li><a>FILE</a>
       <ul>
         <li><a>New</a></li>
         <li><a>Open</a></li>
         <li><a>Save</a></li>
	   </ul>
    </li>
    </ul>

{% endhighlight %}

{% highlight html %}

    "use strict"; 
    ReactDOM.render(
    <EJ.Ribbon width="500px" enableRTL={true} applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu1" applicationTab-menuSettings-openOnClick={false}>
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
			   <group text="Clipboard" alignType="columns">
                <content>
                    <content defaults-type="splitbutton" defaults-width={50} defaults-height={70}>
                       <groups>
                           <group id="paste" text="Paste" customTooltip-prefixIcon="e-pastetip" splitButtonSettings-contentType="imageonly" splitButtonSettings-prefixIcon="e-icon e-ribbon e-ribbonpaste" splitButtonSettings-targetID="pasteSplit1" splitButtonSettings-buttonMode="dropdown" splitButtonSettings-arrowPosition="bottom" splitButtonSettings-click="executeAction">
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

![](Globalizationandlocalization_images/Globalizationandlocalization._img2.png)


