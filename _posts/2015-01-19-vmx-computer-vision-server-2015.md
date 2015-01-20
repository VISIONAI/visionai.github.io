---
layout: post
title: "VMX Computer Vision Server 2015"
description: "VMX 2015 Release"
category: "VMX"
tags: []
---
{% include JB/setup %}

<img src="/images/app_builder_intro.png" style="width:100%">

Today we’re glad to announce a fresh, spanking-new update to VMX, our
flagship computer vision server.  Today’s release focuses on usability
and contains several new features to help you save time when training
your own object detectors.

### Model Search
You can now search models inside your object library.  This is
useful when you have several hundred different detectors to choose
from.  You can sort by date, time, name, and size.

<img src="/images/load_model.png" style="width:100%">

### Image Uploading
You can now upload images into VMX via a drag-and-drop interface
from your Desktop. Modern HTML5/js lets web-based applications feel
like native applications, and uploading your own images into VMX
gives you yet another way of training and/or testing your models.

<img src="/images/video_input.png" style="width:100%">

### Session Logging
You can monitor your object detection sessions remotely. We added a
/session/#model-id/log.txt endpoint to our API which will return
the last line of the internal log.  This will report back what is
being detected by the detector and useful for creating a visual log
of what VMX sees.

### Model Editor
Inside the model-editor, you can now remove positive and/or
negative examples. Before you could only move examples between the
positive and negative side, but now you can throw away any
problematic “half-object” examples.

<img src="/images/model_editor.png" style="width:100%">

### VMX Documentation
Documentation is now bundled with VMX.  Just click the “?” icon
inside VMX and it will bring you to the appropriate help page.

### Download VMX today
If you haven’t yet purchased a copy, why wait?  Getting a license
today will give you access to today’s release, together with any
future updates. (visit us on the web at [https://vision.ai](https://vision.ai))


### How to install/update on Mac OS X:
Download the new installer:
[VMX.pkg](http://files.vision.ai/releases/VMX.pkg)
(~160MB)

If the installer detects a version of VMX already installed, it will
save both your configuration file and your model library so you won’t
have to activate again.

### How to install/update on Linux and Windows:

If you are using Linux, you'll need to first install Docker (or
boot2docker on Windows).

If this is going to be your first time installing VMX, do the following:
{% highlight ruby %}
git clone https://github.com/VISIONAI/vmx-docker-manager.git
cd vmx-docker-manager
./vmx start 3000
{% endhighlight %}

If you have a previous install of VMX, do the following:
{% highlight ruby %}
cd vmx-docker-manager
git pull
./vmx update
./vmx start 3000
{% endhighlight %}


### What’s next for vision.ai?
VMX API examples.  Seeing VMX in action. DIY-home automation.  We have
been revamping our API and are currently building a small library of
examples which show how to build simple Javascript applications using
VMX.


