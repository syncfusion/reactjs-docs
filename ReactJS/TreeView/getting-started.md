---
layout: post
title: getting-startedv 
description: getting started for TreeView
platform: reactjs
control: TreeView
documentation: ug
---

# Getting Started

Using the following steps, you can create a React TreeView component. The basic rendering of React TreeView is achieved with default functionality.

## Create an TreeView

You can create a React application and add necessary scripts and styles with the help of the given [React Getting Started Documentation.](https://help.syncfusion.com/reactjs/overview)

Create a JSX file for rendering TreeView component using &lt;EJ.TreeView&gt; syntax. Add required properties to it in &lt;EJ.TreeView&gt; tag element

{% highlight js %}

ReactDOM.render(   
<EJ.TreeView>
    <ul id="treeView">
          <li id="1" class="expanded">Artwork
                                    <ul>
                                        <li id="2">
                                            Abstract
                                            <ul>
                                                <li id="3">2 Acrylic Mediums</li>
                                                <li>Creative Acrylic</li>
                                                <li>Modern Painting</li>
                                                <li>Canvas Art</li>
                                                <li>Black white</li>
                                            </ul>
                                        </li>
                                        <li>Children
                                             <ul>
                                                 <li>Preschool Crafts</li>
                                                 <li>School-age Crafts</li>
                                                 <li>Fabulous Toddler</li>
                                             </ul>
                                        </li>
                                        <li>Comic / Cartoon
                                            <ul>
                                                <li>Batman</li>
                                                <li>Adventures of Superman</li>
                                                <li>Super boy</li>
                                            </ul>
                                        </li>
                                    </ul>
                        </li>
                        <li class="expanded">Books
                                        <ul>
                                            <li>Comics
                                                <ul>
                                                    <li>The Flash</li>
                                                    <li>Human Target</li>
                                                    <li>Birds of Prey</li>
                                                </ul>
                                            </li>
                                            <li>Entertaining</li>
                                            <li>Design</li>
                                        </ul>
                        </li>
                        <li>Music
                                    <ul>
                                        <li>Classical
                                             <ul>
                                                 <li>Medieval</li>
                                                 <li>Orchestral</li>
                                             </ul>
                                        </li>
                                        <li>Mass</li>
                                        <li>Folk</li>
                                    </ul>
                        </li>
                    </ul>
</EJ.TreeView>,
document.getElementById('treeview')
);

{% endhighlight %}



Define an HTML element for adding TreeView in the application and refer the JSX file.

{% highlight html %}

<div id="treeview"></div>
<script type="text/babel" src="treeview.jsx"></script>


{% endhighlight %}



Run the above code to render the following output.

![](getting-started_images\getting-started_img1.jpg)

## Data Binding

The data for TreeView which can be populated using the `dataSource` property.

The [beforeLoad](https://help.syncfusion.com/api/js/ejtreeview#events:beforeload) event will be triggered before loading nodes into TreeView.

{% highlight js %}

"use strict";
var localData = [
                   { id: 1, name: "Discover Music", hasChild: true, expanded: true },
                   { id: 2, pid: 1, name: "Hot Singles" },
                   { id: 3, pid: 1, name: "Rising Artists" },
                   { id: 4, pid: 1, name: "Live Music" },
                   { id: 6, pid: 1, name: "Best of 2013 So Far" },
                   { id: 7, name: "Sales and Events", hasChild: true, expanded: true },
                   { id: 8, pid: 7, name: "100 Albums - $5 Each" },
                   { id: 9, pid: 7, name: "Hip-Hop and R&B Sale" },
                   { id: 10, pid: 7, name: "CD Deals" },
                   { id: 11, name: "Categories", hasChild: true },
                   { id: 12, pid: 11, name: "Songs" },
                   { id: 13, pid: 11, name: "Bestselling Albums" },
                   { id: 14, pid: 11, name: "New Releases" },
                   { id: 15, pid: 11, name: "Bestselling Songs" },
                   { id: 16, name: "MP3 Albums", hasChild: true },
                   { id: 17, pid: 16, name: "Rock" },
                   { id: 18, pid: 16, name: "Gospel" },
                   { id: 19, pid: 16, name: "Latin Music" },
                   { id: 20, pid: 16, name: "Jazz" },
                   { id: 21, name: "More in Music", hasChild: true },
                   { id: 22, pid: 21, name: "Music Trade-In" },
                   { id: 23, pid: 21, name: "Redeem a Gift Card" },
                   { id: 24, pid: 21, name: "Band T-Shirts" },
                   { id: 25, pid: 21, name: "Mobile MVC" }];
var fields={id: "id", parentId: "pid", text: "name", hasChild: "hasChild", dataSource: localData, expanded: "expanded"};
ReactDOM.render(   
  <EJ.TreeView id="treeview" fields={fields}>
  </EJ.TreeView>,
document.getElementById('treeview')
);

{% endhighlight %}


![](getting-started_images\getting-started_img2.jpeg)


N> You can find the TreeView properties from the [API reference](https://help.syncfusion.com/api/js/ejtreeview) document



