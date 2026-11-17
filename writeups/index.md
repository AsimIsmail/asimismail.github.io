---
layout: page
title: Write-ups
permalink: /writeups/
---

# TryHackMe Write-ups

Documenting my hands-on cybersecurity journey.

{% for post in site.categories.Writeups %}
- [{{ post.title }}]({{ post.url }})
{% endfor %}
