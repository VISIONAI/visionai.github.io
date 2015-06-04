---
layout: post
title: "Object Detection via VMX API"
description: ""
category: ""
author: tom
tags: ["API", "eye detection"]
image: api_output.jpg
tags: []
---
{% include JB/setup %}

The goal of object detection is to localize an object inside an
image. Unlike image classification systems which typically produce a
single category label for an entire image, an object detection system
searches for an object inside an image, and returns the location. 

HTTP-based APIs are a simple and powerful way to interact between
pieces of complex software. Today we're going to explain a simple way
to use the VMX object detection system from the command line. If you
have a directory of images that you want processed, or you want to
learn how to call VMX from an external application, then keep reading.

We will send a JPEG image to VMX and get the resulting detection result as
JSON. The resulting JSON gives you the location of the detected object
as well as the detection confidence score.

**Prerequisites**

You must have VMX installed on your local machine, download the
following gist from Github (vmx_detect.sh), and make sure to have
[jq](http://stedolan.github.io/jq/) installed. This example should
work on both Mac and Linux.

**vmx_detect.sh**
<script
src="https://gist.github.com/quantombone/a1d80f9462d3ca7ebd02.js"></script>

If you want to detect eyes in an image on your hard disk located in
`/tmp/tom.jpg`, issue the following command in the terminal:

{% highlight ruby %}
./vmx_detect.sh eyes /tmp/tom.jpg | jq .
{% endhighlight %}

This will produce something like:

```
{
  "error": 0,
  "message": "Process Image Success",
  "time": 0.219864473,
  "model": {
    "uuid": "e018112b-c9ba-437f-959d-49280acb8c9c",
    "name": "eyes",
    "size": [
      4,
      10
    ],
    "num_pos": 882,
    "num_neg": 360,
    "start_time": "2015-03-16T04:29:36.921Z",
    "end_time": "2015-04-15T07:36:46.837Z",
    "image": "models/e018112b-c9ba-437f-959d-49280acb8c9c/image.jpg"
  },
  "objects": [
    {
      "name": "eyes",
      "bb": [
        103.71047071866975,
        172.78516066270987,
        274.2631644823191,
        242.85020469972238
      ],
      "score": 8.724350218953955
    }
  ]
}
```

And that's why we use jq to format the JSON output nicely in the terminal.

<img src="/images/api_output.jpg" style="width:93%">

The resulting JSON reports the detection time (it took 0.2 seconds to
process this image), a summary of the model used for detection (an
"eyes" model with 882 positive examples), as well as the detected
objects (an "eyes" object detected at [103.7, 172.7, 274.2, 242.8]
with a confidence score of 8.7). Any confidence score above 1.0 means
that VMX is very confident about the detection.

**Behind the scenes**

This command line utility prepares the JPEG image (by using base64 to
encode the image) and sends it a VMX process which is running with the
model you want to use for detection.  The utility makes sure that the
session is already running, or it creates a new session.  If you're
running the script for the first time, it might take an additional
5-10 seconds to spawn a new VMX session. The next time you call the
script with the same model name, detection will be much quicker.

This script uses the `POST /session` endpoint to create a new session,
and the `POST /session/#SessionId` to do the actual object detection.

**Related Information**

1. The [VMX API Documentation](https://docs.vision.ai/VMXapi/index.html)
   website describes more details on the VMX API, lists all available REST
   end-points, and should be first place to go to learn more.

2. If you have any questions/comments, feel free to post a message on
   our [vision.ai forums](https://forums.vision.ai)

3. If you want to create your own object detector, you should use the
   VMX GUI, accessible by going to `http://localhost:3000` after
   installation. The
   [Learn VMX](https://docs.vision.ai/VMXAppBuilder/index.html)
   section of our Documentation goes over the GUI, but feel free to
   get in touch if you have any training-related questions.

4. It is relatively easy to write your own API wrappers inside your
   favorite programming language. Look forward to some of our own
   official vision.ai bindings, or start building your own.
   
