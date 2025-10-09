---
layout: page
title: 公告列表
permalink: /notices/
---

{% comment %}
List all regular pages under /notices/ (sorted by custom notice_date if present).
{% endcomment %}

{% assign pages = site.pages | where_exp: "p", "p.url contains '/notices/' and p.url != '/notices/'" %}

{% assign items = pages | sort: "notice_date" | reverse %}

{% for n in items %}
- **{{ n.notice_date | date: "%Y-%m-%d" }}** — [{{ n.title }}]({{ n.url | relative_url }})
{% endfor %}
