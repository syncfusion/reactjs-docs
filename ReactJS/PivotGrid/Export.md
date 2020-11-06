---
title: Export
description: export
platform: React JS
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Exporting

The PivotGrid control can be exported to the following file formats.

* Excel
* Word
* PDF
* CSV

The PivotGrid control can be exported by invoking **"exportPivotGrid"** method, with an appropriate export option as parameter.

## JSON Export

{% highlight html %}

<div id="PivotGrid1" style="height: 350px; width: 100%; overflow: auto"></div>
<button id="btnExport">Export</button>
<script type="text/babel">
    //...
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" dataSource= {pivotdataSource}></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>
<script type="text/javascript">
    $( "#btnExport" ).click(function() {
        var pGridObj = $('#PivotGrid').data("ejPivotGrid");
        pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/ExcelExport", "fileName");
    });
</script>                                   

{% endhighlight %}

### Excel Export

User can export the contents of PivotGrid to an Excel document for future archival, references and analysis purposes.

To achieve Excel export, service URL and file name is sent as the parameter.

{% highlight javascript %}

$( "#btnExport" ).click(function() {
    var pGridObj = $('#PivotGrid').data("ejPivotGrid");
    pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/ExcelExport", "fileName");
});

{% endhighlight %}  

### Word Export

User can export the contents of PivotGrid to a Word document for future archival, references and analysis purposes.

To achieve Word export, service URL and file name is sent as the parameter.

{% highlight javascript %}

$( "#btnExport" ).click(function() {
    var pGridObj = $('#PivotGrid').data("ejPivotGrid");
    pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/WordExport", "fileName");
});

{% endhighlight %}  

### PDF Export

User can export the contents of PivotGrid to a PDF document for future archival, references and analysis purposes.

To achieve PDF export, service URL and file name is sent as the parameter.

{% highlight javascript %}

$( "#btnExport" ).click(function() {
    var pGridObj = $('#PivotGrid').data("ejPivotGrid");
    pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/PDFExport", "fileName");
});

{% endhighlight %}  

### CSV Export

User can export the contents of PivotGrid to a CSV document for future archival, references and analysis purposes.

To achieve CSV export, service URL and file name is sent as the parameter.

{% highlight javascript %}

$( "#btnExport" ).click(function() {
    var pGridObj = $('#PivotGrid').data("ejPivotGrid");
    pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/CSVExport", "fileName");
});

{% endhighlight %}  

### Customize the export document name

For customizing file name, we need to send file name as parameter to the **exportPivotGrid**  method along with service URL.

{% highlight javascript %}

$( "#btnExport" ).click(function() {
    var pGridObj = $('#PivotGrid').data("ejPivotGrid");
    pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/ExcelExport", "fileName");
});
    
{% endhighlight %}

## Exporting Customization

You can add title and description to the exporting document by using title and description property obtained in the "beforeExport" event.

{% highlight html %}

<div id="PivotGrid1" style="height: 350px; width: 100%; overflow: auto"></div>
<button id="btnExport">Export</button>
<script type="text/babel">
    //...
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" dataSource= {pivotdataSource} beforeExport="Exporting"></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>
<script type="text/javascript">
    $( "#btnExport" ).click(function() {
        var pGridObj = $('#PivotGrid').data("ejPivotGrid");
        pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/ExcelExport", "fileName");
    });
    function Exporting(args){
        args.title = "PivotGrid";
        args.description = "Displays both OLAP and Relational datasource in tabular format";
    }
</script>                                          

{% endhighlight %}

The below screenshot shows the PivotGrid control exported to Excel document.

![](Export_images/ExportPivotExcel.png)

The below screenshot shows the PivotGrid control exported to Word document.

![](Export_images/ExportPivotWord.png)

The below screenshot shows the PivotGrid control exported to PDF document.

![](Export_images/ExportPivotPDF.png)

The below screenshot shows the PivotGrid control exported to CSV document.

![](Export_images/ExportPivotCSV.png)
