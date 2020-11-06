---
layout: post
title: Getting-Started for Angular 2 Upload box
description: getting started for Angular 2 Upload box
platform:React JS
control: Uploadbox
documentation: ug
keywords:Uploadbox,js uploadbox,ejuploadbox
---

# Getting Started

This section explains briefly about how to create an **Uploadbox** in your application with **Angular 2.** **Essential JavaScript Uploadbox** widget provides support to upload files or photos within your web page. From the following guidelines, you can learn how to upload the files that are used in a Resume Upload scenario. This helps you to restrict some file extensions when you upload the resume in server by using **Uploadbox** control.

The following screenshot demonstrates the functionality of **Uploadbox** with the file extension.

![](Getting-Started_images/Getting-Started_img1.png) 

In the above screenshot, you can upload a resume that allows **.txt** files. This helps you to avoid unsupported resume formats getting uploaded in a server.

N> To get upload the file, you should either run this sample in Visual Studio IDE or host in local IIS.

## Create Uploadbox widgets in React JS

**Essential JavaScript Uploadbox** widget basically renders built-in features like upload multiple files, and deletes the files from **Uploadbox**. You can know the status of uploading the file whether it is completed or failed and you can retry uploading the files.  You can easily create the **Uploadbox** widget by using the following steps.

You can create a React application and add necessary scripts and styles with the help of the given [React Getting Started Documentation.](https://help.syncfusion.com/reactjs/overview)

Create a JSX file for rendering Uploadbox component using &lt;EJ.Uploadbox&gt; syntax. Add required properties to it in &lt;EJ.Uploadbox&gt; tag element

{% highlight js %}

var DefaultUploadbox = React.createClass({
    render: function () {
        return (
            <div id="tooltip_default">
                <div class="posupload">Select a file to upload </div>
                <EJ.Uploadbox id="UploadDefault"></EJ.Uploadbox>
            </div>
           );
        }
   });
ReactDOM.render(<DefaultUploadbox />, document.getElementById('uploadbox-default'));

{% endhighlight %}

Define an HTML element for adding Uploadbox in the application and refer the JSX file.

{% highlight html %}

<div id="uploadbox-default"></div>
<script src="app/uploadbox/default.js">

{% endhighlight %}

{% highlight css %}

    <style>
       #targetElement {
        width: 500px;
        height: 500px;
        margin: 0 auto;
        }

       #UploadDefault {
        margin: 0 auto;
      }
    </style>

{% endhighlight %}

Create a new handler file (.ashx) and save it as **saveFiles.ashx** and then copy the following code into it.

{% highlight c# %}

SaveFiles.ashx

    public void ProcessRequest(HttpContext context)
    {
        string targetFolder = HttpContext.Current.Server.MapPath("uploadfiles");
        if (!Directory.Exists(targetFolder))
        {
            Directory.CreateDirectory(targetFolder);
        }
        HttpRequest request = context.Request;
        HttpFileCollection uploadedFiles = context.Request.Files;
        if (uploadedFiles != null && uploadedFiles.Count > 0)
        {
            for (int i = 0; i < uploadedFiles.Count; i++)
            {
                if (uploadedFiles[i].FileName != null && uploadedFiles[i].FileName != "")
                {
                    string fileName = uploadedFiles[i].FileName;
                    int indx = fileName.LastIndexOf("\\");
                    if (indx > -1)
                    {
                        fileName = fileName.Substring(indx + 1);
                    }
                    uploadedFiles[i].SaveAs(targetFolder + "\\" + fileName);
                }
            }
        }
    }

{% endhighlight %}

Create a new handler file (.ashx) and save it as **removeFiles.ashx** and then copy the following code into it.

{% highlight c# %}

removeFiles.ashx

    public void ProcessRequest(HttpContext context)
    {
        System.Collections.Specialized.NameValueCollection s = context.Request.Params;
        string fileName = s["fileNames"];
        string targetFolder = HttpContext.Current.Server.MapPath("uploadfiles");
        if (Directory.Exists(targetFolder))
        {
            string physicalPath = targetFolder + "\\" + fileName;
            if (System.IO.File.Exists(physicalPath))
            {
                System.IO.File.Delete(physicalPath);
            }
        }
    }

{% endhighlight %}

Add the following code example to assign saveUrl and removeUrl for Uploadbox

{% highlight html %}

var DefaultUploadbox = React.createClass({
    render: function () {
        return (
            <div id="tooltip_default">
                <div class="posupload">Select a file to upload </div>
                <EJ.Uploadbox id="UploadDefault" saveUrl= {savefiles} removeUrl= {removefiles}></EJ.Uploadbox>
            </div>
           );
        }
   });
ReactDOM.render(<DefaultUploadbox />, document.getElementById('uploadbox-default'));

{% endhighlight %}

The following screenshot displays an **Uploadbox** control.

![](Getting-Started_images/Getting-Started_img2.png) 

After you upload the files, the following screen shot is displayed. 

![](Getting-Started_images/Getting-Started_img3.png) 

N> The above screenshot displays the Uploadbox control that shows the files are uploaded successfully.

## Set Restriction for File Extension

In a real-time scenario, some file extensions are restricted. You can allow files and restrict files by using the following two properties **extensionsAllow** and **extensionsDeny** enabled in **Uploadbox**. 

N> The SaveUrl and RemoveUrl are the same as above (see step 4)

Add input elements to create elements for file extension.

N> Add the following input elements and two button elements to give file extensions that should support uploading. 

{% highlight js %}

var DefaultUploadbox = React.createClass({
    function onClickAllow(args){
        var uploadobject = $("#uploadDefault").data("ejUploadbox");
        uploadobject.option('extensionsAllow', $("#fileallow").val());
        uploadobject.option('extensionsDeny', "");
    }
    function onclickDeny(){
        var uploadobject = $("#uploadDefault").data("ejUploadbox");
        uploadobject.option('extensionsAllow', "");
        uploadobject.option('extensionsDeny', $("#filedeny").val());
    }
    render: function () {
        return (
            <div id="uploadbox_default"><table id="uploadTable">
        <tr>
            <td>
                Extensions:
            </td>

        </tr>
        <tr>
            <td>
                <input type="text" id="fileallow" class="ejinputtext" placeholder="Format" />
                <input ej-button type="submit" name="allow" value="Allow" click={onClickAllow} />
            </td>

        </tr>
        <tr>
            <td>
                <input type="text" id="filedeny" class="ejinputtext" placeholder="Format" />
                <input ej-button type="submit" name="deny" value="Deny" click={onclickDeny} />
            </td>
            <td>
                <div>Select a file to upload</div>
                <div style="width:100px;height:35px;"> 
                <EJ.Uploadbox id="UploadDefault" saveUrl= {savefiles} removeUrl= {removefiles}></EJ.Uploadbox>
            </td>
            </tr>
        </table>
        </div>
           );
        }
   });
ReactDOM.render(<DefaultUploadbox />, document.getElementById('uploadbox-default'));

{% endhighlight %}

Add the given styles to display the **Uploadbox** with margin alignments.

{% highlight css %}

    <style>
      #targetElement {
        width: 520px;
        height: 500px;
        margin: 0 auto;
       }
      #UploadDefault {
        float: right;
      }
      #uploadTable {
        width: 100%;
       }
      #fileallow, #filedeny {
        width: 150px;
        height: 20px;
        padding: 5px;
      }
    </style> 

{% endhighlight %}

N> You can restrict one or more files at a time by giving it as .html,.txt

The following screenshot displays an **Uploadbox** control with the file extension.

![](Getting-Started_images/Getting-Started_img4.png) 

The above screenshot shows the **Uploadbox** that allows “**.txt”** file formats. You can give  number of  file formats in both allow and deny textbox elements.

## Upload Multiple Files

You can click the **Browse** button and select  files to upload multiple files in **Uploadbox** control. You can see the selected files in **Uploadbox** control and you can upload all the files.

The following screenshot displays an **Uploadbox** control with multiple files.

![](Getting-Started_images/Getting-Started_img5.png) 

