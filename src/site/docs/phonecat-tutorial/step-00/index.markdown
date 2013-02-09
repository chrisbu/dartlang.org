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

You are now ready to build the WebUI phonecat app. In this step, you will become 
familiar with the most important source code files, learn how the Dart Editor 
builds a WebUI project, and run the application in the browser.

<div class="tabbable" show="true">
  <ul class="nav nav-tabs">
    <li class="active"><a href="#git-mac" data-toggle="tab">Git on Mac/Linux</a></li>
    <li><a href="#git-win" data-toggle="tab">Git on Windows</a></li>
  </ul>
  <div class="tab-content">
    <div class="tab-pane active" id="git-mac">
    	<p>In <code>dart-phonecat</code> directory, run this command:</p>
    </div>

    <div class="tab-pane" id="git-win">
      <p>Open Git Bash and run this command (in the <code>dart-phonecat</code> 
        directory):</p>
    </div>
  </div>
</div>

    git checkout -f step-0

This resets your workspace to step 0 of the tutorial app and discards any local
changes.

You must repeat this for every future step in the tutorial and 
change the number to the number of the step you are on. This will 
cause any changes you made within your working directory 
to be lost.

## Open the project

![dart-logo](/imgs/Dart_Logo_21.png)
Use the Dart Editor's `Open Folder` dialog, browse to `dart-phonecat` project.  
After a few seconds of "building" (more on this in a minute), your project's 
structure will look like this:

![Project layout](images/00_01-project-layout.png)

For the moment, you are only interested in the contents of the `web/` folder.  The `simplehttpserver.dart` is a tutorial-specific utility that you will use in later steps.

![dart-logo](/imgs/Dart_Logo_21.png)
Hit the green `Run` button to start running the app.  This starts the project 
in the Dartium web browser, and you should get an html page that shows 
"Nothing here yet!":

![First run output](images/00_02-project-first-run.png)

It's not very exciting, but that's OK - this is a running Dart Web UI app, and
some key processes have occurred to get us to this point.  Let's take a look at 
the main html file that contains our app.

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

  <p>Nothing here {{ "{{'yet'.concat('!') " }}}}</p>

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
Web UI templates and components, and adds polyfils to get cross-browser 
compatibility.

<aside class="alert alert-info" markdown="1">
  <strong>Note:</strong>
  Web UI is an implementation of the W3C Web Components specification, with 
  extensions for Model Driven Views.  Support is varied across browsers, which
  is why the Web UI compiler fills-in the gaps.
</aside>

The output HTML ...

{% endcapture %}

{% include phonecat-tutorial.html %}
