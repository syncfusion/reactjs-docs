---
layout: post
title: Properties, options and events of Syncfusion ejBarcode widget
description: How to use Properties, options and events of Essential JS ejBarcode widget
documentation: UG
platform: ReactJS
metaname: 
metacontent: 
---

# Custom Design for Barcode control.
<ts root="datavisualization" />
The Barcode can be easily configured to the DOM element, such as div. you can create a Barcode with a highly customizable look and feel.

Syntax

ReactDOM.render(EJ.Barcode{})


Example
{:.example}


{% highlight html %}
 

//Create the Barcode by setting the symbologyType and providing input URL to the text property. QR Barcode is rendered by default.
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id="default" text="http://www.syncfusion.com" symbologyType="qrbarcode" xDimension="5" > 
</EJ.Barcode>
</div>,
document.getElementById('barcode- default')
);


{% endhighlight %}









## Members








### barcodeToTextGapHeight `number`
{:#members:barcodetotextgapheight}








Specifies the distance between the Barcode and text below it.

N>    This property is applicable only for one dimensional barcode.


Default Value:
{:.param}






* 10 pixels








Example
{:.example}


{% highlight html %}
 

// Add the below code to set barcodeToTextGapHeight during initialization inside the div container. 
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id=" code39" text=" SYNCFUSION " symbologyType=" code39'" barcodeToTextGapHeight=50 enabled=true>
</EJ.Barcode>
</div>,
document.getElementById('barcode- code39')
);



{% endhighlight %}







### barHeight `number`
{:#members:barheight}








Specifies the height of bars in the Barcode. By modifying the barHeight, the entire Barcode height can be customized. Please refer to [xDimension](/api/js/ejBarcode#xdimensionspan-classtype-signature-type-numbernumberspan) for two dimensional barcode height customization.

N>    This property is applicable only for one dimensional barcode.


Default Value:
{:.param}






* 150 pixels








Example
{:.example}


{% highlight html %}
 

// Add the below code to set barHeight during initialization with inside the div container.  
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id=" code39" text=" SYNCFUSION " barHeight: 50 symbologyType=" code39">
</EJ.Barcode>
</div>,
document.getElementById('barcode- code39')
);


{% endhighlight %}







### darkBarColor `object`
{:#members:darkbarcolor}








Specifies the dark bar color of the Barcode. One dimensional barcode contains a series of dark and light bars which are usually colored as black and white respectively. 

N>    1. For the Barcode should be properly detected by all scanners, choose the best possible contrast color.
N>             2. This property is applicable only for one dimensional barcode.

Default Value:
{:.param}






* black








Example
{:.example}


{% highlight html %}
 
// Add the below code to set darkBarColor during initialization with inside the div container.  
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id=" code39" text=" SYNCFUSION " darkBarColor="blue" symbologyType=" code39">
</EJ.Barcode>
</div>,
document.getElementById('barcode- code39')
);


{% endhighlight %}







### displayText `boolean`
{:#members:displaytext}








Specifies whether the text below the Barcode is visible or hidden.

N>    This property is applicable only for one dimensional barcode.




Default Value:
{:.param}






* true








Example
{:.example}


{% highlight html %}
 

// Add the below code to hide displayText during initialization with inside the div container.  
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id=" code39" text=" SYNCFUSION " displayText=false symbologyType=" code39">
</EJ.Barcode>
</div>,
document.getElementById('barcode- code39')
);


{% endhighlight %}







### enabled `boolean`
{:#members:enabled}








Specifies whether the control is enabled.




Default Value:
{:.param}






* true







Example
{:.example}


{% highlight html %}
 
// Add the below code to hide displayText during initialization with inside the div container.  
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id=" code39" text=" SYNCFUSION " enabled=false symbologyType=" code39">
</EJ.Barcode>
</div>,
document.getElementById('barcode- code39')
);
{% endhighlight %}







### encodeStartStopSymbol `boolean`
{:#members:encodestartstopsymbol}








Specifies the start and stop encode symbol in the Barcode. In one dimensional barcodes, an additional character is added as start and stop delimiters. These symbols are optional and the unique of the symbol allows the reader to determine the direction of the Barcode being scanned.

N>    This property is applicable only for one dimensional barcode.




Default Value:
{:.param}






* true








Example
{:.example}


{% highlight html %}
 
// Add the below code to remove encodeStartStopSymbol during initialization with inside the div container.  
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id=" code39" text=" SYNCFUSION " encodeStartStopSymbol=false symbologyType=" code39">
</EJ.Barcode>
</div>,
document.getElementById('barcode- code39')
);

{% endhighlight %}







### lightBarColor `object`
{:#members:lightbarcolor}








 Specifies the light bar color of the Barcode. One dimensional barcode contains a series of dark and light bars which are usually colored as black and white respectively.

N>    1. For the Barcode should be properly detected by all scanners, choose the best possible contrast color.
N>                     2. This property is applicable only for one dimensional barcode.

Default Value:
{:.param}






* white








Example
{:.example}


{% highlight html %}
 

// Add the below code to set lightBarColor during initialization with inside the div container.   
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id=" code39" text=" SYNCFUSION " lightBarColor="blue" symbologyType=" code39">
</EJ.Barcode>
</div>,
document.getElementById('barcode- code39')
);
{% endhighlight %}







### narrowBarWidth `number`
{:#members:narrowbarwidth}








Specifies the width of the narrow bars in the Barcode. The dark bars in the one dimensional barcode contains random narrow and wide bars based on the provided input which can be specified during initialization.

N>    This property is applicable only for one dimensional barcode.



Default Value:
{:.param}






* 1 pixel








Example
{:.example}


{% highlight html %}
 

// Add the below code to set narrowBarWidth during initialization with inside the div container.  
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id=" code39" text=" SYNCFUSION " narrowBarWidth= 5 symbologyType=" code39">
</EJ.Barcode>
</div>,
document.getElementById('barcode- code39')
);
{% endhighlight %}







### quietZone `object`
{:#members:quietzone}








Specifies the width of the quiet zone. In barcode, a quiet zone is the blank margin on either side of a barcode which informs the reader where a barcode's symbology starts and stops. The purpose of a quiet zone is to prevent the reader from picking up unrelated information.










### quietZone.all `number`
{:#members:quietzone-all}








Specifies the quiet zone around the Barcode.




Default Value:
{:.param}






* 1 pixel








Example
{:.example}


{% highlight html %}
 

// Add the below code to set quiet zone during initialization with inside the div container. 
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id=" code39" text=" SYNCFUSION " quietZone= {   all: 10  } symbologyType=" code39">
</EJ.Barcode>
</div>,
document.getElementById('barcode- code39')
);
{% endhighlight %}







### quietZone.bottom `number`
{:#members:quietzone-bottom}








Specifies the bottom quiet zone of the Barcode.




Default Value:
{:.param}






* 1 pixel








Example
{:.example}


{% highlight html %}
 

// Add the below code to set quiet zone during initialization with inside the div container.  
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id=" code39" text=" SYNCFUSION " quietZone= {   bottom: 10  } symbologyType=" code39">
</EJ.Barcode>
</div>,
document.getElementById('barcode- code39')
);
{% endhighlight %}







### quietZone.left `number`
{:#members:quietzone-left}








Specifies the left quiet zone of the Barcode.




Default Value:
{:.param}






* 1 pixel








Example
{:.example}


{% highlight html %}
 

// Add the below code to set quiet zone during initialization.  
container.  
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id=" code39" text=" SYNCFUSION " quietZone= {   left: 10  } symbologyType=" code39">
</EJ.Barcode>
</div>,
document.getElementById('barcode- code39')
);
{% endhighlight %}







### quietZone.right `number`
{:#members:quietzone-right}








Specifies the right quiet zone of the Barcode.




Default Value:
{:.param}






* 1 pixel








Example
{:.example}


{% highlight html %}
 

// Add the below code to set quiet zone during initialization with inside the div container.  
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id=" code39" text=" SYNCFUSION " quietZone= {   right: 10  } symbologyType=" code39">
</EJ.Barcode>
</div>,
document.getElementById('barcode- code39')
);
{% endhighlight %}







### quietZone.top `number`
{:#members:quietzone-top}








Specifies the top quiet zone of the Barcode.




Default Value:
{:.param}






* 1 pixel








Example
{:.example}


{% highlight html %}
 

// Add the below code to set quiet zone during initialization with inside the div container.
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id=" code39" text=" SYNCFUSION " quietZone= {   top: 10  } symbologyType=" code39">
</EJ.Barcode>
</div>,
document.getElementById('barcode- code39')
);
{% endhighlight %}







### symbologyType `enum`
{:#members:symbologytype}

<ts name="ej.datavisualization.Barcode.SymbologyType"/>

Specifies the type of the Barcode. See <a href="global.html#SymbologyType">SymbologyType</a>
<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">QRBarcode</td>
            <td class="description">Represents the QR code</td>
        </tr>
        <tr>
            <td class="name">DataMatrix</td>
            <td class="description">Represents the Data Matrix barcode</td>
        </tr>
        <tr>
            <td class="name">Code39</td>
            <td class="description">Represents the Code 39 barcode</td>
        </tr>
        <tr>
            <td class="name">Code39Extended</td>
            <td class="description">Represents the Code 39 Extended barcode</td>
        </tr>
        <tr>
            <td class="name">Code11</td>
            <td class="description">Represents the Code 11 barcode</td>
        </tr>
        <tr>
            <td class="name">Codabar</td>
            <td class="description">Represents the Codabar barcode</td>
        </tr>
        <tr>
            <td class="name">Code32</td>
            <td class="description">Represents the Code 32 barcode</td>
        </tr>
        <tr>
            <td class="name">Code93</td>
            <td class="description">Represents the Code 93 barcode</td>
        </tr>
        <tr>
            <td class="name">Code93Extended</td>
            <td class="description">Represents the Code 93 Extended barcode</td>
        </tr>
        <tr>
            <td class="name">Code128A</td>
            <td class="description">Represents the Code 128 A barcode</td>
        </tr>
        <tr>
            <td class="name">Code128B</td>
            <td class="description">Represents the Code 128 B barcode</td>
        </tr>
        <tr>
            <td class="name">Code128C</td>
            <td class="description">Represents the Code 128 C barcode</td>
        </tr>
        <tr>
            <td class="name">UPCBarcode</td>
            <td class="description">Represents the UPC barcode</td>
        </tr>
    </tbody>
</table>
Default Value:
{:.param}

* symbologyType="qrbarcode"








Example
{:.example}


{% highlight html %}
 

// Add the below code to set the SymbologyType during initialization with inside the div container.
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id="default" text="http://www.syncfusion.com" symbologyType="qrbarcode" xDimension="5" > 
</EJ.Barcode>
</div>,
document.getElementById('barcode- default')
);


{% endhighlight %}




### text `string`
{:#members:text}








Specifies the text to be encoded in the Barcode.




Default Value:
{:.param}






* empty








Example
{:.example}


{% highlight html %}
 

// Add the below code to set the text to be encoded while initialization with inside the div container.
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id="default" text="http://www.syncfusion.com" symbologyType="qrbarcode" xDimension="5" > 
</EJ.Barcode>
</div>,
document.getElementById('barcode- default')
);
{% endhighlight %}






### textColor `object`
{:#members:textcolor}








Specifies the color of the text/data at the bottom of the Barcode.

N>    This property is applicable only for one dimensional barcode.




Default Value:
{:.param}






* black








Example
{:.example}


{% highlight html %}
 

// Add the below code to set the textColor while initialization with inside the div container.
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id=" code39" text=" SYNCFUSION " symbologyType="code39" textColor="blue" >
</EJ.Barcode>
</div>,
document.getElementById('barcode- code39')
);

{% endhighlight %}







### wideBarWidth `number`
{:#members:widebarwidth}








Specifies the width of the wide bars in the Barcode. One dimensional barcode usually contains random narrow and wide bars based on the provided which can be customized during initialization.

N>    This property is applicable only for one dimensional barcode.


Default Value:
{:.param}






* 3 pixels








Example
{:.example}


{% highlight html %}
 

// Add the below code to set wideBarWidth during initialization with inside the div container.  
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id=" code39" text=" SYNCFUSION " symbologyType="code39" wideBarWidth= 5>
</EJ.Barcode>
</div>,
document.getElementById('barcode- code39')
);
{% endhighlight %}







### xDimension `number`
{:#members:xdimension}








Specifies the width of the narrowest element(bar or space) in a Barcode. The greater the x dimension, the more easily a barcode reader will scan.

N>    This property is applicable only for two dimensional barcode.


Default Value:
{:.param}






* 4 pixels








Example
{:.example}


{% highlight html %}
 

// Add the below code to set xDimension during initialization with inside the div container.  
"use strict";
ReactDOM.render(
<div className="control">
<EJ.Barcode id="default" text="http://www.syncfusion.com" symbologyType="qrbarcode" xDimension="5" > 
</EJ.Barcode>
</div>,
document.getElementById('barcode- default')
);

{% endhighlight %}





## Events








### load
{:#events:load}








Fires after Barcode control is loaded.

<table class="params">
<thead>
<tr>
<th>Name</th>
<th>Type</th>
<th class="last">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td class="name">{% highlight html %}
argument{% endhighlight %}</td>
<td class="type"><span class="param-type">Object</span></td>
<td class="description last">Event parameters from barcode
<table class="params">
<thead>
<tr>
<th>Name</th>
<th>Type</th>
<th class="last">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td class="name">{% highlight html %}
cancel{% endhighlight %}</td>
<td class="type"><span class="param-type">boolean</span></td>
<td class="description last">if the event should be canceled; otherwise, false.</td>
</tr>
<tr>
<td class="name">{% highlight html %}
model{% endhighlight %}</td>
<td class="type"><span class="param-type">object</span></td>
<td class="description last">returns the barcode model</td>
</tr>
<tr>
<td class="name">{% highlight html %}
type{% endhighlight %}</td>
<td class="type"><span class="param-type">string</span></td>
<td class="description last">returns the name of the event</td>
</tr>
<tr>
<td class="name">{% highlight html %}
status{% endhighlight %}</td>
<td class="type"><span class="param-type">boolean</span></td>
<td class="description last">return the barcode state</td>
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>




Example
{:.example}



{% highlight html %}

"use strict";
function load(args) {	
	debugger;
 }
ReactDOM.render(
<div className="control">
<EJ.Barcode id="code39" text="SYNCFUSION" symbologyType="code39" load="load">
</EJ.Barcode>
</div>,
document.getElementById('barcode-code39')
);


{% endhighlight %}


