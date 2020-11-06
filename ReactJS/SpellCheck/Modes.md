---
title: SpellCheck - Operations
description: SpellCheck Operations
platform: ReactJS
control: spellcheck
documentation: ug
keywords: operations, spellcheck modes, dialog mode, context menu mode,  custom menu, handling menu actions, handling dialog actions
---
# SpellCheck Operations

Essential SpellCheck provides two ways to perform the spellcheck operation(error correction). They are,

* Dialog Mode 
* Context Menu Mode  

## Dialog Mode

### Description

SpellCheck provides the dialog mode option to perform the following spellcheck operations.

* Ignore Once
* Ignore All
* Change
* Change All
* Add to Dictionary

### Open Dialog Mode

The following code snippet shows how to open the dialog to spell check the content.

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
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={false}>
                Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
                The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
            </EJ.SpellCheck>,
            <EJ.Button id="btnCheck" type="button" height={30} text="Spell Check" click={this.checkErrors}>
            </EJ.Button>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

### Handling Dialog Actions

To define the specific actions before the dialog window open, the client-side event `dialogBeforeOpen` can be used as depicted in the below code example.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    checkErrors: function (e) {
        var spellObj = $("#SpellCheck1").data("ejSpellCheck");
        spellObj.showInDialog();
    },
    onDialogBeforeOpen:function(e){
        if (e.requestType == "dialogBeforeOpen") {
            alert("dialog before open event triggered");
        }
    },
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={false} dialogBeforeOpen={this.onDialogBeforeOpen} >
                Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
                The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
            </EJ.SpellCheck>,
            <EJ.Button id="btnCheck" type="button" height={30} text="Spell Check" click={this.checkErrors}>
            </EJ.Button>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

The client-side event `dialogOpen` can be used to define the specific actions after the dialog window open as shown in the following code example.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    checkErrors: function (e) {
        var spellObj = $("#SpellCheck1").data("ejSpellCheck");
        spellObj.showInDialog();
    },
    onDialogOpen:function(e){
        if (e.requestType == "dialogOpen") {
            alert(e.targetText);
        }
    },
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={false} dialogOpen={this.onDialogOpen} >
                Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
                The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
            </EJ.SpellCheck>,
            <EJ.Button id="btnCheck" type="button" height={30} text="Spell Check" click={this.checkErrors}>
            </EJ.Button>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

The following code example used to define some actions after the dialog closing by using the client-side event `dialogClose`.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    checkErrors: function (e) {
        var spellObj = $("#SpellCheck1").data("ejSpellCheck");
        spellObj.showInDialog();
    },
    onDialogClose:function(e){
        if (e.requestType == "dialogClose") {
            alert(e.updatedText);
        }
    },
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={false} dialogClose={this.onDialogClose} >
                Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
                The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
            </EJ.SpellCheck>,
            <EJ.Button id="btnCheck" type="button" height={30} text="Spell Check" click={this.checkErrors}>
            </EJ.Button>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

It is possible to predict the error word details before starting the spellcheck operations through dialog mode by using the client side event `start`. The below code example describes the above behavior.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    checkErrors: function (e) {
        var spellObj = $("#SpellCheck1").data("ejSpellCheck");
        spellObj.showInDialog();
    },
    onSpellCheckStart:function(e){
        if (e.requestType == "spellCheckDialog") {
           alert(JSON.stringify(args.errorWords));    
        }
    },
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={false} start={this.onSpellCheckStart} >
                Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
                The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
            </EJ.SpellCheck>,
            <EJ.Button id="btnCheck" type="button" height={30} text="Spell Check" click={this.checkErrors}>
            </EJ.Button>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

You can get the corrected text content details before updating it into target element with the help of the client side event `complete` as mentioned in the below code example.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    checkErrors: function (e) {
        var spellObj = $("#SpellCheck1").data("ejSpellCheck");
        spellObj.showInDialog();
    },
    onSpellCheckComplete:function(e){
        if (args.requestType == "changeErrorWord") {
            alert(args.targetText);
        }
    },
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={false} start={this.onSpellCheckComplete} >
                Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
                The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
            </EJ.SpellCheck>,
            <EJ.Button id="btnCheck" type="button" height={30} text="Spell Check" click={this.checkErrors}>
            </EJ.Button>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

## Context Menu Mode

SpellCheck provides default context menu options to perform the spellcheck operations. It also allows to define additional custom context menu options.

The options that are available under `contextMenuSettings` are as follows,

* `**enable**` - Enables/disables the context menu option in SpellCheck.
* `**menuItems**` - Contains the options to perform spellcheck operations.

### Default Menu Options

The menu items contains the following options to perform the spellcheck operation.

* Ignore All
* Add to Dictionary 

The following code snippet shows how to enable the context menu settings in SpellCheck and to make use of it with default available options.

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
            <EJ.SpellCheck id="SpellCheck2" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={true} contextMenuSettings-menuItems={[
                        { id: "IgnoreAll", text: "Ignore All" },
                        { id: "AddToDictionary", text: "Add To Dictionary" }]}>
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

N> For default menu items, the id must be defined the same as mentioned in the above code example – as we have processed the menus based on this id within our source.

### Custom Menu Options

Apart from the default available options, it is also possible to add custom menu options to the context-menu list.

The following code example depicts how **to add the custom menu items** into the context menu settings.

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
            <EJ.SpellCheck id="SpellCheck2" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={true} contextMenuSettings-menuItems={[
                        { id: "Ignore", text: "IgnoreOnce" },
                        { id: "IgnoreAll", text: "Ignore All" },
                        { id: "AddToDictionary", text: "Add To Dictionary" }]}>
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

N> The **id** given for the custom menu items **must be unique**.

### Handling Menu Actions

The client-side event `contextClick` can be used to define specific actions when a click made on the custom menu items. The following code example describes the above behavior.

{% highlight html %}

"use strict";

var SpellMenu = React.createClass({
    checkInTarget: function (e) {
        var obj = $("#SpellCheck2").data("ejSpellCheck");
        obj.validate();
    },
    onCustomMenuClick: function (e) {debugger;
        if (e.selectedOption == "Ignore") {
            alert("Custom menu clicked");
        }
    },
    render: function () {
        return (
        <div id="spell_menu">
            <EJ.SpellCheck id="SpellCheck2" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={true} contextMenuSettings-menuItems={[
                        { id: "Ignore", text: "IgnoreOnce" },
                        { id: "IgnoreAll", text: "Ignore All" },
                        { id: "AddToDictionary", text: "Add To Dictionary" }
                    ]} contextClick={this.onCustomMenuClick}>
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


It is possible to predict the target (error word) on which the right click is made with the use of the event `contextOpen`. The below code example shows how to block the display of context menu, when right clicked on the word by setting **args.cancel** as **true**.

{% highlight html %}

"use strict";

var SpellMenu = React.createClass({
    checkInTarget: function (e) {
        var obj = $("#SpellCheck2").data("ejSpellCheck");
        obj.validate();
    },
    onMenuOpen: function (e) {
        if (e.selectedErrorWord == "Bluetec") {
            e.cancel = true;
        }
    },
    render: function () {
        return (
        <div id="spell_menu">
            <EJ.SpellCheck id="SpellCheck2" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={true} contextOpen={this.onMenuOpen}>
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

You can get the current spell check operation arguments details with the client-side event `validating'. The following code example describes the way to block the ignoreAll operation for the particular word.

{% highlight html %}

"use strict";

var SpellMenu = React.createClass({
    checkInTarget: function (e) {
        var obj = $("#SpellCheck2").data("ejSpellCheck");
        obj.validate();
    },
    onSpellChecking: function (e) {
        if (e.requestType == "ignoreAll" && e.ignoreWord == "Bluetec") {
            e.cancel = true;
        }
    },
    render: function () {
        return (
        <div id="spell_menu">
            <EJ.SpellCheck id="SpellCheck2" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={true} validating={this.onSpellChecking}>
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