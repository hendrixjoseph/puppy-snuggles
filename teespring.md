---
layout: default
permalink: /tshirts/
---

<style>h2{ text-align: center; } .entry img{ max-width: 500px; }</style>

{% for tee in site.data.teespring %}
## [{{ tee.title }}]({{ tee.link }})
{% include twitter-facebook-share.html url=tee.link text=tee.title width="100%" %}
[![{{ tee.title }}]({{ tee.image }} "{{ tee.title }}")]({{ tee.link }})
{% endfor %}
