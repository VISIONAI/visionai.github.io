---
layout: post
title: "Why we built VMX"
description: ""
category: ""
tags: []
---
{% include JB/setup %}

Computer vision (or “Machine Vision”) is the technology responsible for extracting useful information from images and video and can help answer questions such as, “Is Tom looking at the computer screen? Is my dog on the sofa? How many bottles are on the shelf?”  The field of computer vision has made great progress in the past three decades, but it is typically developed inside universities focusing on research and industrial labs focusing on products.  Look at the course offerings of most Computer Science PhD programs and you will find a computer vision course.  Look at large companies such as Google and Facebook, and you will find many engineers with Computer Vision PhD degrees.  While this technology is slowly being incorporated into our daily lives (e.g., the new generation of gaming consoles and online image search engines), putting computer vision technology to use for your very own creative applications is challenging, time consuming, as well as intimidating.  Simply put, Computer Vision technology is being developed by PhDs either for PhDs or for MegaCorps.  Why should they have all the fun?

We talked to aspiring vision developers about potential uses of our technology and were amazed about all the creative ways people envisioned using computer vision in their daily life.  In fact, everybody kept asking us “Can you build an app to do X?” where X was each person’s dream app.  After a quick back-of-the-napkin calculation, we realized that we could only build a small fraction of these apps ourselves.  We retreated to our high-tech research lab (we call it the “garage”) and came up with an alternate strategy.  Instead of building an app for John, an app for Jane, and another app for Suzy, we decided to create a tool for John, Jane, Suzy, and the rest of the world to bring their own creations to life.  Our technology, dubbed VMX, will change they way you think about computer vision.  Because different people want to interact with different objects, the single most important feature of VMX is the ability to train your own models with zero programming experience.

A world without VMX?

Computer Vision researchers in academia and high-tech research labs enjoy working on some the world’s most ambitious problems.  Consider the problem of recognizing cats in images uploaded to Facebook.  There are brown cats, black cats, hairless cats, as well as fat cats.  To make things worse, the kinds of non-cat objects found in those images are extremely diverse.  There are dogs, cheetahs, brown pillows, and piles of clothes which might at first glance look like a cat.  To make a long story short, recognizing cats in images is a very ambitious problem.  If researchers could solve this problem, then their cat detector would also work on your own cat (let’s call him Toby in this example).  But why wait until researchers have cracked the most ambitious visual recognition problem of all if all you want to build is a door opener for Toby.

The issue is that Toby, your cat, is not special for researchers.  A researcher will not spend several days building and training a custom Toby detector for you -- Toby is likely too unpopular for research to care about.  But Toby is your cat, your companion, and most likely the most important cat in the world for you.  Not only is Toby the one cat you truly care about, but Toby’s environment might not even have cheetahs or cat-like piles of brown clothes on the floor -- this makes training a Toby detector in your home much more approachable than a generic cat detector.  The only missing component is a tool which lets you, a non-computer vision expert, teach your computer all about Toby.  And that's why we built VMX. No software installations, no need for mathematics.  We designed our technology so that if you can point a webcam at Toby and click on Toby, then you can train a powerful Toby detector.  What you want to do with a Toby detector is up to you.  Be creative.  We can’t wait to see what you’ll build.

Check out [The VMX Project on kickstarter](http://kickstarter.vmx.ai).

