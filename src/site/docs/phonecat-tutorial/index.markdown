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
* Learn Web-UI - a basic knowledge of the Dart language is useful.
* This tutorial is a port of the AngularJS Phone Catalog tutorial.
* Dart is an open-source platform for building structured HTML5 web apps.

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


<div class="tabbable" show="true">
  <ul class="nav nav-tabs">
    <li class="active"><a href="#git-mac" data-toggle="tab">Git on Mac/Linux</a></li>
    <li><a href="#git-win" data-toggle="tab">Git on Windows</a></li>
  </ul>
  <div class="tab-content">
    <div class="tab-pane active" id="git-mac">
      **// TODO Git on mac instructions**
    </div>

    <div class="tab-pane" id="git-win">
      **//TODO Git on windows instructions**
    </div>
  </div>
</div>


The last thing to do is to make sure your computer has a web browser and a good text editor
installed. Now, let's get some cool stuff done!


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
