---
layout: post
title: Service reference for ejChart widget
description: What is the service used for exporting ejChart
platform: js
keywords: ejChart, exporting service, services, Essential JavaScript Chart, Excel exporting, PDF exporting, Export to word, Export to SVG
metaname:
metacontent:
control: Chart
documentation: ug
api : /api/js/ejchart
---

## Exporting Service

### Description

Export Chart as PNG, JPG, SVG, PDF document, Excel document or Word document.

### URL

[http://js.syncfusion.com/ExportingServices/api/JSChartExport/ExportChart](http://js.syncfusion.com/ExportingServices/api/JSChartExport/ExportChart)

### Parameters
<table>
<tr>
    <th>Name</th>
    <th>Value</th>
</tr>
<tr>
    <td>exportMultipleChart</td>
	<td>false</td>
</tr>
</table>

### Request

{% highlight js %}
 
var chart = $(".e-datavisualization-chart").ejChart("instance");
var exportSettings = chart.model.exportSettings;
exportSettings.fileName = "Chart";
exportSettings.angle = "90";
exportSettings.type = "png";
exportSettings.mode = 'server';
exportSettings.action = 'http://js.syncfusion.com/ExportingServices/api/JSChartExport/ExportChart';
data = chart.export();

{% endhighlight %}

### Response (PNG, JPG, SVG, PDF, Word or Excel):

#### Status Code: 200

#### Content-Type: application/octet-stream

Browser will prompt a dialog box to save the file (image or document).

### Online Demo

Our [Exporting Demo](http://js.syncfusion.com/demos/web/#!/azure/chart/export) sample uses this service to export Chart as images (PNG, JPG, SVG), PDF document, Word document and Excel worksheet.



