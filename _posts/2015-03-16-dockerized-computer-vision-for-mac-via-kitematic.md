---
layout: post
title: "Dockerized Computer Vision for Mac via Kitematic"
description: ""
category: "VMX"
author: tom
tags: ["Docker", "Mac", "boot2docker", "Kitematic"]
image: kitematic.png
---
{% include JB/setup %}

[Kitematic](https://kitematic.com/), is a new cool open-source
software project which brings a great looking GUI to Mac OS X users
wanting to explore applications that are shipped as Docker
containers. Kitematic was recently
[acquired by Docker](http://blog.docker.com/2015/03/kitematic-a-docker-gui-joins-the-docker-family/),
giving them much credibility, and I was immediately excited as I'm
always looking for new ways to deliver our flagship computer vision
server to a larger audience.  In other words, maintaining and shipping
multi-platform builds is not nearly as much fun as training object
detectors. :-)

<img src="/images/kitematic.png" style="width:30%">

### Kitematic vs. boot2docker

Before Kitematic, Mac users had to use
[boot2docker](http://boot2docker.io/) (or install a Linux Virtual
Machine) to enjoy the benefits of Docker.  This works for those Mac
users who are savvy on the command line, as boot2docker gives you all
of Docker's features like building your own images. If you're using
Docker in your normal development workflow on Linux machines in the
cloud (like us), then boot2docker for Mac is still highly
recommended. If you haven't yet jumped on Docker bandwagon, you really
should.

However, if you just want to play with somebody's application,
Kitematic provides an exceptional installation experience.  It assumes
that the authors have already published their images on Docker Hub
(which is true for many great applications, including our very own
vision.ai software), and I'll be really excited once they have a
Windows port.

### Want to install our vision.ai software via Kitematic?


#### Step 1: Download and install Kitematic

<a href="https://kitematic.com/download/"><img src="/images/kitematic_icon.png" style="width:50px"></a>

Download the Kitematic installer and wait a few minutes as it installs
all of the Docker requirements behind the scenes.

#### Step 2: Find the visionai-kitematic image
As of today you can also find VMX in Kitematic when you search
for `visionai/vmx-kitematic`. 

<img src="/images/visionai_kitematic.png" style="width:100%">

### Step 3: Hit "create" and go grab a coffee

Hitting create will download the VMX image (about 1.8GB) from Docker
Hub and it will automatically start when finished.  You should now see
the VMX GUI inside the Kitematic preview window.  Clicking the preview
window will open up VMX inside a browser with a randomly assigned
port.  One last step and you're on your way to Computer Vision nirvana.

### Step 4: Active your copy of VMX

You can purchase an individual developer license for VMX $100 at our
[vision.ai store](https://beta.vision.ai/purchase),
but if you want to try the Kitematic installer we have a limited
number of coupons for 10% off. Just enter the code KITEMATIC when
checking out using Stripe.

If you've already obtained an activation key from us (either
as an invite or by purchasing) but want to an extra activation key to
try out the Kitematic installer, just let us know and we'll send you
one.

---

We created a special single-container version of VMX which is suitable
for Kitematic, but still encourage all users comfortable with Docker
to use our
[vmx-docker-manager](https://github.com/VISIONAI/vmx-docker-manager)
which allows you to update and backup the data inside VMX.  The
vmx-docker-manager runs our full multi-container application and makes
updating much faster.

### The future of Docker containers

We are still providing our VMX Computer Vision server as a native Mac
OS X installer [VMX.pkg](https://files.vision.ai/releases/VMX.pkg), but I
look forward to the time where a single build can be shipped out to
Windows, Mac OS X, Linux machines, and datacenters.

I see a future when more applications, especially scientific ones, are
shipped as Docker Containers.  Docker makes development, deployment,
and (as we can now see) distribution much easier and allows developers
to get the same high-quality build that the authors are using.

The next time you consider shipping shipping an application which is
installable on Linux and requires Apache config files, a custom
version of Python, just ask yourself: why not Docker?
