---
layout: info-page
title: Sitemap
permalink: /sitemap/
---

## Top Level

* [Front Page](/index.html){% for navlink in site.navlinks %}
* [{{ navlink.text }}]({{ site.url }}/{{ navlink.url }}){% endfor %}
* [Tags](/tags)
* [Privacy Policy]({{ site.url }}/privacy/)
* [Sitemap (this page)]({{ site.url }}/sitemap/)
* [Sitemap.xml]({{ site.url }}/sitemap.xml)
* [RSS Feed]({{ site.url }}/feed.xml)
* [robots.txt]({{ site.url }}/robots.txt)

## Blog Posts

| Date | Title | Tags |
|-------|--------|{% for post in site.posts %}
| {{ post.date | date: "%B %e, %Y" }} | [{{ post.title }}]({{ post.url }}) | {% assign tags = post.tags | sort %}{% for tag in tags %}{{ tag }}{% unless forloop.last %}, {% endunless %}{% endfor %} |{% endfor %}

## 404s
