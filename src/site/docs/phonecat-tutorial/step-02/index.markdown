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

In this application, we will make use of Model Driven Views (MDV) to support a 
sensible dynamic separation between page display and the data which drives it.
In this model, the application declares the relationship between the data and
the presentation, and updates to the application data are reflected in the 
presentation, and user input is assigned to the application data.  This two-way
data binding helps reduce the need for manually creating controller objects that
do these bindings by hand.

With that in mind, let's use little Web UI and Dart to declare a templated view
and its relationship with the underlying data.  We will update the `app.html` 
file to contain a dynamic view template, and add a model object (in the shape
of a `Phone` class) to our `app.dart` file.

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
            <li>Open or refresh the project in the Dart Editor</li>
            <li>Refresh your browser, or checkout the <a href="#">//TODO live demo</a></li>
          </ol>
        </div>
      </div>
  </div>
</div>

The app now contains a dynamically generated list with three phones.

The most important changes are listed below.  You can see the full diff on Github.

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

We replaced the hard-coded phone list with the [//TODO: `template`](##) directive and 
two Web UI expressions enclosed in curly braces: <code>{{ " {{ phone.name " }}}}</code>
and <code>{{ " {{ phone.snippet " }}}}</code>:

- As we learned in step 0, the curly braces around `phone.name` and `phone.snippet`
  deonte bindings.  As opposed to evaluating constants, these expressions are 
  referring to our application model, the `Phone` class, which you are about to
  see.


## Models and Classes

The `<template iterate="phone in phones">` statement uses the [//TODO: `iterate`](##) directive
to tell Web UI to iterate for each `phone` in the list of `phones`.  Where
did the list of phones come from?

In Dart, the Model part of Model Driven Views generally refers to instances
of a particular class.  In our phonecat example, that class is defined as the
`Phone` class in the `app.dart` file, and `phones` refers to a list of `Phone` 
objects.

The `Phone` class, which defines the "Model" is shown below:

{% prettify dart %}

class Phone {
  String name;
  String snippet;

  Phone(this.name, this.snippet);
}

{% endprettify %}

Then we use the Phone class to create a `List` of `phone` objects:

{% prettify dart %}

List<Phone> phones = [
  new Phone("Nexus S", "Fast just got faster with Nexus S."),
  new Phone("Motorola XOOM™ with Wi-Fi","The Next, Next Generation tablet."),
  new Phone("MOTOROLA XOOM™", "The Next, Next Generation tablet.") 
];

{% endprettify %}

Web UI binds this `phones` list to the template.

## Experiments

<i class="icon-star"> </i> 
Add another binding to `app.html`. For example:

{% prettify html %}

<p>Total number of phones: {{ " {{ phones.length " }}}}</p>

{% endprettify %}

<i class="icon-star"> </i> 
Create a new model property in 
the `app.dart` file, and bind it to the template.  For example

{% prettify dart %}

var hello = "Hello World";

{% endprettify %}

Refresh your browser and make sure it says "Hello World".

<i class="icon-star"> </i> 
Create a template that constructs a simple table.  Tables are 
fussy about the child tags, so the `template` needs to exist as an
attribute of the `table` tag itself.

{% prettify html %}

<table template iterate="row in [0,1,2,3,4,5,6,7]">
  <tr>
    <td>{{ " {{ row " }}}}</td>
  <tr>
</table>

{% endprettify  %}

Now, make the list 1-based by incrementing `row` by one in the binding:
  
{% prettify html %}

<table template iterate="row in [0,1,2,3,4,5,6,7]">
    <tr>
      <td>{{ " {{ row + 1 " }}}}</td>
    </tr>
</table>
 
{% endprettify %}

<i class="icon-star"> </i>
Now move the list of numbers into the `app.dart` code and bind using the 
list's variable name:

{% prettify dart %}

var numbers = [0,1,2,3,4,5,6,7];

{% endprettify %}

## Summary

This step introduced the idea of Model Driven Views, which allows you to have
data that is decoupled from its representation.  The view lives in a 
Web UI template, and the model objects live in source code.  In the next step, 
you will learn how to make these templates react dynamically to updates to the
underlying lists by using watchers.

<div class="btn-group span9 offset1">
  <a class="btn" href="../step-01/"><i class="icon-step-backward">&nbsp;</i>Previous</a>
  <a class="btn" href="#"><i class="icon-play">&nbsp;</i>Live Demo</a>
  <a class="btn" href="https://github.com/chrisbu/dart-phonecat/compare/step-1...step-2"><i class="icon-search">&nbsp;</i>Code Diff</a>
  <a class="btn" href="../step-03/"><i class="icon-step-forward">&nbsp;</i>Next</a>
</div>

{% endcapture %}

{% include phonecat-tutorial.html %}
