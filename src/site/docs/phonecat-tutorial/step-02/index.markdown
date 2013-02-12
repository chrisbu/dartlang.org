---
layout: default
title: "Step 2: Dynamic Pages"
description: "Convert your static text into dynamic content"
has-permalinks: true
tutorial:
  id: phonecat-step-02
---

{% capture whats_the_point %}

* Use the Dart Editor to build your Web UI code.
* Run a WebUI app in the Dartium Browser.
* WebUI is a browser agnostic implementation of Web Components and Model 
Driven Views

{% endcapture %}

{% capture content %}

<div class="btn-group span9 offset1">
  <a class="btn" href="../step-01/"><i class="icon-step-backward">&nbsp;</i>Previous</a>
  <a class="btn" href="#"><i class="icon-play">&nbsp;</i>Live Demo</a>
  <a class="btn" href="https://github.com/chrisbu/dart-phonecat/compare/step-1...step-2"><i class="icon-search">&nbsp;</i>Code Diff</a>
  <a class="btn" href="../step-03/"><i class="icon-step-forward">&nbsp;</i>Next</a>
</div>

Now it's time to make the web page dynamic- with Web UI.
We'll also add a test that verifies the code for the controller we're going
to add.

There are many ways to structure the code for an application.  For Web UI apps,
we encourage the use of the Model-View-Controller (MVC) design pattern to
to decouple the code and to separate concerns.  With that in mind, let's use
a little Web UI and Dart to add model, view and controller components to 
our app.

<div class="accordion">
  <div class="accordion-group">
    <div class="accordion-heading">
      <a class="accordion-toggle" 
          data-toggle="collapse" 
          data-parent="workspace-reset" href="#collapseOne">
          <i class="icon-plus"> Workspace reset instructions</i>
        </a>
      </div>
      <div id="collapseOne" class="accordion-body collapse">
        <div class="accordion-inner">
          <i class="icon-star"> </i>
          From the <code>dart-phonecat/</code> folder:
          <ol>
            <li>Reset the workspace to step 1.
            <pre>git checkout -f step-2</pre></li>
            <li>Refresh your browser, or checkout the <a href="#">//TODO live demo</a></li>
          </ol>
        </div>
      </div>
  </div>
</div>

The app now contains a list with three phones.

The most important changes are listed below.  You can see the ful diff on Github.

## View and Template

In Web UI, the **view** is a projection of the model through the HTML **template**.
This means that whenever the model changes, Web UI refreshes the appropriate
binding points, which updates the view.

The view component is constructed by Web UI from this template:

**web/app.html**:

{% prettify html %}

<ul>
  <template iterate="phone in phones">
    <li>
      <span>{{ "{{ phone.name " }}}}<span>
      <p>{{ "{{ phone.snippet " }}}}</p>
    </li>  
  </template>
</ul>

{% endprettify %}

We replaced the hard-coded phone list with the [//TODO template](##) directive and 
two Web UI expressions enclosed in curly braces: <code>{{ " {{ phone.name " }}}}</code>
and <code>{{ " {{ phone.snippet " }}}}</code>:

- The `<template iterate="phone in phones">` statement uses the `iterate` directive
  to tell Web UI to iterate for each `phone` in the list of `phones`.  Where
  did the list of phones come from?

  The phonecat app consists of both the `app.html` _and_ `app.dart` files.  In
  our `app.dart` file, we can define code structures and objects.

  There are two key items that we've added - the first is a `Phones` class, 
  shown below:

  {% prettify dart %}

  class Phone {
    String name;
    String snippet;
  
    Phone(this.name, this.snippet);
  }

  {% endprettify %}

  Then we use the Phone class to create a List of phone objects:

  {% prettify dart %}

  List<Phone> phones = [
    new Phone("Nexus S", "Fast just got faster with Nexus S."),
    new Phone("Motorola XOOM™ with Wi-Fi","The Next, Next Generation tablet."),
    new Phone("MOTOROLA XOOM™", "The Next, Next Generation tablet.") 
  ];

  {% endprettify %}

  Web UI binds this `phones` list to the template.

- As we learned in step 0, the curly braces around `phone.name` and `phone.snippet`
  deonte bindings.  As opposed to evaluating constants, these expressions are 
  referring to our application model, the `Phone` class, which was setup in 
  our `app.dart` file.

## Experiments

<i class="icon-star"> </i>
Try adding more static HTML to `app.html`.  For example: 

{% prettify html %}

<p>Total number of phones: 2</p>

{% endprettify %}

## Summary

This addition to your app uses static HTML to display the list. Now, 
let's go to step 2 to learn how to use Web UI to dynamically generate the 
same list.

<div class="btn-group span9 offset1">
  <a class="btn" href="../step-01/"><i class="icon-step-backward">&nbsp;</i>Previous</a>
  <a class="btn" href="#"><i class="icon-play">&nbsp;</i>Live Demo</a>
  <a class="btn" href="https://github.com/chrisbu/dart-phonecat/compare/step-1...step-2"><i class="icon-search">&nbsp;</i>Code Diff</a>
  <a class="btn" href="../step-03/"><i class="icon-step-forward">&nbsp;</i>Next</a>
</div>

{% endcapture %}

{% include phonecat-tutorial.html %}
