---
layout: page
title: 公告列表
permalink: /notices/
---


- 可用 `area:`、`status:` 等欄位來篩選（建立多個索引頁，或之後加入前端搜尋）。


{% assign items = site.notices | sort: 'notice_date' | reverse %}
{% for n in items %}
- **{{ n.notice_date | date: "%Y-%m-%d" }}** — [{{ n.title }}]({{ n.url }})
{%- if n.area %}（{{ n.area }}）{% endif -%}
{%- if n.status %} · {{ n.status }}{% endif -%}
{% endfor %}