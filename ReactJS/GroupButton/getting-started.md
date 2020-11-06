---
layout: post
title: create a GroupButton in ReactJS framework 
description: create a GroupButton in ReactJS framework 
platform: ReactJS
control: GroupButton
documentation: ug
---

# Getting Started

You can create a ReactJS GroupButton component in your application with the help of the following steps. The basic rendering of ReactJS GroupButton is achieved with default functionality.

## Create a GroupButton Using JSX template

You can create a ReactJS application and add necessary scripts and styles with the help of the given link [https://help.syncfusion.com/reactjs/overview](https://help.syncfusion.com/reactjs/overview)

Define an HTML element for adding GroupButton in the application and refer the JSX file.

{% highlight html %}

    <body>   
    <div id="groupbutton"></div>                                                                 
    <script type="text/babel" src="GroupButton.jsx"> <script/>                 
    </body>                                                                               

{% endhighlight %}

Create a JSX file for rendering GroupButton components using '<EJ.GroupButton>' tag. Add required properties in the with this tag element.

{% highlight html %}

    "use strict";

    var data=[



            { text: 'Day', contentType: 'textonly' },



            { text: 'Week', contentType: 'textonly' },



            { text: 'Work Week', contentType: 'textonly' },



            { text: 'Month', contentType: 'textonly', selected: 'selected' },



            { text: 'Agenda', contentType: 'textonly' }

    ];

{% endhighlight %}


{% highlight html %}

    ReactDOM.render(
            
                <EJ.GroupButton id="dtp" dataSource={data} >
    </EJ.GroupButton>
        ,
    document.getElementById('groupbutton')
    );

{% endhighlight %}


This will render the GroupButton in the above HTML page in the div element with id sample.



![](buttonusingjsxtemplate_images\createagroupbuttonusingjsxtemplate_img1.png)


## Create a GroupButton without using JSX template

GroupButton can be created without using JSX template. It can be done by using script section in HTML file.

The following script code will render the GroupButton component.

{% highlight html %}

    <div id="groupbutton">
        <script>

            var data = [

            { text: 'Day', contentType: 'textonly' },

            { text: 'Week', contentType: 'textonly' },

            { text: 'Work Week', contentType: 'textonly' },

            { text: 'Month', contentType: 'textonly', selected: 'selected' },

            { text: 'Agenda', contentType: 'textonly' }
            ];


            ReactDOM.render(


                React.createElement(EJ.GroupButton, { id: 'groupbutton', dataSource: data, showRoundedCorner: true }
                ),
                document.getElementById('groupbutton')
                );

        </script>
    </div>
    
{% endhighlight %}

## Configure Properties

you can make use of all available properties in GroupButton in ReactJS framework. Please refer below code to configure the all properties in this framework

{% highlight javascript %}

    "use strict";

    var data=[



            { text: 'Day', contentType: 'textonly' },



            { text: 'Week', contentType: 'textonly' },



            { text: 'Work Week', contentType: 'textonly' },



            { text: 'Month', contentType: 'textonly', selected: 'selected' },



            { text: 'Agenda', contentType: 'textonly' }

    ];



    ReactDOM.render(



                <EJ.GroupButton id="dtp" dataSource={data} showRoundedCorner={true}>

    </EJ.GroupButton>

        ,

    document.getElementById('groupbutton')

    );

{% endhighlight %}

Run the above code to render the following output.

![](configureproperties_images\configureproperties_img1.png)
