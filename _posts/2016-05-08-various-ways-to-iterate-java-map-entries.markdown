---
layout:     post
title:      "Various ways to Iterate Java Map Entries"
subtitle:   "Over period of time java has added new constructs to do same task more succinctly and efficiently. And same holds good for iterating a map. In this short tutorial let's look at old and latest ways to iterate a map."
date:       2016-05-08 12:10:00
author:     "vishwambharu@gmail.com"
header-img: "img/post-bg-03.jpg"
---

<h2 class="section-heading">Iterating a Map using an Iterator</h2>
<!-- HTML generated using hilite.me --><div style="background: #ffffff; overflow:auto;width:auto;border:solid gray;border-width:.1em .1em .1em .8em;padding:.2em .6em;"><table><tr><td><pre style="margin: 0; line-height: 125%"> 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18
19
20
21
22
23</pre></td><td><pre style="margin: 0; line-height: 125%"><span style="color: #008800; font-weight: bold">package</span> main<span style="color: #333333">.</span><span style="color: #0000CC">java</span><span style="color: #333333">.</span><span style="color: #0000CC">lessons</span><span style="color: #333333">;</span>

<span style="color: #008800; font-weight: bold">import</span> <span style="color: #0e84b5; font-weight: bold">java.util.HashMap</span><span style="color: #333333">;</span>
<span style="color: #008800; font-weight: bold">import</span> <span style="color: #0e84b5; font-weight: bold">java.util.Iterator</span><span style="color: #333333">;</span>
<span style="color: #008800; font-weight: bold">import</span> <span style="color: #0e84b5; font-weight: bold">java.util.Map</span><span style="color: #333333">;</span>

<span style="color: #008800; font-weight: bold">public</span> <span style="color: #008800; font-weight: bold">class</span> <span style="color: #BB0066; font-weight: bold">IterateMapEntries</span> <span style="color: #333333">{</span>

    <span style="color: #008800; font-weight: bold">public</span> <span style="color: #008800; font-weight: bold">static</span> <span style="color: #333399; font-weight: bold">void</span> <span style="color: #0066BB; font-weight: bold">main</span><span style="color: #333333">(</span>String<span style="color: #333333">...</span> args<span style="color: #333333">)</span> <span style="color: #333333">{</span>
        Map<span style="color: #333333">&lt;</span>String<span style="color: #333333">,</span> String<span style="color: #333333">&gt;</span> map <span style="color: #333333">=</span> <span style="color: #008800; font-weight: bold">new</span> HashMap<span style="color: #333333">();</span>
        map<span style="color: #333333">.</span><span style="color: #0000CC">put</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;California&quot;</span><span style="color: #333333">,</span> <span style="background-color: #fff0f0">&quot;Sacramento&quot;</span><span style="color: #333333">);</span>
        map<span style="color: #333333">.</span><span style="color: #0000CC">put</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;Texas&quot;</span><span style="color: #333333">,</span> <span style="background-color: #fff0f0">&quot;Austin&quot;</span><span style="color: #333333">);</span>
        map<span style="color: #333333">.</span><span style="color: #0000CC">put</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;Florida&quot;</span><span style="color: #333333">,</span> <span style="background-color: #fff0f0">&quot;Tallahassee&quot;</span><span style="color: #333333">);</span>
        map<span style="color: #333333">.</span><span style="color: #0000CC">put</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;Georgia&quot;</span><span style="color: #333333">,</span> <span style="background-color: #fff0f0">&quot;Atlanta&quot;</span><span style="color: #333333">);</span>

        <span style="color: #888888">/** 1. Iterating Map using an Iterator. **/</span>
        Iterator iterator <span style="color: #333333">=</span> map<span style="color: #333333">.</span><span style="color: #0000CC">entrySet</span><span style="color: #333333">().</span><span style="color: #0000CC">iterator</span><span style="color: #333333">();</span>
        <span style="color: #008800; font-weight: bold">while</span> <span style="color: #333333">(</span>iterator<span style="color: #333333">.</span><span style="color: #0000CC">hasNext</span><span style="color: #333333">())</span> <span style="color: #333333">{</span>
            Map<span style="color: #333333">.</span><span style="color: #0000CC">Entry</span><span style="color: #333333">&lt;</span>String<span style="color: #333333">,</span> String<span style="color: #333333">&gt;</span> entry <span style="color: #333333">=</span> <span style="color: #333333">(</span>Map<span style="color: #333333">.</span><span style="color: #0000CC">Entry</span><span style="color: #333333">)</span> iterator<span style="color: #333333">.</span><span style="color: #0000CC">next</span><span style="color: #333333">();</span>
            System<span style="color: #333333">.</span><span style="color: #0000CC">out</span><span style="color: #333333">.</span><span style="color: #0000CC">println</span><span style="color: #333333">(</span>String<span style="color: #333333">.</span><span style="color: #0000CC">format</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;Key:%s Value:%s&quot;</span><span style="color: #333333">,</span> entry<span style="color: #333333">.</span><span style="color: #0000CC">getKey</span><span style="color: #333333">(),</span> entry<span style="color: #333333">.</span><span style="color: #0000CC">getValue</span><span style="color: #333333">()));</span>
        <span style="color: #333333">}</span>
    <span style="color: #333333">}</span>
<span style="color: #333333">}</span>
</pre></td></tr></table></div>


<h2 class="section-heading">Iterating a Map using for each loop over Map entries</h2>
<!-- HTML generated using hilite.me --><div style="background: #ffffff; overflow:auto;width:auto;border:solid gray;border-width:.1em .1em .1em .8em;padding:.2em .6em;"><table><tr><td><pre style="margin: 0; line-height: 125%"> 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18
19
20
21</pre></td><td><pre style="margin: 0; line-height: 125%"><span style="color: #008800; font-weight: bold">package</span> main<span style="color: #333333">.</span><span style="color: #0000CC">java</span><span style="color: #333333">.</span><span style="color: #0000CC">lessons</span><span style="color: #333333">;</span>

<span style="color: #008800; font-weight: bold">import</span> <span style="color: #0e84b5; font-weight: bold">java.util.HashMap</span><span style="color: #333333">;</span>
<span style="color: #008800; font-weight: bold">import</span> <span style="color: #0e84b5; font-weight: bold">java.util.Iterator</span><span style="color: #333333">;</span>
<span style="color: #008800; font-weight: bold">import</span> <span style="color: #0e84b5; font-weight: bold">java.util.Map</span><span style="color: #333333">;</span>

<span style="color: #008800; font-weight: bold">public</span> <span style="color: #008800; font-weight: bold">class</span> <span style="color: #BB0066; font-weight: bold">IterateMapEntries</span> <span style="color: #333333">{</span>

    <span style="color: #008800; font-weight: bold">public</span> <span style="color: #008800; font-weight: bold">static</span> <span style="color: #333399; font-weight: bold">void</span> <span style="color: #0066BB; font-weight: bold">main</span><span style="color: #333333">(</span>String<span style="color: #333333">...</span> args<span style="color: #333333">)</span> <span style="color: #333333">{</span>
        Map<span style="color: #333333">&lt;</span>String<span style="color: #333333">,</span> String<span style="color: #333333">&gt;</span> map <span style="color: #333333">=</span> <span style="color: #008800; font-weight: bold">new</span> HashMap<span style="color: #333333">();</span>
        map<span style="color: #333333">.</span><span style="color: #0000CC">put</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;California&quot;</span><span style="color: #333333">,</span> <span style="background-color: #fff0f0">&quot;Sacramento&quot;</span><span style="color: #333333">);</span>
        map<span style="color: #333333">.</span><span style="color: #0000CC">put</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;Texas&quot;</span><span style="color: #333333">,</span> <span style="background-color: #fff0f0">&quot;Austin&quot;</span><span style="color: #333333">);</span>
        map<span style="color: #333333">.</span><span style="color: #0000CC">put</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;Florida&quot;</span><span style="color: #333333">,</span> <span style="background-color: #fff0f0">&quot;Tallahassee&quot;</span><span style="color: #333333">);</span>
        map<span style="color: #333333">.</span><span style="color: #0000CC">put</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;Georgia&quot;</span><span style="color: #333333">,</span> <span style="background-color: #fff0f0">&quot;Atlanta&quot;</span><span style="color: #333333">);</span>

    <span style="color: #888888">/** Iterating Map using for each loop over Map entries. **/</span>
        <span style="color: #008800; font-weight: bold">for</span> <span style="color: #333333">(</span>Map<span style="color: #333333">.</span><span style="color: #0000CC">Entry</span> entry <span style="color: #333333">:</span> map<span style="color: #333333">.</span><span style="color: #0000CC">entrySet</span><span style="color: #333333">())</span> <span style="color: #333333">{</span>
            System<span style="color: #333333">.</span><span style="color: #0000CC">out</span><span style="color: #333333">.</span><span style="color: #0000CC">println</span><span style="color: #333333">(</span>String<span style="color: #333333">.</span><span style="color: #0000CC">format</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;Key:%s Value:%s&quot;</span><span style="color: #333333">,</span> entry<span style="color: #333333">.</span><span style="color: #0000CC">getKey</span><span style="color: #333333">(),</span> entry<span style="color: #333333">.</span><span style="color: #0000CC">getValue</span><span style="color: #333333">()));</span>
        <span style="color: #333333">}</span>
    <span style="color: #333333">}</span>
<span style="color: #333333">}</span>
</pre></td></tr></table></div>


<h2 class="section-heading">Iterating Map using java 1.8 forEach and lambda constructs</h2>
<!-- HTML generated using hilite.me --><div style="background: #ffffff; overflow:auto;width:auto;border:solid gray;border-width:.1em .1em .1em .8em;padding:.2em .6em;"><table><tr><td><pre style="margin: 0; line-height: 125%"> 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18
19
20
21</pre></td><td><pre style="margin: 0; line-height: 125%"><span style="color: #008800; font-weight: bold">package</span> main<span style="color: #333333">.</span><span style="color: #0000CC">java</span><span style="color: #333333">.</span><span style="color: #0000CC">lessons</span><span style="color: #333333">;</span>

<span style="color: #008800; font-weight: bold">import</span> <span style="color: #0e84b5; font-weight: bold">java.util.HashMap</span><span style="color: #333333">;</span>
<span style="color: #008800; font-weight: bold">import</span> <span style="color: #0e84b5; font-weight: bold">java.util.Iterator</span><span style="color: #333333">;</span>
<span style="color: #008800; font-weight: bold">import</span> <span style="color: #0e84b5; font-weight: bold">java.util.Map</span><span style="color: #333333">;</span>

<span style="color: #008800; font-weight: bold">public</span> <span style="color: #008800; font-weight: bold">class</span> <span style="color: #BB0066; font-weight: bold">IterateMapEntries</span> <span style="color: #333333">{</span>

    <span style="color: #008800; font-weight: bold">public</span> <span style="color: #008800; font-weight: bold">static</span> <span style="color: #333399; font-weight: bold">void</span> <span style="color: #0066BB; font-weight: bold">main</span><span style="color: #333333">(</span>String<span style="color: #333333">...</span> args<span style="color: #333333">)</span> <span style="color: #333333">{</span>
        Map<span style="color: #333333">&lt;</span>String<span style="color: #333333">,</span> String<span style="color: #333333">&gt;</span> map <span style="color: #333333">=</span> <span style="color: #008800; font-weight: bold">new</span> HashMap<span style="color: #333333">();</span>
        map<span style="color: #333333">.</span><span style="color: #0000CC">put</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;California&quot;</span><span style="color: #333333">,</span> <span style="background-color: #fff0f0">&quot;Sacramento&quot;</span><span style="color: #333333">);</span>
        map<span style="color: #333333">.</span><span style="color: #0000CC">put</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;Texas&quot;</span><span style="color: #333333">,</span> <span style="background-color: #fff0f0">&quot;Austin&quot;</span><span style="color: #333333">);</span>
        map<span style="color: #333333">.</span><span style="color: #0000CC">put</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;Florida&quot;</span><span style="color: #333333">,</span> <span style="background-color: #fff0f0">&quot;Tallahassee&quot;</span><span style="color: #333333">);</span>
        map<span style="color: #333333">.</span><span style="color: #0000CC">put</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;Georgia&quot;</span><span style="color: #333333">,</span> <span style="background-color: #fff0f0">&quot;Atlanta&quot;</span><span style="color: #333333">);</span>

    <span style="color: #888888">/** Iterating Map using java 1.8 forEach &amp; lambda constructs. **/</span>
        map<span style="color: #333333">.</span><span style="color: #0000CC">forEach</span><span style="color: #333333">((</span>k<span style="color: #333333">,</span> v<span style="color: #333333">)</span> <span style="color: #333333">-&gt;</span> <span style="color: #333333">{</span>
            System<span style="color: #333333">.</span><span style="color: #0000CC">out</span><span style="color: #333333">.</span><span style="color: #0000CC">println</span><span style="color: #333333">(</span>String<span style="color: #333333">.</span><span style="color: #0000CC">format</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;Key:%s Value:%s&quot;</span><span style="color: #333333">,</span> k<span style="color: #333333">,</span> v<span style="color: #333333">));</span>
        <span style="color: #333333">});</span>
    <span style="color: #333333">}</span>
<span style="color: #333333">}</span>
</pre></td></tr></table></div>


<p>I'd highly recommend to start using java 1.8 forEach construct to iterate Map. It is so crisp and clear :)</p>
