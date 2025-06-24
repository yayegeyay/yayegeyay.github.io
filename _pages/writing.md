---
layout: single
title: "Writing & AI Insights"
permalink: /writing/
author_profile: true
---

Below you'll find my latest essays on AI-product strategy, pricing, and hands-on engineering tactics.

{% for post in site.posts %}
* [{{ post.title }}]({{ post.url }}) <span style="color:#888">— {{ post.date | date: "%b %d, %Y" }}</span>
{% endfor %} 