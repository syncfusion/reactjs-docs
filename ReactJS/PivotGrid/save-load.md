---
title: Save and Load Report
description: save and load report
platform: React JS
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Save and Load Report

Allows you to save the current report of PivotGrid and render the control with the saved report later.

## Save Report to Local Storage

To save the current report of PivotGrid to local storage, we need to call the [`saveReport`](/api/js/ejpivotgrid#members:saveReport) method in PivotGrid.

{% highlight html %}

<div id="PivotGrid1"> </div>
<button id="btnSave">save</button>
<script type="text/babel">
    //...
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" saveReport= "saveToLocal"></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>
<script type="text/javascript">
    $( "#btnSave" ).click(function() {
        var pGridObj = $('#PivotGrid').data("ejPivotGrid");
        url = "",
        name = "report",
        storage = "local",
        pGridObj.saveReport(name, storage, url);
    });
    function saveToLocal(args){
        localStorage.setItem("report", JSON.stringify(args.report));
    }
</script>

{% endhighlight %}

## Load Report from Local Storage

To load the stored report of PivotGrid from local storage, we need to call the ['loadReport'](/api/js/ejpivotgrid#members:loadReport) method in PivotGrid.

{% highlight html %}

<div id="PivotGrid1"> </div>
<button id="btnLoad">load</button>
<script type="text/babel">
    //...
    $(function(){
        ReactDOM.render(
        <EJ.PivotGrid id="PivotGrid" loadReport= "loadFromLocal"></EJ.PivotGrid>,
        document.getElementById('PivotGrid1')
        );
    });
</script>
<script type="text/javascript">
    $( "#btnLoad" ).click(function() {
        var pGridObj = $('#PivotGrid').data("ejPivotGrid");
            url = "",
            name = "report",
            storage = "local",
            pGridObj.loadReport(name, storage, url);
    });
    function loadFromLocal(args){
        args.targetControl.model.dataSource = JSON.parse(localStorage.getItem("report"));
    }
</script>

{% endhighlight %}