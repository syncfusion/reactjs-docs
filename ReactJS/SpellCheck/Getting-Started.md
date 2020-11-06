---
title: Getting started with SpellCheck component	
description: Rendering a basic SpellCheck
platform: ReactJS
control: spellcheck
documentation: ug
keywords: ejSpellCheck, spellcheck, spellcheck widget, js spellcheck, getting started, initialization, service reference
---
# Getting Started 

You can create a React application and add necessary scripts and styles with the help of the given [React Getting Started Documentation.](https://help.syncfusion.com/reactjs/overview)

## Control Initialization

Define an HTML element for adding SpellCheck in the application and refer the JS file.

{% highlight html %}

<div id="spellcheck-default"></div>
<script src="app/spellcheck/default.js"></script>

{% endhighlight %}

Create a JSX file for rendering SpellCheck component using <EJ.SpellCheck> syntax. Add required properties to it in <EJ. SpellCheck> tag element.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={false}>
                Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
                The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
            </EJ.SpellCheck>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));


{% endhighlight %}

N> The above jsx template needs to be converted from .jsx to .js extension by using gulp nuget package (refer [here](https://help.syncfusion.com/reactjs/overview#converting-jsx-to-javascript-with-react)) and then it must be referred in the html page.

## Spell Checking

To spell check the content of the target element, you need to add one button and calling any one of the SpellCheck method `showInDialog` or `validate` by clicking the button to highlight the error words.

The following code example depicts that checking the spelling of the target element through the "validate" method.

{% highlight html %}

"use strict";

var SpellMenu = React.createClass({    
    checkInTarget: function (e) {
        var obj = $("#SpellCheck2").data("ejSpellCheck");
        obj.validate();
    },
    render: function () {
        return (
        <div id="spell_menu">
            <EJ.SpellCheck id="SpellCheck2" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary">
                It is a concept vehicle with Liuid Silver body colour, 20-inch wheels, fabric foding roof, electrically-controlled hood, 4-cylinder 2.0 TDI engine rated 204 PS (150 kW; 201 hp)
                and 400  (295.02 lbf ft), diesel particulate filter and Bluetec emission control system, quattro permanent four-wheel drve system,
                Audi S tronic dual-clutch gearbox, McPherson-strut front axle and a four-link rear axle, Audi drive select system with 3 modes (dynamic, sport, efficiency),
                MMI control panel with touch pad and dual-view technology, sound system with the proinent extending tweeters.
            </EJ.SpellCheck>
            <EJ.Button id="btnCheck" type="button" height={30} text="Spell Check" click={this.checkInTarget}>
            </EJ.Button>
        </div>
        );
    }
});

ReactDOM.render(<SpellMenu />, document.getElementById('contextmenu'));

{% endhighlight %}