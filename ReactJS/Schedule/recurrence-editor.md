---
title: Getting started with RecurrenceEditor component and basic render.	 	
description: Rendering a basic Recurrence editor with properties and generate the recurrence rule for Recurrence editor.
platform: ReactJS
control: Recurrence Editor
documentation: ug
keywords: recurrence editor, recurrence widget, ejRecurrenceEditor, js recurrence editor
---
# Recurrence Editor

The **Recurrence Editor** includes the entire recurrence related information in a separate portable manner which can be either utilized as a separate widget or else can be embed within the appointment window of Scheduler to enable recurrence options within it. The recurrence rule can be easily generated based on the frequency selected. The customizations like changing the labels of the recurrence editor is also possible to achieve through its properties. The frequencies available are Never, Daily, Weekly, Monthly, Yearly and Every weekday.

## Getting Started

To render the Recurrence Editor control as a separate widget, the following list of external dependencies are needed,

* [jQuery](http://jquery.com) - 1.7.1 and later versions
* [jsRender](https://github.com/borismoore/jsrender) - to render the templates
* [jQuery.easing](http://gsgd.co.uk/sandbox/jquery/easing) - to support animation effects in the components

The other required internal dependencies are tabulated below,

<table>
    <tr>
        <th>File<br/><br/></th>
        <th>Description/Usage<br/><br/></th>
    </tr>
    <tr>
        <td>ej.core.min.js<br/><br/></td>
        <td>Must be referred always first before using all the JS controls.<br/><br/></td>
    </tr>
    <tr>
        <td>ej.globalize.min.js<br/><br/></td>
        <td>Must be referred to localize any of the JS control's text and content.<br/><br/></td>
    </tr>
    <tr>
        <td>ej.recurrenceeditor.min.js<br/><br/></td>
        <td>Schedule core file<br/><br/></td>
    </tr>
    <tr>
        <td>ej.scroller.min.js<br/><br/>ej.datepicker.min.js<br/><br/>ej.checkbox.min.js<br/><br/>ej.editor.min.js<br/><br/>ej.dropdownlist.min.js<br/><br/>ej.radiobutton.min.js<br/><br/></td>
        <td>These files are referred for proper working of the sub-controls used within RecurrenceEditor.<br/><br/></td>
    </tr>
</table>

N> Recurrence Editor uses one or more sub-controls, therefore refer the `ej.web.all.min.js` (which encapsulates all the `ej` controls and frameworks in a single file) in the application instead of referring all the above specified internal dependencies.

To get the real appearance of the Recurrence Editor, the dependent CSS file `ej.web.all.min.css` (which includes styles of all the widgets) should also needs to be referred.

## Control Initialization

Create a div element within the body section of the HTML document, where the Recurrence Editor needs to be rendered.

{% highlight html %}

<body>
	<div id="RecurrenceEditor"></div>
</body>

{% endhighlight %}

Initialize the Recurrence Editor control, by adding the following script code to the body section of the HTML document.

{% highlight html %}

<body>
    <!-- div for RecurrenceEditor creation -->
    <div id="RecurrenceEditor"></div>
</body>

{% endhighlight %}

{% highlight html %}

var Recurrence = React.createClass({
    render: function () {
        return (
            <EJ.RecurrenceEditor id="editor"></EJ.RecurrenceEditor>
       );
    }
});

ReactDOM.render(<Recurrence />, document.getElementById('RecurrenceEditor'));

{% endhighlight %}

## Generating Recurrence Rule

The Recurrence Editor can be used to generate the recurrence rule as a string, based on the repeat options selected.

The following code example depicts the way to generate the recurrence rule.

{% highlight html %}

var Recurrence = React.createClass({
    onCreate: function(args) {
        this.element.find("#recurrencetype_wrapper").css("width", "33%");
        $("#RecurrenceEditor").after($("#donerecur1"));
    },
    render: function () {
        return (
            <EJ.RecurrenceEditor id="editor" selectedRecurrenceType={0} create={this.onCreate}></EJ.RecurrenceEditor>
       );
    }
});

var Button = React.createClass({
    closeRecurrence: function(args) {
        var obj = $("#RecurrenceEditor").data("ejRecurrenceEditor");
        alert(obj.getRecurrenceRule());
    },
    render: function() {
        return (
            <EJ.Button id="donerecur1" width="155px" text="Recurrence String" height="35px" showRoundedCorner={true} click={this.closeRecurrence}></EJ.Button>
        );
    }
});

ReactDOM.render(<Recurrence />, document.getElementById('RecurrenceEditor'));

{% endhighlight %}
