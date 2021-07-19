---
layout: post
title: About Browser Security
date: 2021-07-19
categories: tech, hacking, security
---

# Browser Security Sandbox

Reference: [What is a Browser Security Sandbox?! (Learn to Hack Firefox)](https://youtu.be/StQ_6juJlZY)

## What is a sandbox?

A process can do anything... basically your code can do anything

Similarily a vulnerability in the browser means that the attacker can do anything during the process

However the architecture changed over the years

Simply put, there is a parent process which is the browser window and the overall browser and a content process which can be the tab that reners the actual webpage.

Thus, for the content process, the javascript and html etc. files don't need the powerful ability to perform some activities.

Therefore, now the content process was stripped from its power. Hence being 'sandboxed'

Basically now content process can read html, render page, execute javascript that makes website fancier

The implementations for these sandboxes differ by the OS.

In theorey, it is great but practically it is hard to implement properly.

### Inter Process Communication (IPC)

IPC is basically a communication between two processes. In this case, the sandboxed process, the content process sends requests to the parent process to perform actions otherwise restricted.

Thus with this implementation, it is hard for attackers to simply attack with a content process vulnerability.

Now they need to find another vulnerability in the parent process for a complete exploitation.

### Problems

The problem still arises in the fact that the page already contains sensitive and perhaps critical information accessible by the attacker.

This problem was dealt by the fission process. In the fission process, the content process (the tab) is not a single process. Now, every single web page is a process. Thus, exploiting a single ad or single page doesn't help the attacker get into the main tab or webpage.

## Full Exploit

Now for firefox, a full exploit requires:
 - renderer vulnerability
 - sandbox vulnerability

 And the above two tasks are separated. Thus, with a team, one part can look for JS vulnerability and the other for browser security.

 Mozilla considers sandbox escape a high impact vulnerability ($8,000 ~ $10,000)


# Attack Methods

1. OS sandbox feature
2. IPC layer
3. Logic bugs (from IPC)
	- Settings page in firefox and chrome is written in JS, HTML
