---
layout: page
title: AI Tips
description: Practical AI tips, newest first. Prompting basics, work habits, and everyday uses.
lang: en
page_id: tips
alt_lang_url: /ja/tips/
permalink: /en/tips/
---
Practical AI tips, newest first. Links jump to the English section of each tip.

<ul class="tip-list">
{% assign tips = site.tips | where_exp: 'tip', 'tip.date <= site.time' | sort: 'date' | reverse %}
{% for tip in tips %}
  <li><a href="{{ tip.url }}#en">{{ tip.title_en | default: tip.title_ja }}</a><br>{% for tag in tip.tags %}<span class="tag">{{ tag }}</span>{% endfor %}</li>
{% endfor %}
</ul>
