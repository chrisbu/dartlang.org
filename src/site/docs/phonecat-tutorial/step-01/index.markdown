---
layout: default
title: "Step 1: Static Pages"
description: "It all starts with a static page.  It will get more exciting..."
has-permalinks: true
tutorial:
  id: phonecat-step-01
---

{% capture whats_the_point %}

* Use the Dart Editor to build your Web UI code.
* Run a WebUI app in the Dartium Browser.
* WebUI is a browser agnostic implementation of Web Components and Model 
Driven Views

{% endcapture %}

{% capture content %}

<div class="btn-group">
  <a class="btn" href="../step-00/"><i class="icon-step-backward"> </i>Previous</a>
  <button class="btn"><i class="icon-play"> </i>Live Demo</button>
  <a class="btn" href="https://github.com/chrisbu/dart-phonecat/compare/step-0...step-1"><i class="icon-search"> </i>Code Diff</a>
  <a class="btn" href="../step-01/"><i class="icon-step-forward"> </i>Next</a>
</div>

In order to illustrate how Web UI enhances standard HTML, you will create a 
purely _static_ HTML page and then examine how we can turn this HTML code into
a template that Web UI will use to dynamically display the same result with any
set of data.

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
            <pre>git checkout -f step-1</pre></li>
            <li>Refresh your browser, or checkout the <a href="#">//TODO live demo</a></li>
          </ol>
        </div>
      </div>
  </div>
</div>

In this step you will add some basic information about two cell phones.

The most important changes are listed below.  You can see the full 
diff on [Github](https://github.com/chrisbu/dart-phonecat/compare/step-0...step-1)

**web/app.html**:

{% prettify html %}

<ul>
  <li>
    <span>Nexus S</span>
    <p>
      Fast just got faster with Nexus S.
    </p>
  </li>
  <li>
    <span>Motorola XOOM™ with Wi-Fi</span>
    <p>
      The Next, Next Generation tablet.
    </p>
  </li>
</ul>

{% endprettify %}

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

{% endcapture %}

<div class="btn-group">
  <a class="btn" href="../step-00/"><i class="icon-step-backward"> </i>Previous</a>
  <button class="btn"><i class="icon-play"> </i>Live Demo</button>
  <a class="btn" href="https://github.com/chrisbu/dart-phonecat/compare/step-0...step-1"><i class="icon-search"> </i>Code Diff</a>
  <a class="btn" href="../step-01/"><i class="icon-step-forward"> </i>Next</a>
</div>

{% include phonecat-tutorial.html %}
