---
layout: post
title: My OSCP Attempt
---

### Introduction:

Last year when COVID was all the rage I decided to sign up for the OSCP. It's a pentesting exam where you hack 5 machines in under 24 hours.

### Motivation:

2020 was hell for a lot of people. People died and got laid off. Job offers got revoked. It was a scary year with a lot of uncertainty.

Around June 2020, I'd wrapped up a software engineering internship, following which I didn't have much of anything on my plate. The OSCP seemed like a good thing to pursue, as it would keep me busy for the next few months and I'd learn about pentesting/security, something I'd wanted to learn for quite a while. Plus it could potentially be helpful in finding me a job post-graduation, with the job market at the time seeming all too bleak.

### The Exam:

The night before I bought three cans of 350 ml redbulls. They came in handy, a lot. I'd booked the exam for 8:30 AM the next day.
Following is the timeline of that day. I took a _lot_ of breaks in between, so those continuous stretches of time you see are marked by me meandering around the house a lot:

**8:00 AM:**: Boot up Windows and my Kali VM on it.

**8:30 AM:** OffSec sends me a mail with proctoring instructions; log onto the proctoring platform. A bit of troubleshooting as requested by the proctor. Got the lab invite and off we go.

**9:00 AM - 11:00 AM:** I spent two hours just getting a lay of the land. Launched all my autorecons and nmaps within these two hours, tried to understand the nature of each machine from the outside.

**11:00 AM - 1:00 PM:** Cracked my first machine, a 20-pointer. I was familiar with the exploit needed for the foothold, and luckily enough I was also familiar with the privesc tactic. This machine was kind of a breeze and pure dumb luck, but it had only just begun.

**1:00 PM - 5:00 PM:** Okay, so my initial plan was to crack both the 25-pointers, one 20-pointer, get those 70 points and call it a day. So I got to cracking the 25-pointer w/o the buffer overflow. This machine kicked my metaphorical ass so, so hard. I panicked. Thought I'll do another 20-pointer on the side in case I screw up the 25-pointer. And that kicked my metaphorical ass too. More panic.

**5:00 PM - 6:00 PM:** Around this time, I thought I'd just do the buffer overflow as I was running out of time and had only 20 points in the basket. I whipped open youtube, saw a few buffer overflow videos, and did a hack-along. Suprisingly, I was able to crack it in under 30 minutes. I had 45 points now, so the panic slightly subsided.

**6:00 PM - 9:00 PM:** Did absolutely nothing. Downed a redbull.

**9:00 PM - 11:00 PM:** Tried my hand at the 10-pointer. I'd tried to get this one done initially during the first few hours of the exam but couldn't. Tried again this time and got it. 55 points.
Also tried to crack the other 25-pointer a bit, and I did get a little far but no dice.

**11:00 PM - 1:00 AM:** Downed another redbull. Got to working on the other 20-pointer, which I'd failed at before. It seemed impenetrable at first, but then, out of nowhere it appeared. The foothold vector. And I finally got in.

**1:00 AM - 2:00 AM:** Downed another redbull. Got to working on root for the 20-pointer. After a _lot_ of googling and re-reading scans, I got it. And that was 75 points in the basket. I'd passed.

**2:00 AM - 3:00 AM:** A lot of meandering around, a lot of basking in victory. I spent a few minutes verifying if I had all the screenshots I needed, every command down to the T. 4/5 machines and 75 points. I was dead tired and ended the exam.

### Resources:

If you've read a lot of these blog posts, then you're probably familiar with these resources, but in case you're not here you go. This is everything I used to prepare for the exam:

- [Hack the Box](https://hackthebox.eu). This is the only platform I used to practice, other than the OffSec labs.
- [Cyber Mentor's youtube series on Buffer Overflow](https://www.youtube.com/watch?v=qSnPayW6F7U).
- Use [this](https://github.com/noraj/OSCP-Exam-Report-Template-Markdown) amazing report format if you're proficient in markdown and the terminal. It looks clean and gets your report ready in a short amount of time.
- [My own notes for buffer overflow.](https://github.com/jajajasalu2/BOF/blob/master/bof.md). They're pretty disorganized, but maybe they're useful to you.

### Personal notes:

Personally I'm not a fan of stacking up certifications without applying any of the knowledge you get from those certifications. Like in software engineering, getting a certification for a programming language but never applying any of that knowledge to an actual project or problem. All you're left with is remembering a bunch of syntax and how to code a fibonacci sequence.

The OSCP is different in that way. It's a certification that forces you to apply your knowledge on problems, multiple times too. _Way_ too many times. You attempt to solve problems that you don't readily find answers for on the internet. All you can do is gather as much information as you can and attempt to piece the puzzle. This was in stark contrast to my (limited) software engineering experience, where any problem you have could potentially be answered by a stack overflow search or reading the docs.

I had a lot of fun hacking and breaking things for the past few months, and I look forward to doing more of it in the future.
