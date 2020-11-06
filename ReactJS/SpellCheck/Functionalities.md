---
title: SpellCheck - Functionalities
description: SpellCheck Functionalities
platform: ReactJS
control: spellcheck
documentation: ug
keywords: spellcheck functionalities, check spelling, ignore words, change words, change, ignore, ignore settings,
---
# Functionalities

## Check Spelling

The main functionality of the SpellCheck control is checking the spelling of a word and returns the suggestions for an error word.

For example, if you pass the sentence that contains misspell words as input, you can know the error words in this sentence and its suggestions (apt words to replace).

## Ignore Words

The SpellCheck control provides the support to ignore the words from an error word consideration and also to ignore an error words whenever needed. Please refer the following options to ignore the words.

### Ignore

The `ignore` option is used to ignore a specific word once from the given input string. 

The following code example describes the above method implementation.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    componentDidMount:function(){
        var targetSentence = 'The <span class="errorspan e-errorword">textarea</span> sample uses a dialog to display the spell errors.';
        var schObj = $("#SpellCheck1").data("ejSpellCheck");
        schObj.ignore("textarea",targetSentence, null);
    },
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={false}>
            </EJ.SpellCheck>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %} 

### Ignore All

The `ignore all` option is used to ignore all the error word occurrences from the given input string.

The following code example describes the way of using ignore all method.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    componentDidMount:function(){
        var targetSentence = 'This <span class="errorspan e-errorword">textarea</span> sample uses a dialog to display all the <span class="errorspan e-errorword">textarea</span> spell errors.';
        var schObj = $("#SpellCheck1").data("ejSpellCheck");
        schObj.ignoreAll("textarea",targetSentence, null);
    },
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={false}>
            </EJ.SpellCheck>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

### Word Collection to Ignore

The `ignoreWords` option is used to ignore the collection of words from an error word checking. You can pass the technical terms, brand names which is not present in the dictionary file to this property "ignoreWords" as shown in the following code example and then while checking the spelling these passed words are considered as a correct word.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={true} ignoreWords={["fouders","graually"]}>
                Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
                The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
            </EJ.SpellCheck>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

## Ignore Settings

The `ignore settings` helps to ignore the uppercase, mixed case words, alphanumeric words, file path and email addresses from the error word checking. Ignore settings contains the following options to ignore the words based on their category.

* `ignoreAlphaNumericWords` - ignoring the alpha numeric words from an error word consideration.
* `ignoreUpperCase` - ignoring the upper case words from an error word consideration.
* `ignoreMixedCaseWords` - ignoring the mixed case words from an error word consideration.
* `ignoreFileNames` - ignoring the file address path from an error word consideration.
* `ignoreUrl` - ignoring the url links from an error word consideration.
* `ignoreEmailAddress` - ignoring the email address from an error word consideration.

The following code example uses to enable the checking of all the words formed with alphanumeric, uppercase, mixed case words and file paths and email addresses.  

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={true} ignoreSettings-ignoreAlphaNumericWords={false} ignoreSettings-ignoreMixedCaseWords={false} ignoreSettings-ignoreUpperCase={false} ignoreSettings-ignoreUrl={false} ignoreSettings-ignoreEmailAddress={false} ignoreSettings-ignoreFileNames={false}>
                Amazon.com, Inc., often refered to as simply Amazon, is an American electronic commerce and cloud computing company with headquarters in Seattle, Washington. It is the largest web-based retailer in the United States. Amazon.com started as bookstore on the web, later diversifying to sell DVDs, Blu-rays, CDs, video downloads/streaming, MP3 downloads/streaming, audiobook downloads/streaming, software, video games, electronics, apparel, furniture, food, toys and jewelry. The company also produces consumer electronics notably, Amazon Kindle e-book readers, Fire tablets, Fire TV and Fire Phone and is the world's largest provider of cloud infrastructure services (IaaS). Amazon also sells certain low-end products like USB cables under its in-house brand AmazonBasics.
                Amazon has separate retail websites for United States, United Kingdom and Ireland, France, Canada, Germany, Italy, Spain, Netherlands, Australia, Brazil, Japan, China, India and Mexico. Amazon also offers international shipping to cetain other countries for some of its products.
            </EJ.SpellCheck>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

## Change Words

The SpellCheck control provides the support to change an error words from its possible suggestions. Please refer the following options to change an error word.

### Change

The `change` option is used to replace an error word occurrences once from the given input string with the correct word.

The following code example describes the behavior of change method.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    componentDidMount:function(){
        var targetSentence = 'The <span class="errorspan e-errorword">textarea</span> sample uses a dialog to display the spell errors.';
        var schObj = $("#SpellCheck1").data("ejSpellCheck");
        schObj.change("textarea", targetSentence, null);
    },
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary">
            </EJ.SpellCheck>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

### Change All

The `change all` option is used to replace all the occurrences of an error word with the correct word(selected from the suggestions list) from the given inputs string.

The following code example uses to change all the error word occurrences.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    componentDidMount:function(){
        var targetSentence = 'This <span class="errorspan e-errorword">textarea</span> sample uses a dialog to display all the <span class="errorspan e-errorword">textarea</span> spell errors.';
        var schObj = $("#SpellCheck1").data("ejSpellCheck");
        schObj.changeAll("textarea", targetSentence, null);
    },
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary">
            </EJ.SpellCheck>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

## Custom Words

The SpellCheck control provides the support to add the custom words into the custom dictionary file.

The `addToDictionary` option is used to add the custom words into the custom dictionary file.

The following code example uses to add the custom word into the custom dictionary file.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    componentDidMount:function(){
        var schObj = $("#SpellCheck1").data("ejSpellCheck");
        schObj.addToDictionary("textarea");
    },
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary">
            </EJ.SpellCheck>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

You can also add the custom words into the custom dictionary file through the dialog mode or context menu mode add to dictionary option.

* Dialog Mode - Add To Dictionary button is available in the dialog window, while highlighting the error word in the given input string and clicking this button then the word will be adding into the custom dictionary file.
* Context Menu Mode - Add To Dictionary option is available while right click on the error word and selecting this option, the word will be adding into the custom dictionary file.

## Checking content on typing

SpellCheck control provides support for checking the content, on pressing the `Enter` and `Space` key. The cursor position will also be properly retained, while processing the SpellCheck operations. If you enable “enableValidateOnType” property, the spellcheck operation will be carried out on typing.

The following code example describes the above behavior.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" contextMenuSettings-enable={true} enableValidateOnType={true}>
            </EJ.SpellCheck>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

The following screenshot displays the output for the above code

![](ValidateOnType_images/validateontype.png)

You can also validate the content within the IFrame element or IFrame element target text, by passing the IFrame element id or class name value to the `controlsToValidate` property. 
Detailed information is given [here](https://help.syncfusion.com/js/spellcheck/multiple-target)

## Suggestion Words

The `getSuggestionWords` option is used to retrieve the possible suggestion words for an error word which is provided to correct that spelling.

The following code example describes the above behavior.

{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    componentDidMount:function(){
        var schObj = $("#SpellCheck1").data("ejSpellCheck");
        schObj.getSuggestionWords("textarea");
        setTimeout(function () {
		   alert(spellObj._suggestedWords);
		}, 800);
    },
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary">
            </EJ.SpellCheck>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

N> You can get the suggestion words after some time interval once this method is called. Since, ajax request processing takes place in the background.

## Synchronous request

On setting `enableAsync` option to false, enables the synchronous request to the server to perform SpellCheck operations.

The following code example describes the above behavior.


{% highlight html %}

"use strict";
var DefaultDialog = React.createClass({
    render: function () {
        return (
        <div id="dialog_default">
            <EJ.SpellCheck id="SpellCheck1" dictionarySettings-dictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/CheckWords" dictionarySettings-customDictionaryUrl="http://js.syncfusion.com/demos/ejservices/api/SpellCheck/AddToDictionary" enableAsync={false} ajaxDataType="json">
            </EJ.SpellCheck>
        </div>
        );
    }
});

ReactDOM.render(<DefaultDialog />, document.getElementById('spellcheck-default'));

{% endhighlight %}

N> You need to set the `ajaxDataType` value as `json` to retrieve the synchronous request result properly.