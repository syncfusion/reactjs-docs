---
layout: post
title: Controls-Support for Syncfusion Ribbon
description: controls support
documentation: ug
platform: reactjs
keywords: controls support,ribbon controls support
---

# Controls Support

Button, Split Button, DropdownList, Toggle button, Gallery and Custom controls can be added to each groups. You can set `type` property in group to define the controls. Default `type` is `button`. 

N> 1. You can specify type either to `group’s collection` or to each `group`.
N> 2. For `type` property you can assign either string value (“splitbutton”) or enum value (ej.Ribbon.type.splitButton).


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
    <ul id="pasteSplit1">
    <li><a>Paste</a></li>
    </ul>

   

{% endhighlight %}


{% highlight html %}

    "use strict"; 
    var fontfamily = ["Segoe UI", "Arial", "Times New Roman", "Tahoma", "Helvetica"];
    var  fontsize = ["1pt", "2pt", "3pt", "4pt", "5pt"];
    ReactDOM.render(
    <EJ.Ribbon width="100%" applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu1" applicationTab-menuSettings-openOnClick={false}>
      <tabs>
        <tab id="home" text="HOME">
           <groups>
		      <group text="New" alignType="rows">
			    <content>
				   <content defaults-type="button" defaults-width={60} defaults-height={60} defaults-isBig={false}>
				      <groups>
					     <group id="new" text="New" toolTip="New" buttonSettings-contentType="imageonly" buttonSettings-imagePosition="imagetop" buttonSettings-prefixIcon="e-icon e-ribbon e-new" buttonSettings-click={executeAction}>
						 </group>
					   </groups>
					</content>
				</content>
			  </group>
			  <group text="Clipboard" alignType="columns">
                <content>
                    <content defaults-type="splitbutton" defaults-width={60} defaults-height={70}>
                       <groups>
                           <group id="paste" text="Paste" customTooltip-prefixIcon="e-pastetip" splitButtonSettings-contentType="imageonly" splitButtonSettings-prefixIcon="e-icon e-ribbon e-ribbonpaste" splitButtonSettings-targetID="pasteSplit1" splitButtonSettings-buttonMode="dropdown" splitButtonSettings-arrowPosition="bottom" splitButtonSettings-click={executeAction}>
                           </group>
                        </groups>
                      </content>
                        </content>
                     </group>
                     <group text="Font" alignType="rows">
                        <content>
						<content defaults-type="dropdownlist" defaults-height={28}>
                              <groups>
                                 <group id="fontfamily" dropdownSettings-dataSource={fontfamily} dropdownSettings-text="Segoe UI" dropdownSettings-select="executeAction" dropdownSettings-width={150}>
                                </group>
                                <group id="fontsize" dropdownSettings-dataSource={fontsize} dropdownSettings-text="1pt" dropdownSettings-select="executeAction" dropdownSettings-width={65}>
                                </group>
                              </groups>
                            </content>
                          <content defaults-isBig={false}>
                             <groups>
                                <group id="bold" text="bold" type="togglebutton" toggleButtonSettings-contentType="imageonly" toggleButtonSettings-defaultText="Bold" toggleButtonsettings-activeText="Bold" toggleButtonSettings-defaultPrefixIcon="e-icon e-ribbon e-resbold" toggleButtonSettings-activePrefixIcon="e-icon e-ribbon e-resbold" toggleButtonSettings-click={executeAction}></group>
                                <group id="italic" type="togglebutton" toggleButtonSettings-contentType="imageonly" toggleButtonSettings-defaultText="Italic" toggleButtonSettings-activeText="Italic" toggleButtonSettings-defaultPrefixIcon="e-icon e-ribbon e-resitalic" toggleButtonsettings-activePrefixIcon="e-icon e-ribbon e-resitalic" toggleButtonSettings-click={executeAction}></group> 
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
