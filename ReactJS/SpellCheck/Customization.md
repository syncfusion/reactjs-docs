---
title: SpellCheck - Customization | Syncfusion
description: SpellCheck Customization
platform: ReactJS
control: spellcheck
documentation: ug
keywords: customization, spellcheck customization, misspell word appearance, restrict suggestion count
---
# SpellCheck Customization

The SpellCheck provides option to customize for the following scenarios.

* Misspell Word Appearance
* Restrict Suggestion Count
    
## Misspell Word Appearance

The SpellCheck control provide the support(`misspellWordCss]`) to display the error word in user defined style. By default displaying the error words with the red underline. 

The following code example depicts the way to customize the error word highlight (displaying error word with red color font and lightblue background).

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    checkInDialog: function (e) {
        var obj = $("#SpellCheck1").data("ejSpellCheck");
        obj.showInDialog();
    },
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={false} misspellWordCss="highlight">
                Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
                The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
            </EJ.SpellCheck>
            <EJ.Button id="btnCheck" type="button" height={30} text="Spell Check" click={this.checkInDialog}>
            </EJ.Button>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

Html file:

{% highlight html %}

<style>
    .highlight {
        background-color: lightblue;
        color: red;
    }
</style>

{% endhighlight %}

## Restrict Suggestion Count

The SpellCheck control provides option (`maxSuggestionCount`) to restrict the count that the number of items displayed in the suggestion list.

The following code example describes the way to control the suggestion count.

{% highlight html %}
    "use strict";
var DefaultDialog = React.createClass({
    checkInDialog: function (e) {
        var obj = $("#SpellCheck1").data("ejSpellCheck");
        obj.showInDialog();
    },
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={false} maxSuggestionCount={3}>
                Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
                The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
            </EJ.SpellCheck>
            <EJ.Button id="btnCheck" type="button" height={30} text="Spell Check" click={this.checkInDialog}>
            </EJ.Button>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}