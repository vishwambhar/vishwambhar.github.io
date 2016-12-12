---
layout:     post
title:      "Testing Out TensorFlow Environment"
subtitle:   "Testing Out TensorFlow Environment."
date:       2016-12-11 20:40:00
author:     "vishwambharu@gmail.com"
header-img: "img/post-bg-03.jpg"
---


<p>Automated driving sounds cool, so I'm too excited to learn something about the technologies involved in this space. And one of the first things I had to do was to learn <a href="https://tensorflow.org"> TensorFlow.</a> 
<p>
Here are the steps I used to install TensorFlow on macOS Sierra.
</p>
</p>

<p>
<ul type="disc">
<li>Install <a href="https://docs.continuum.io/anaconda/install">Anaconda.</a></li>
<li>Run the following steps to setup Anaconda environment:
<!-- HTML generated using hilite.me --><div style="background: #ffffff; overflow:auto;width:auto;border:solid gray;border-width:.1em .1em .1em .8em;padding:.2em .6em;"><pre style="margin: 0; line-height: 125%">conda create <span style="color: #333333">--</span>name<span style="color: #333333">=</span>IntroToTensorFlow python<span style="color: #333333">=</span><span style="color: #0000DD; font-weight: bold">3</span> anaconda
source activate IntroToTensorFlow
conda install <span style="color: #333333">-</span>c conda<span style="color: #333333">-</span>forge tensorflow
</pre></div>
</li>
<li>Run the following code in your favourate python code editor to make sure TensorFlow environment is working as expected:
<!-- HTML generated using hilite.me --><div style="background: #ffffff; overflow:auto;width:auto;border:solid gray;border-width:.1em .1em .1em .8em;padding:.2em .6em;"><pre style="margin: 0; line-height: 125%"><span style="color: #008800; font-weight: bold">import</span> <span style="color: #0e84b5; font-weight: bold">tensorflow</span> <span style="color: #008800; font-weight: bold">as</span> <span style="color: #0e84b5; font-weight: bold">tf</span>
<span style="color: #008800; font-weight: bold">import</span> <span style="color: #0e84b5; font-weight: bold">numpy</span> <span style="color: #008800; font-weight: bold">as</span> <span style="color: #0e84b5; font-weight: bold">np</span>
<span style="color: #008800; font-weight: bold">import</span> <span style="color: #0e84b5; font-weight: bold">matplotlib.pyplot</span> <span style="color: #008800; font-weight: bold">as</span> <span style="color: #0e84b5; font-weight: bold">plt</span>
<span style="color: #333333">%</span>matplotlib inline

<span style="color: #888888"># 2x5 Tensor of randomally distributed numbers</span>
normal <span style="color: #333333">=</span> tf<span style="color: #333333">.</span>random_normal([<span style="color: #0000DD; font-weight: bold">2</span>, <span style="color: #0000DD; font-weight: bold">5</span>], mean<span style="color: #333333">=</span><span style="color: #6600EE; font-weight: bold">2.0</span>, stddev<span style="color: #333333">=</span><span style="color: #6600EE; font-weight: bold">4.0</span>)
<span style="color: #008800; font-weight: bold">with</span> tf<span style="color: #333333">.</span>Session() <span style="color: #008800; font-weight: bold">as</span> sess:
    out <span style="color: #333333">=</span> sess<span style="color: #333333">.</span>run(normal)
    <span style="color: #007020">print</span>(out) <span style="color: #888888"># print the 2x5 matrix</span>
    x, y <span style="color: #333333">=</span> out <span style="color: #888888"># split up the 2x5 matrix into two 1x5 vectors, x and y</span>
    plt<span style="color: #333333">.</span>scatter(x, y) <span style="color: #888888"># create scatter plot with x and y</span>
    plt<span style="color: #333333">.</span>show() <span style="color: #888888"># show scatter plot</span>
</pre></div>

You should see the scatter plot output something similar to this:

<a href="#">
    <img src="{{ site.baseurl }}/img/testing_out_tensorflow_environment_pic1.png" alt="Output">
</a>
</li>
</ul>
</p>
