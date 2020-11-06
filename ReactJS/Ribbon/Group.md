---
layout: post
title:  Group
description: group
documentation: ug
platform: React JS
keywords: group,ribbon group
---

# Group

`Group` is a collection of logical content groups that are combined under related Tab. Each group can be defined using content groups or custom content.

## Adding Tab Groups

Group items can be added to Tabs by specifying `text` and corresponding `content` to be displayed. The content of group can be specified as either with `content` collection, `contentID` or `customContent`. You can add tab group dynamically in the ribbon control with given tab index, tab group object and group index position by using [`addTabGroup`](https://help.syncfusion.com/api/js/ejribbon#methods:addtabgroup) method.

### Adding Content

Add content to Group item which is based on `type` of content specified. The available types are `button`, `splitButton`, `toggleButton`,`gallery`, and `dropDownList`.

Groups and defaults settings can be added with the `content`. You can add group content dynamically in the ribbon control with given tab index, group index, content, content index and sub group index position by using [`addTabGroupContent`](https://help.syncfusion.com/api/js/ejribbon#methods:addtabgroupcontent).

#### _Defaults_

The [`tabs.groups.content.defaults.height`](https://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-content-defaults-height), [`tabs.groups.content.defaults.width`](https://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-content-defaults-width), 
[`tabs.groups.content.defaults.type`](https://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-content-defaults-type), [`tabs.groups.content.defaults.isBig`](https://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-content-defaults-isbig) property to the controls in the [`group`](https://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-content-groups) can be specified commonly.

The `height` & `width` applicable to button, split button, dropdown list ,Toggle button controls and `isBig` applicable to only button controls ( button, split , toggle)

#### _Adding Content Groups_

Controls such as button, split button, dropdown list, toggle button, gallery in the subgroup of the Ribbon tab can be rendered. All of these can be customized using its corresponding settings property such as `buttonSettings`, `dropdownSettings`, etc.

Custom controls or items (such as table, div etc.) can be added when the `type` set as `custom`. `defaults` control settings of group can be specified for an `individual group` instead of specifying them to groups collection commonly.

`Tooltip` and `Custom Tooltip` can be specified for each group controls.

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
	
{% endhighlight %}


{% highlight html %}
	
	"use strict"; 
	ReactDOM.render(
    <div>
     <EJ.Ribbon width="500px" applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu1" applicationTab-menuSettings-openOnClick={false}>
      <tabs>
        <tab id="home" text="HOME">
           <groups>
			  <group text="Clipboard" alignType="columns">
                <content>
                    <content defaults-type="splitbutton" defaults-width={50} defaults-height={70}>
                       <groups>
                           <group id="paste" text="Paste" customTooltip-prefixIcon="e-pastetip" splitButtonSettings-contentType="imageonly" splitButtonSettings-prefixIcon="e-icon e-ribbon e-ribbonpaste" splitButtonSettings-targetID="pasteSplit1" splitButtonSettings-buttonMode="dropdown" splitButtonSettings-arrowPosition="right" splitButtonSettings-click="executeAction">
                           </group>
                        </groups>
                      </content> 
                        </content>
                     </group>
                     <group text="Font" alignType="columns">
                        <content>
						 <content defaults-type="button" defaults-width={75} defaults-height={30}defaults-isBig={false}>
                         <groups>
                              <group id="cut" text="Cut Over" buttonSettings-prefixIcon="e-icon e-ribbon e-ribboncut" buttonSettings-click="executeAction">
                              </group>
                              <group id="copy" text="Copy" buttonSettings-prefixIcon="e-icon e-ribbon e-ribboncopy" buttonSettings-click="executeAction">
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

![](/js/Ribbon/Group_images/Group_img1.png)

#### _Enable Separator_ 

Separates the control from the next control in the group when group `alignType` is `row`. Set “true” to `enableSeparator`.

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
	
{% endhighlight %}

{% highlight html %}

    "use strict"; 
	ReactDOM.render(
    <div>
    <EJ.Ribbon width="500px" applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu1" applicationTab-menuSettings-openOnClick={false}>
      <tabs>
        <tab id="home" text="HOME">
           <groups>
		      <group text="New" alignType="rows">
			    <content>
				   <content defaults-type="button" defaults-width={60} defaults-height={60} defaults-isBig={false}>
				      <groups>
					     <group id="new" text="New" toolTip="New" enableSeparator="true" buttonSettings-width="100">				 
						 </group>
						   <group id="font" text="Font" toolTip="font" buttonSettings-width="150">
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

![](/js/Ribbon/Group_images/Group_img2.png)

### Adding Custom Content 

Set group `type` as `custom` to add custom items such as div, table and custom controls. With type as custom, content can be added in two ways as specified below.

*	HTML contents can be directly added into the groups as string content using `customContent` property
*	Custom template id can be specified to render those specific custom template using `contentID` property

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
	
{% endhighlight %}
 

{% highlight html %}

	ReactDOM.render(
    <div>
     <EJ.Ribbon width="500px" applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu1" applicationTab-menuSettings-openOnClick={false}>
      <tabs>
        <tab id="home" text="HOME">
           <groups>
		      <group text="New" type="custom" customContent="<button id='customContent'>Using Custom Content</button>">
			  </group>
              <group text="Data" type="custom" contentID="btn" toolTip="font" buttonSettings-width="150">
			  </group>			  
			  </groups>  
        </tab>     
      </tabs>
    </EJ.Ribbon>
    </div>,
    document.getElementById('ribbon-default')
    );

{% endhighlight %}

![](/js/Ribbon/Group_images/Group_img3.png)

## Group Expander

Set `enableGroupExpander` as true to show Group Expander for each group in Tab. These expanders can be customized using `groupExpand` event, such as to show popup dialog. To specify tooltip for the group expander of the group [`tabs.groups.groupExpanderSettings`](https://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-groupexpandersettings) and 
[`tabs.groups.groupExpanderSettings.toolTip`](https://help.syncfusion.com/api/js/ejribbon#members:tabs-groups-groupexpandersettings-tooltip) can be used.

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
	
{% endhighlight %}

{% highlight html %}

    ReactDOM.render(
    <div>
    <EJ.Ribbon width="500px" applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu1" applicationTab-menuSettings-openOnClick={false}>
      <tabs>
        <tab id="home" text="HOME">
           <groups>
              <group text="New" type="custom" enableGroupExpander="true" contentID="btn" toolTip="font" buttonSettings-width="150">
			  </group>			  
			  </groups>  
        </tab>     
      </tabs>
    </EJ.Ribbon>
    </div>,
    document.getElementById('ribbon-default')
    );

{% endhighlight %}

![](/js/Ribbon/Group_images/Group_img4.png)

