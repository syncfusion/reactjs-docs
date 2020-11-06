---
title: PivotGrid-Elements
description: pivotGrid elements
platform: React JS
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# PivotGrid: Elements

## Hyperlink
The PivotGrid control supports hyperlink option to link data for each individual cell. Hyperlink can be enabled separately for row header, column header, value and summary cells. Following are the respective properties:

* [`enableColumnHeaderHyperlink`](/api/js/ejpivotgrid#members:hyperlinksettings-enablerowheaderhyperlink) - Enables hyperlink for column headers.
* [`enableRowHeaderHyperlink`](/api/js/ejpivotgrid#members:hyperlinksettings-enablerowheaderhyperlink) - Enables hyperlink for row headers.
* [`enableSummaryCellHyperlink`](/api/js/ejpivotgrid#members:hyperlinksettings-enablesummarycellhyperlink) - Enables hyperlink for summary cell.
* [`enableValueCellHyperlink`](/api/js/ejpivotgrid#members:hyperlinksettings-enablevaluecellhyperlink) - Enables hyperlink for value cell.

Also hyperlink option provides separate events for row header, column header, value and summary cells as mentioned below.
 
* [`columnHeaderHyperlinkClick`](/api/js/ejpivotgrid#events:columnheaderhyperlinkclick) - Returns column header information through event on hyperlink click.
* [`rowHeaderHyperlinkClick`](/api/js/ejpivotgrid#events:rowheaderhyperlinkclick) - Returns row header information through event on hyperlink click.
* [`summaryCellHyperlinkClick`](/api/js/ejpivotgrid#events:summarycellhyperlinkclick) - Returns summary cell information through event on hyperlink click.
* [`valueCellHyperlinkClick`](/api/js/ejpivotgrid#events:valuecellhyperlinkclick) - Returns value cell information through event on hyperlink click.

{% highlight html %}

<script type="text/babel">
    //...
    var hyperlinkSettings= {
    enableValueCellHyperlink: true,
    enableRowHeaderHyperlink: true,
    enableColumnHeaderHyperlink: true,
    enableSummaryCellHyperlink: true
    }
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" hyperlinkSettings= {hyperlinkSettings} valueCellHyperlinkClick= "CellClickEvent" rowHeaderHyperlinkClick= "CellClickEvent" columnHeaderHyperlinkClick= "CellClickEvent" summaryCellHyperlinkClick= "CellClickEvent"></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>
<script type="text/javascript">
    function CellClickEvent(evt) {
        alert("Cell click event is fired.");
    }
</script>

{% endhighlight %}

![](PivotGrid-Elements_images/hyperlink.png)

## Selection
You can select a particular range of value cells from PivotGrid and manipulate/display them. Cell selection is applicable only for value cells and you can enable this functionality by setting [`enableCellSelection`](/api/js/ejpivotgrid#members:enablecellselection) property to true.

The [`cellSelection`](/api/js/ejpivotgrid#events:cellselection) event would be triggered as soon as the selection process is over, that is, when the mouse left click is released. The event argument contains a collection of JSON records and header values, which contains information about the selected cells.

{% highlight html %}

<script type="text/babel">
    //...
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" enableCellSelection= {true} cellSelection= "valueCellClick"></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>
<script type="text/javascript">
    valueCellClick = function(evt) {
        //This event lets you to perform required operation with the selected range of cells.
        cellvalue = evt.JSONRecords;
        rowheaders = evt.rowHeader;
        colheaders = evt.columnHeader;
    }
</script>

{% endhighlight %}

![](PivotGrid-Elements_images/cellselection.png)

## Cell Context
Cell context allows user to perform any custom operation on cell right-click. For example, you can create and display context menu on cell right-click.

Cell context is enabled by setting the [`enableCellContext`](/api/js/ejpivotgrid#members:enablecellcontext) property to true. The [`cellContext`](/api/js/ejpivotgrid#events:cellcontext) event would be raised as soon as right-click is done providing cell information through event argument.

{% highlight html %}

<script type="text/babel">
    //...
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" enableCellContext= {true} cellContext= "cell_RightClick"></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>
<script type="text/javascript">
    cell_RightClick = function(evt) {
        //You can write your code here
    }
</script>

{% endhighlight %}

## Conditional Formatting
Conditional formatting in PivotGrid allows user to highlight particular cells with certain color, font-style, font-family etc. based on the condition they have met.  Also the condition can be applied for certain Measure alone.
  
Conditional formatting is enabled by setting [`enableConditionalFormatting`](/api/js/ejpivotgrid#members:enableConditionalFormatting) property to true and the formatting dialog is launched when **"createConditionalDialog"** method is invoked.

{% highlight html %}

<div id="PivotGrid1" style="height: 350px; width: 100%; overflow: auto"></div>
<button id="Button1">Apply formatting</button>
<script type="text/babel">
    //...
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" enableConditionalFormatting= {true} ></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>
<script type="text/javascript">
    $( "#Button1" ).click(function() {
        var pGridObj = $('#PivotGrid').data("ejPivotGrid");
        if (pGridObj.model.enableConditionalFormatting) {
                pGridObj.createConditionalDialog();
            }
    });
</script>   

{% endhighlight %}

![](PivotGrid-Elements_images/FormatDialog.png)

![](PivotGrid-Elements_images/FormattedGrid.png)

### Export

We can export the PivotGrid with highlighted particular cells along with its formatting styles. 

LIMITATIONS FOR WORD:

The following border styles are not supported

* Solid
* Groove
* Ridge

LIMITATIONS FOR PDF:

Border styles are not applicable.

LIMITATIONS FOR EXCEL:

The following border styles are alone supported

* Dashed
* Dotted
* Double

Also border size is not supported.

![](PivotGrid-Elements_images/conditional_export.png)