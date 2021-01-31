---
title: Note Application - Use Cases-I
tags:
- noteapplication
comments: true
layout: post
---

Hello everyone,

Today I'm starting to develop a new note application. I hope it helps you this article series. Because I'm going to cover all development processes on simple way.

Let's start by designing  use case diagrams.

Mobile devices are most connected to Internet as you know. That's why we chose mobile users as actor in the  use case diagrams and  there are 6 use cases.

Below shown use case diagram:
![]({{ 'assets/img/noteapp_use_cases.png' | relative_url }})

<br/>

It is wrote user stories to better explain the  user diagram.

<br/>
<hr/>
<br/>


**User Story 1:** Show All Notes <br/>
**Priority:** High <br/>
**Estimate:** 13 <br/>
**Description:** <br/>

 1. Click the note application on mobile phone
 2. Get notes by limit 10 from database
 3. List notes that got in.

**Acceptance Criterias:** <br/>

 1. Listed notes must be clickable.
 2. User can load 10 notes when click "load more" button everytimes.


<br/>
<hr/>
<br/>

Everything is OK for the user story  ? :) Unfortunately NO! Some statements appear unclear. For example; "Get notes by limit 10 from database". How?
You should explain it such that you can't ask the question of HOW.
<br/>

Let's write this row again.


 - Connect the local database by "Room" persistence library provided by Android
 - Get "id", "title", "content", "create date", "update date" values of "NOTES" table for 10 records using Room


That is better than before. We explained better how to do it. But It is not still what we want. 

"List notes that got in". How?

Write the sentence again.


- List "title" and "create date " of each note item.


Now that's allright. 

In last status the user story:

<br/>
<hr/>
<br/>


**User Story 1:** Show All Notes <br/>
**Priority:** High <br/>
**Estimate:** 13 <br/>
**Description:** <br/>

 1. Click the note application on mobile phone
 2. Connect the local database by "Room" persistence library provided by Android
 3. Get "id", "title", "content", "create date", "update date" values of "NOTES" table for 10 records using Room
 4. List "title" and "create date " of each note item.

**Acceptance Criterias:** <br/>

 1. Show the notes as "title" and "create date" by limit 10 records.
 1. Listed notes must be clickable but when clicked, no action for now.
 2. User can load 10 notes when click "load more" button everytimes.


<br/>
<hr/>
<br/>

I hope this article was usefull. 

See you.
