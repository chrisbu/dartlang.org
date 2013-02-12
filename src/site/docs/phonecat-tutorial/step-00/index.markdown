---
layout: default
title: "Step 0: Bootstrapping"
description: "Get ready to start building with WebUI... you're starting a journey of discovery"
has-permalinks: true
tutorial:
  id: phonecat-step-00
---

{% capture whats_the_point %}

* Use the Dart Editor to build your Web UI code.
* Run a WebUI app in the Dartium Browser.
* WebUI is a browser agnostic implementation of Web Components and Model 
Driven Views

{% endcapture %}

{% capture content %}

<div class="btn-group">
  <a class="btn" href="../"><i class="icon-step-backward">&nbsp;</i>Previous</a>
  <button class="btn"><i class="icon-play">&nbsp;</i>Live Demo</button>
  <button class="btn"><i class="icon-search">&nbsp;</i>Code Diff</button>
  <a class="btn" href="../step-01/"><i class="icon-step-forward">&nbsp;</i>Next</a>
</div>

You are now ready to build the Web UI phonecat app. In this step, you will become 
familiar with the most important source code files, learn how the Dart Editor 
builds a Web UI project, and run the application in the browser.  You will also
discover how the Web UI tools provide cross-browser bootstrapping for your
app.

If you've been through another Web-UI tutorial, or are happy with how the Web UI
build tool work, feel free to skip this step.

<i class="icon-star"> </i>
Using the terminal, or Git Bash, change into the  `dart-phonecat` folder
and run this command:

    git checkout -f step-0

This resets your workspace to step 0 of the tutorial app and discards any local
changes.

You must repeat this for every future step in the tutorial and 
change the number to the number of the step you are on. This will 
cause any changes you made within your working directory 
to be lost.

## Open the project

<i class="icon-star"> </i>
Use the Dart Editor's `Open Folder` dialog, browse to `dart-phonecat` project.  
After a few seconds of "building" (more on this in a minute), your project's 
structure will look like this:

![Project layout](images/00_01-project-layout.png)

For the moment, you are only interested in the contents of the `web/` folder.  
The `simplehttpserver.dart` is a tutorial-specific utility that you will use in later steps.

<i class="icon-star"> </i>
Hit the green `Run` button to start running the app.  This starts the project 
in the Dartium web browser, and you should get an html page that shows 
"Nothing here yet!":

![First run output](images/00_02-project-first-run.png)

It's not very exciting, but that's OK - this is a running Dart Web UI app, and
some key processes have occurred to get us to this point.  Take a look at 
the main html file that contains our app:

**web/app.html**:

{% prettify html %}

<!DOCTYPE html>

<html>
  <head>
    <meta charset="utf-8">
    <title>Step-0: Dart Phonecat Tutorial</title>
    <link rel="stylesheet" href="app.css">
  </head>
  <body>
     <p>Nothing here {{ "{{'yet'.concat('!') " }}}}</p>

    <script type="application/dart" src="app.dart"></script>
    <script src="packages/browser/dart.js"></script>
  </body>
</html>

{% endprettify %}

## What is this code doing?

- Dart app script tag:

  {% prettify html %}

  <script type="application/dart" src="app.dart"></script>

  {% endprettify %}

  This attaches the client-side Dart script containing your application's source
  code.  At present, this file contains a couple of library imports
  and an empty `main()` function.

- Dart.js script:
 
  {% prettify html %}

  <script src="packages/browser/dart.js"></script>

  {% endprettify %}

  This is a bootstrapper which detects if the app is running in a Dart-enabled
  browser (such as Dartium), and starts the Dart VM.  If Dart is not available,
  the script will use the JavaScript version of your app (produced by 
  [dart2js](http://www.dartlang.org/docs/dart2js/)).

- Double-curly binding with an expression:

  {% prettify html %}

  <p>Nothing here {{ "{{ 'yet'.concat('!') " }}}}</p>

  {% endprettify %}

  This line demonstrates one of the core features of Web UI's templating 
  capabilities - a binding, denoted by double curlies `{{ "{{ " }}}}` as well as 
  demonstrating a simple expression: calling the `.concat('!')` method on the 
  string `'yet'` to produce `'yet!'`.

  The binding tells WebUI that it should evaluate an expression and insert the 
  result into the DOM in place of the binding.  Rather than a one-time insert,
  as we'll see in the next steps, a binding will result in efficient continuous
  updates whenever the result of the expression changes.

  Web UI expressions are valid Dart expressions that are evaluated in the 
  context of the current model scope.

## Bootstrapping Web UI

Back to that "building" step.  When the Dart Editor detects a changed file, the
`build.dart` file in the root of your project is run.  This file invokes the 
(WebUI tools)[http://www.dartlang.org/articles/dart-web-components/tools.html], 
which perform the real magic of Web UI.  The Web UI compiler takes your 
Web UI templates and components, which consist of HTML markup and associated 
Dart classes, and adds polyfills to get cross-browser compatibility.

<aside class="alert alert-info" markdown="1">
  <strong>Note:</strong>
  Web UI is an implementation of the W3C Web Components specification, with 
  extensions for Model Driven Views.  Support is varied across browsers, which
  is why the Web UI compiler fills-in the gaps.
</aside>

The output of the Web UI compiler is placed in the `out/` subfolder, although
the Dart Editor is clever enough to know that when you launch your original 
`app.html`, it actually needs to load `out/app.html`.  The folder structure
is shown below:

![Layout after WebUI build](images/00_03-project-layout-build.dart.png)

The output HTML has changed slightly, to enable the Web UI polyfill code to 
actually provide the implementation of web components and model driven views
that is currently missing from many browsers.

<aside class="alert alert-info" markdown="1">
  <strong>Tip:</strong>
  For the most part, the Web UI compiler should be transparent to you.  The only
  time you may notice that it is when you want to view source on your app's 
  HTML.  You will be viewing the source generated by Web UI, rather than your
  own original content.
</aside>

Take a look at the output of the Web UI compiler:

**web/out/app.html**:

{% prettify html %}

<!DOCTYPE html>
<!-- This file was auto-generated from web/app.html. -->
<html>
  <head>
    <meta charset="utf-8">
    <title>Step-0: Dart Phonecat Tutorial</title>
    <link rel="stylesheet" href="../app.css">
  </head>
  <body>
    <p id="__e-1"></p>

    <script src="../packages/browser/dart.js"></script>
    <script type="application/dart" src="app.html_bootstrap.dart"></script>
  </body>
</html>

{% endprettify %}

This is almost the same as your original html, except for two parts:

- The Dart app script tag has been modified:

    {% prettify html %}

    <script type="application/dart" src="app.html_bootstrap.dart"></script>

    {% endprettify %}

    This new bootstrap file starts up the Web UI code in the browser, providing
    the necessary script to allow the data binding.  

- The binding markup has been modified:
  
    {% prettify html %}

    <p id="__e-1"></p>

    {% endprettify  %}

    The actual binding expression is moved into generated Dart code.  
    This generated code is started by the bootstrapper script, 
    which also starts your app's original `main()` entry-point function.

    You can see the generated output in the `out/app.dart` file, which contains
    the your binding text:

    {% prettify html %}

  // Original code
  main() {
    
  }

  // Additional generated code
  void init_autogenerated() {
    var _root = autogenerated.document.body;
    var __e1;

    var __t = new autogenerated.Template(_root);
    __e1 = _root.query('#__e-1');
    var __binding0 = __t.contentBind(() => ('yet'.concat('!') ));
    __e1.nodes.addAll([
      new autogenerated.Text('Nothing here '),
      __binding0
    ]);
    

    __t.create();
    __t.insert();
  }

    {% endprettify %}

## Experiments

<i class="icon-star"> </i>
Try adding a new expression to `app.html` that will do some math:

{% prettify html %}

<p>1 + 2 = {{ 1 + 2 }}</p>

{% endprettify %}

Check that the correct answer renders in your browser.

<i class="icon-star"> </i>
Try copying the url from Dartium into Firefox, and check that the JavaScript
version of your app runs correctly:

![Dart Web UI running in FireFox](images/00_04-firefox.png)

## Summary

Web UI provides a cross-browser implementation of the Web Components 
specification, and adds model driven views.  The Dart Editor uses the Web UI
compiler to produce a bootstrapped output.

Now that you are familiar with the tools, move on to [step 1](../step-01/)
, where you will see the first part of our Phone Catalog as a static html file.

<div class="btn-group">
  <a class="btn" href="../"><i class="icon-step-backward">&nbsp;</i>Previous</a>
  <button class="btn"><i class="icon-play">&nbsp;</i>Live Demo</button>
  <button class="btn"><i class="icon-search">&nbsp;</i>Code Diff</button>
  <a class="btn" href="../step-01/"><i class="icon-step-forward">&nbsp;</i>Next</a>
</div>

{% endcapture %}

{% include phonecat-tutorial.html %}

