---
layout: post
title:  Tab
description: tab 
documentation: ug
platform: React JS
keywords: ribbon tab
---

# Tab

Tab is a collection of control `groups` which enables you to organize related commands into single view.  Tabs can be added to Ribbon using `tabs` property. `id` & `text` properties are used to set unique ID and header text to Tab. The manipulation of given text tab in the ribbon control can be done by using  [`addTab`](https://help.syncfusion.com/api/js/ejribbon#methods:addtab), [`removeTab`](https://help.syncfusion.com/api/js/ejribbon#methods:removetab), [`hideTab`](https://help.syncfusion.com/api/js/ejribbon#methods:hidetab),
[`showTab`](https://help.syncfusion.com/api/js/ejribbon#methods:showtab) methods and [`tabAdd`](https://help.syncfusion.com/api/js/ejribbon#events:tabadd), [`tabCreate`](https://help.syncfusion.com/api/js/ejribbon#events:tabcreate), [`tabRemove`](https://help.syncfusion.com/api/js/ejribbon#events:tabremove), [`tabClick`](https://help.syncfusion.com/api/js/ejribbon#events:tabclick) and [`tabSelect`](https://help.syncfusion.com/api/js/ejribbon#events:tabselect) events.


{% highlight html %}

     <div id="ribbon-resize"></div>
     <div id="sendReceive">
        Send/Receive All Folders
    </div>
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
    <EJ.Ribbon width="50%" applicationTab-type="menu" applicationTab-menuItemID="ribbonmenu1" applicationTab-menuSettings-openOnClick={false}>
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
		     <tab id="sendrec" text="Send/Receive">
           <groups>
              <group text="Send/Receive" type="custom" contentID="sendReceive">
			  </group>			  
			  </groups>  
        </tab>     
      </tabs>
    </EJ.Ribbon>,
    document.getElementById('ribbon-resize')
    );
     
{% endhighlight %}

![](/js/Ribbon/Tab_images/Tab_img1.png)

