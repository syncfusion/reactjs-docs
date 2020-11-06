---
layout: post
title: Exporting-the-Digital-Gauge
description: exporting the digital gauge
platform: js
control: Digital Gauge
documentation: ug
---

# Exporting the Digital Gauge

**Digital Gauge** has an exporting feature where **Gauge** control is converted into image format and then exported to client-side. The method API **exportImage** exports the **Digital Gauge**. It has two arguments such as **file****name** and **file format**. For exporting, you can refer the following code example.

{% highlight html %}

<div id="DigitalGauge1"></div>
<button id="btnSubmit">Export</button>
<div id=" fileName ">FileName </div>
<div id=" fileFormat ">FileFormat </div>
<select id="fileFormat">
    <option value="JPEG">JPEG</option>
    <option value="PNG">PNG</option>
</select>

{% endhighlight %}

{% highlight javascript %}

"use strict"
ReactDOM.render(
    <EJ.DigitalGauge id="default" value="Syncfusion">
    </EJ.DigitalGauge>,
		  document.getElementById('DigitalGauge1')
);
ReactDOM.render(
    <EJ.Button id="btnExportImage" width={100} click={buttonclickevent}>
    </EJ.Button>
)
function buttonclickevent() {
     var FileName = $("#txtFileName").val();
     var FileFormat = $("#ddlFileType").val();
     var flag = $("#default").ejDigitalGauge("exportImage", FileName, FileFormat);
     if(!flag)
        alert("Sorry for the inconvenience. Export is currently not supported in Internet Explorer 9 and below version");
}

{% endhighlight %}

Execute the above code examples to render the **Digital****Gauge** as follows.

![](/js/DigitalGauge/Exporting-the-Digital-Gauge_images/Exporting-the-Digital-Gauge_img1.png)

