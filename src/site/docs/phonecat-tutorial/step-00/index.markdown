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

Use the Dart Editor's `Open Folder` dialog, browse to `dart-phonecat` project.  
After a few seconds of "analyzing" and "building" (more on this in a minute), 
the your project structure will look like this:

![Project layout](images/00_01-project-layout.png)

Hit the green `Run` button to start running the app.  This starts the project 
in the Dartium web browser, and you should get an html page that shows 
"Nothing here yet!":

![First run output](images/00_02-project-first-run.png)

It's not very exciting, but that's OK - this is a running Dart web-ui app, and
some key processes have occurred to get us to this point.



{% endcapture %}

{% include phonecat-tutorial.html %}
