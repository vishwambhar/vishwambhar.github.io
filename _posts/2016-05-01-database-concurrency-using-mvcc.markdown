---
layout:     post
title:      "Database Concurrency using MVCC"
subtitle:   "MVCC stands for multi-version concurrency control. Whole idea behind MVCC is to improve concurrency of database system by reducing contention and locks."
date:       2016-05-01 12:02:00
author:     "vishwambharu@gmail.com"
header-img: "img/post-bg-03.jpg"
---


<p>Relational databases support principles of <a href="https://en.wikipedia.org/wiki/ACID">ACID model</a> for reliability and consistency. ACID architectural pattern guarantees that the database transaction executes reliably. <strong>'Isolated'</strong> principle states that in case of multiple transactions occurring simultaneously, one transaction shouldn’t see the effects of other in-progress transaction.</p>

<p>Isolation among multiple transactions can be easily achieved with locks. If a session is reading an item, lock can stop another session from modifying the same item and if a session is modifying an item, lock can stop another session from reading the it. It is simple but very costly for a concurrent application. Lock based applications leads to high contention and low concurrency.</p>

<p>To improve concurrency without too many locks, almost all relation database systems and some NoSQL stores such as HBase, use <em>multi-version concurrency control</em> (MVCC) architectural pattern</p>

<h2 class="section-heading">What is MVCC and how it helps improve concurrency?</h2>

<p>MVCC stands for multi-version concurrency control. Whole idea behind MVCC is to improve concurrency of database system by reducing contention and locks.</p>

<blockquote>Readers shouldn’t block writers and writers shouldn’t block reader. MVCC works towards achieving this goal.</blockquote>

<p>In MVCC model, database systems keep multiple versions of same data. So, rather than overwriting an existing data, database engine marks the existing data obsolete and adds a newer version. Database systems use either timestamp or some sort of change identifier to adopt versioning of data. So, with versioning at place, database system can construct a snapshot view of database any given point in time. And every session sees it’s own snapshot view of database.</p>

<a href="#">
    <img src="{{ site.baseurl }}/img/mvcc.jpg" alt="MVCC Image">
</a>
<span class="caption text-muted">Session 1 and Session 2 are trying to access database field 'item'.</span>

<p>
   <p>Session 1 : update operation starts at time t1</p>
   <p>Session 2 : read operation starts at time t2 (>t1)</p>
   <p>Session 1 creates another revision of ‘item’, however, Session 2 still reads old revision of ‘item’ as ver:2 was created after Session 1 started.</p>
</p>

<h2 class="section-heading">Points to be noted ...</h2>
<p>
<ul type="disc">
<li>No in-place edits of data. Since existing data is never edited, there is no reason to apply a lock. This dramatically improves the performance of database systems.</li>
<li>Versioning system helps to identify latest revision of data easily.</li>
<li>Old versions are pruned offline based on how many old versions need to be maintained for the application to work correctly.</li>
</ul>
</p>
