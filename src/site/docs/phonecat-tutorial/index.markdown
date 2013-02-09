---
layout: default
title: "WebUI Phone Catalog Tutorial"
description: "Using Dart WebUI to build a client side catalog."
has-permalinks: true
rel:
  author:
    - chris-buckett
    - angular.js
tutorial:
  id: tut-phonecat
article:
  written_on: 2013-02-02
  collection: everyday-dart
---

{% capture whats_the_point %}

* This blue box shows page highlights.
* Learn Web UI - a basic knowledge of the Dart language is useful.
* You'll need the Dart Editor to work through this tutorial, 
  (but it's not mandatory for Web UI).
* This tutorial is a port of the AngularJS Phone Catalog tutorial.

{% endcapture %}

{% capture content %}

A great way to get introduced to Dart WebUI is to work through this tutorial, 
which walks you through the construction of an WebUI web app. The app you 
will build is a catalog that displays a list of Android devices, lets you 
filter the list to see only devices that interest you, and then view details 
for any device.

**// TODO: Image**

Work through the tutorial to see how Dart WebUI makes browsers smarter — without 
the use of extensions or plug-ins. As you work through the tutorial, you will:

**// TODO: Edit this list!**

  * See examples of how to use client-side data binding and dependency injection
   to build dynamic views of data that change immediately in response to 
   user actions.
  * See how WebUI creates listeners on your data without the need for DOM 
  manipulation.
  * Learn a better, easier way to test your web apps.
  * Learn how to use Angular services to make common web tasks, such as getting 
  data into your app, easier.

And all of this works in any browser without modification to the browser!

When you finish the tutorial you will be able to:

**// TODO: Edit this list!**

  * Create a dynamic application that works in any browser.
  * Define the differences between Angular and common JavaScript frameworks.
  * Understand how data binding works in AngularJS.
  * Use the angular-seed project to quickly boot-strap your own projects.
  * Create and run tests.
  * Identify resources for learning more about AngularJS.

The tutorial guides you through the entire process of building a simple 
application, including writing and running unit and end-to-end tests. 
Experiments at the end of each step provide suggestions for you to learn more 
about Web UI and the application you are building.

You can go through the whole tutorial in a couple of hours or you may want to 
spend a pleasant day really digging into it. If you're looking for a shorter 
introduction to Web UI, check out the 
[Web UI](http://www.dartlang.org/articles/dart-web-components/) document.  
If you're interested in how the WebUI tools work, read the 
[Tools for Web UI](http://localhost:8080/articles/dart-web-components/tools.html)
article.

## Start Here

Although using the Dart Editor is not mandatory for working with WebUI, it does
help you a lot.  This tutorial assumes that you're working with the 
Dart Editor.

To get started, you'll need the following:

  * [The Dart Editor](http://www.dartlang.org/editor/), downloaded and 
    unzipped on your machine.  This contains all the tools you'll need to 
    get started.  Check out the [getting started](http://localhost:8080/docs/tutorials/get-started/) 
    tutorial for help.
  * The [sample code from github](https://github.com/chrisbu/dart-phonecat) that 
    goes along with this article.  The instructions below explain how to get the
    sample code.

<div class="tabbable" show="true">
  <ul class="nav nav-tabs">
    <li class="active"><a href="#git-mac" data-toggle="tab">Git on Mac/Linux</a></li>
    <li><a href="#git-win" data-toggle="tab">Git on Windows</a></li>
  </ul>
  <div class="tab-content">
    <div class="tab-pane active" id="git-mac">
      <p>If you need to install git, grab the installer 
      <a href="http://code.google.com/p/msysgit/downloads/list?q=full+installer+official+git">from google code</a>.</p>

      <p>From the terminal change into a suitable working folder, 
        such as <code>~/work/"</code> and run the 
      following command to grab a copy of the repository.
      <pre>git clone https://github.com/chrisbu/dart-phonecat.git</pre></p>
    </div>

    <div class="tab-pane" id="git-win">
      <p>If you need to install git, grab the installer 
      <a href="http://code.google.com/p/msysgit/downloads/list?q=full+installer+official+git">from google code</a>.</p>

      <p>From the command prompt (or the "Git Bash" application) change into a 
      suitable working folder, such as <code>c:\work\</code> and run the 
      following command to grab a copy of the repository.
      <pre>git clone https://github.com/chrisbu/dart-phonecat.git</pre></p>
    </div>
  </div>
</div>

Change into the new `dart-phonecat` folder using 

    cd dart-phonecat

You are now in your local git repo, in the master branch.  
Each of the code samples in this tutorial are in feature branches.  To
switch between each of the branches, use the `<code>git checkout` 
command.  For example, the following line switches to the step-0 branch,
discarding any changes you might have made to master.

    git checkout -f step-0

## Serving HTTP data from the dart-phonecat folder

The client-side app requests data from `http://localhost:8000/` 
which serves files from the root of your dart-phonecat folder.
You can use any HTTP server for this purpose, but there is a simple http server
provided in the `bin/` folder.  From the commmand line, from the 
`dart-phonecat/` folder, run:

    dart bin/simplehttpserver.dart

which will start serving files from `dart-phonecat/`

<aside class="alert alert-info" markdown="1">
  <strong>Tip:</strong>
  Add the `dart` executable, found in the editor zip file at 
  `dart/dart-sdk/bin/` to your path.  
  This makes running Dart apps from the command line easier.
</aside>

Checkout the `step-0` branch now, open the `dart-phonecat` folder in the Dart 
Editor, and let's get some awesome stuff done!

<div class="row">
  <div class="span3">
  <p style="font-size:xx-small">Version: 03 Feb 2013</p>
  </div>
  <div class="span3">
<a href="http://code.google.com/p/dart/issues/entry?template=WebUI%20Phonecat%20feedback"
 target="_blank">
<i class="icon-comment"> </i>
Send feedback
</a>
  </div>
  <div class="span3">
  <a href="/docs/phonecat-tutorial/step-00/" class="pull-right">Get Started <i class="icon-chevron-right"> </i></a>
  </div>
</div>

{% endcapture %}

{% include phonecat-tutorial.html %}
