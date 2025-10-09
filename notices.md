---
layout: page
title: 公告列表
permalink: /notices/
---

{% assign items = site.notices %}
{% if items == nil %}{% assign items = site.collections.notices.docs %}{% endif %}
{% if items == nil %}{% assign items = "" | split: "," %}{% endif %}
{% assign items = items | sort: 'notice_date' | reverse %}

{% for n in items %}
- **{{ n.notice_date | date: "%Y-%m-%d" }}** — [{{ n.title }}]({{ n.url | relative_url }})
{% endfor %}
