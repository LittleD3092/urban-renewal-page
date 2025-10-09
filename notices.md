---
layout: page
title: 公告列表
permalink: /notices/
---

{%- comment -%}
List all normal pages that live under /notices/ (but not the index itself),
and sort them by the custom `notice_date` field (newest first).
This avoids `where_exp` so it's Liquid 4 / Jekyll 3 compatible.
{%- endcomment -%}

{%- assign pages_all = site.pages | sort: 'notice_date' | reverse -%}

{%- for p in pages_all -%}
  {%- if p.url contains '/notices/' and p.url != '/notices/' -%}
- **{{ p.notice_date | date: "%Y-%m-%d" }}** — [{{ p.title }}]({{ p.url | relative_url }})
  {%- endif -%}
{%- endfor -%}
