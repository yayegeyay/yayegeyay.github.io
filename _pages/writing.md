---
layout: single
title: "AI Systems Thinking Library"
permalink: /writing/
author_profile: true
classes: wide
---

# Writing

{% for post in site.posts %}
<div style="background: white; border: 1px solid #e9ecef; border-radius: 8px; padding: 1.5rem; margin: 1rem 0; border-left: 4px solid #2C3E50;">
<h3 style="margin-top: 0;"><a href="{{ post.url }}" style="text-decoration: none; color: #333;">{{ post.title }}</a></h3>
<div style="display: flex; justify-content: space-between; align-items: center; margin: 0.5rem 0;">
<span style="color: #666; font-size: 0.9rem;"><strong>Published:</strong> {{ post.date | date: "%B %d, %Y" }}</span>
<span style="background: #e8f4fd; color: #0066cc; padding: 0.2rem 0.8rem; border-radius: 12px; font-size: 0.8rem; font-weight: 500;">🏗️ Architecture Blueprint</span>
</div>
<p style="margin-bottom: 0;">Technical architecture patterns with business implementation frameworks for AI-native transformation.</p>
<a href="{{ post.url }}" style="color: #2C3E50; text-decoration: none; font-weight: 500;">View architecture →</a>
</div>
{% endfor %}

