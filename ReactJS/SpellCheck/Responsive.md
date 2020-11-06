---
title: SpellCheck - Responsive
description: How to set the spellcheck, responsive to screen resolutions
platform: ReactJS
control: spellcheck
documentation: ug
keywords: Responsive, Responsive spellcheck dialog, Resize spellcheck dialog
---
# Responsive

The SpellCheck control has support for responsive behavior based on client browser’s width and height. To enable responsive, `isResponsive` property should be true.

The following code example describes the above behavior.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={false} isResponsive={true}>
                Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
                The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
            </EJ.SpellCheck>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

The dialog of spell check control is rendering based on the client browser’s width and height. Refer to the following code to render the spellcheck dialog control with responsive.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    checkErrors: function (e) {
        var spellObj = $("#SpellCheck1").data("ejSpellCheck");
        spellObj.showInDialog();
    },
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={false} isResponsive={true}>
                Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
                The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
            </EJ.SpellCheck>,
            <EJ.Button id="btnCheck" type="button" height={30} text="Spell Check" click={this.checkErrors}>
            </EJ.Button>
        </div>
        );
    }
});

</script>

{% endhighlight %}

Mobile Rendering Screenshot:

![](Responsive_Images/Responsive_Image.png)