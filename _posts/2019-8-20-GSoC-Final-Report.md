---
layout: post
title: GSoC Final Report
---

## Introduction:

The Debian Patch Porting System aims to systematize and partially automate the security patch porting process.

In this Google Summer of Code (2019), I wrote a webcrawler to extract security patches for a given security vulnerability identifier. This webcrawler or patch-finder serves as the first step of the Debian Patch Porting System.

The Patch-finder should recognize numerous vulnerability identifiers. These identifiers can be security advisories (DSA, GLSA, RHSA), vulnerability identifiers (OVAL, CVE), etc. So far, it can identify CVE, DSA (Debian Security Advisory), GLSA (Gentoo Linux Security Advisory) and RHSA (Red Hat Security Advisory).

Each vulnerability identifier has a list of entrypoint URLs associated with it. These URLs are used to initiate the patch finding.

Vulnerabilities that are not CVEs are generic vulnerabilities. If a generic vulnerability is given, its "aliases" (i.e. CVEs that are related to the generic vulnerability) are determined. This method was chosen because CVEs are quite possibly the most widely used security vulnerability and thus would have the most number of patches associated to them. Once the aliases are determined, the entrypoint URLs of the aliases are crawled for the patch-finding.

The Patch-finder is based on the web crawling and scraping framework [Scrapy](https://github.com/scrapy/scrapy).

## What was done:

During these three months, I have:

- Used Scrapy to implement a spider to collect patch links.
- Implemented a recursive patch-finding process. Any links that the patch-finder finds on a page (in a certain area of interest, of course) that are not patch links are followed.
- Implemented a crawler to extract patches from Debian Packages.
- Implemented a crawler to extract patches from a given GitHub repository.

Here's a link to the [patch-finder's Github Repository](https://github.com/PatchPorting/patch-finder) which I have used for GSoC.

## TODO:

There is a lot more stuff to be done, from solving small bugs to implementing major features. Some of these issues are on the project's GitHub issue tracker [here](https://github.com/PatchPorting/patch-finder/issues). Following is a summary of these issues and a few more ideas:

- A way to uniquely identify patches. This is so that the same patches are not scraped and collected.
- A Database, and a corresponding database API.
- Store patches in the database, along with any other information.
- Collect not only patches but other information relevant to the vulnerability.
- Integrate the Github crawler/parser in the crawling process.
- A way to check the relevancy of the patch to the vulnerability. A naive solution is, of course, to simply check for mention of the vulnerability ID in the patch description.
- Efficient page filters. Certain links should not be crawled because it is obvious they will not yield any patches, for example homepages.
- A better way to scrape links, rather than using a URL's corresponding xpath.
- A more efficient testing framework.
- More crawlers/parsers.

## Personal Notes:

Google Summer of Code has been a super comfortable and fun experience for me. I've learnt tonnes about Python, Open Source and Software Development. My mentors [Luciano Bello](https://github.com/1ucian0) and [László Böszörményi](https://github.com/gcsideal) have been immensely helpful and have guided me through these three months.

I plan to continue working on this project and hopefully develop it to a state where Debian and everyone who needs it can use it conveniently.
