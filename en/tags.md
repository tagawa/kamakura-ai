---
layout: page
title: Tips by tag
lang: en
page_id: tags
alt_lang_url: /ja/tags/
permalink: /en/tags/
description: Kamakura AI tips grouped by tag.
---
{% assign all_tags = "" | split: "" %}
{% assign published_tips = site.tips | where_exp: 'tip', 'tip.date <= site.time' %}
{% for tip in published_tips %}{% for t in tip.tags %}{% assign all_tags = all_tags | push: t %}{% endfor %}{% endfor %}
{% assign all_tags = all_tags | uniq | sort %}
{% assign tips_sorted = published_tips | sort: 'date' | reverse %}
{% for tag in all_tags %}
<h2 id="{{ tag }}">{{ tag }}</h2>
<ul class="tip-list">
{% for tip in tips_sorted %}{% if tip.tags contains tag %}
  <li><a href="{{ tip.url }}#en">{{ tip.title_en | default: tip.title_ja }}</a></li>
{% endif %}{% endfor %}
</ul>
{% endfor %}