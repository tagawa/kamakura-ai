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
  {% assign primary = tip.tags | first %}{% assign fam = site.data.tags[primary].group | default: "context" %}<li>{% include icon.html group=fam %}<a class="tip-link" href="{{ tip.url }}#en">{{ tip.title_en | default: tip.title_ja }}</a>
    <span class="tip-lede">{{ tip.description_en }}</span>
    {% for tag in tip.tags %}{% include tag.html tag=tag lang='en' %}{% endfor %}
  </li>
{% endfor %}
</ul>
