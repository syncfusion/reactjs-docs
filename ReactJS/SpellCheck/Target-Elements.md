---
title: SpellCheck - Working with Target Elements
description: Target element's text spell checking with Syncfusion SpellCheck
platform: ReactJS
control: spellcheck
documentation: ug
keywords: multiple target, target element check
---

# Supported Target Elements

The SpellCheck control has support for spell checking for the HTML element’s texts such as div, span, textarea, input, address, article and IFrame elements.

## Multiple Target

The SpellCheck control has support for multiple target HTML element’s texts spelling and correct its error words. This can be achieved by passing the target HTML elements “id” values or “CSS Class Name” or combination of both id and class names to the property “controlsToValidate”.

The following code example describes the above behavior.

{% highlight html %}

"use strict";

var MultipleTargets = React.createClass({
    
    render: function () {
        return (
         <div id="spell_multiple">
            <div id="control1" class="control1">
                London, one of the most popular touist destinations in the world for a reason. A cultural and hisorical hub, London has an excellent public transportation system that allows visitors to see all the fantatic sights without spending a ton of money on a rental car.
                London contains four World Heritage Sites.
            </div><br />
            <span id="control2">
                Rome, one of the world's most facinating cities. The old adage that Rome was not built in a day - and that you won't see it in one or even in three - is true. For the intrepid traveler who can keep pace, here is a list of must-sees.
                But reember what the Romans say: Even a lifetime isn't enough to see Rome.
            </span><br />
            <EJ.SpellCheck id="SpellCheck3" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" controlsToValidate=".control1,#control2">
            </EJ.SpellCheck><br />
        </div>
        );
    }
});

ReactDOM.render(<MultipleTargets />, document.getElementById('multipletargets'));

{% endhighlight %}

You need to pass the target HTML element’s id value or CSS class name or combination of the id value and class name with comma separator. Passing the class name followed by (.) character and passing the id value followed by the (#) character.

The following code example describes the spell checking of HTML element’s.

{% highlight html %}

"use strict";

var MultipleTargets = React.createClass({
    // Perform the spell check through dialog mode
    correctErrors: function (e) {
        var obj = $("#SpellCheck3").data("ejSpellCheck");
        obj.showInDialog();
    },
    // Perform the spell check through context menu mode
    correctErrors: function (e) {
        var obj = $("#SpellCheck3").data("ejSpellCheck");
        obj.validate();
    },
    render: function () {
        return (
        <div id="spell_multiple">
            <div id="control1" class="control1">
                London, one of the most popular touist destinations in the world for a reason. A cultural and hisorical hub, London has an excellent public transportation system that allows visitors to see all the fantatic sights without spending a ton of money on a rental car.
                London contains four World Heritage Sites.
            </div><br />
            <span id="control2">
                Rome, one of the world's most facinating cities. The old adage that Rome was not built in a day - and that you won't see it in one or even in three - is true. For the intrepid traveler who can keep pace, here is a list of must-sees.
                But reember what the Romans say: Even a lifetime isn't enough to see Rome.
            </span><br />
            <EJ.SpellCheck id="SpellCheck3" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" controlsToValidate="#control1,#control2">
            </EJ.SpellCheck><br />
            <EJ.Button id="btnCheck" type="button" height={30} text="Spell Check" click={this.correctErrors}>
            </EJ.Button>
        </div>
        );
    }
});

ReactDOM.render(<MultipleTargets />, document.getElementById('multipletargets'));

{% endhighlight %}

The spellcheck component iterates through the target elements which specified in the “controlsToValidate” property, and process the element’s content one by one in the order of CSS elements, and id specified elements.