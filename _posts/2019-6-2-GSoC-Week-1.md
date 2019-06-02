---
layout: post
title: GSoC Project Overview & Week 1
---

## Overview:
Here's a quick rundown on my project for this summer:

The Debian Patch Porting System aims to systematize and partially automate the security patch porting process.

The number of security vulnerability identifiers is quite large- these are relevant to specific distributions, organizations and applications. Each organization handles security vulnerabilities that are relevant to them in their own way. MITRE's vulnerability identifier called Common Vulnerabilities and Exposures (CVE) is global, and most advisories are somehow related to a CVE.

The purpose of the system is to unify all these algorithmically for easy patch finding, management and application. The system would be able to take any vulnerability as input and extract patches w/r/t that vulnerability. Patches can be collected by employing certain patch finding methods. Some of these methods are to crawl sites, trackers, and various distributions' respositories. Along with that, general purpose information about that vulnerability and its equivalent identifiers for other organizations could also be collected to get the vulnerability's complete profile. This profile could then be stored in a NoSQL database.

Following this, the system would then test whether the patches are applicable for the upstream source that they are for. Patching heuristics can be employed to test the patch's applicability in the source package. Some of these heuristics are fuzzing, patching w/r/t offsets, etc.

The nature of the system is to be generic enough so that it can fit in with Debian (maybe allow use with the [Debian Security Tracker](https://security-tracker.debian.org)), or act independently as well.


## GSoC:
The focus in this GSoC would be to design a flexible crawler i.e. a patch finder. The patch finder would primarily find patches for a given vulnerability, and optionally a given source package. Implementing the patch finder would require a modular implementation of certain patch finding methods, which would be based extensively on web crawling. A very simple example of this is to extract patches from fixed versions of a Debian package, as these are mostly in the debian/patches folder.

My mentors for this project are Luciano Bello and László Böszörményi (GCS). Luciano started this project in 2017 and implemented it, but due to its limited scope, he felt re-doing what has been done with a broader vision in mind was called for. You can find his and his team's work [here](https://github.com/patchPorting).

Prior to this week was the Community Bonding Period. Most of that time was spent in discussion about the ins and outs of the system, its scope, ultimate goal, and design. We also decided on how and when conference conversations should take place, mainly on Hangouts.

GSoC's coding period commenced on 27th May 2019. Due to my university examinations till 3rd June 2019, I found putting in the required 40 hours for the first week a bit difficult, so I chose a task that would require minimal effort and could be completed in under week. I decided on setting up the base of the implementation, mostly classes that would be used in the input and output of the patch finder, and then tested these. I won't go into implementation specific details as there's not much to talk about yet code-wise. You can check out the code and follow our progress in the [GitHub repository](https://github.com/jajajasalu2/patch-finder). As our prime language, we've chosen Python3.

Feel free to contact me on the address in the footer. 
