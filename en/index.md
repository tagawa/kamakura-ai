---
layout: page
title: Home
lang: en
page_id: home
alt_lang_url: /ja/
permalink: /en/
---
<!-- REPLACE: 2-3 sentence site concept (EN). Placeholder below. -->
A collection of practical, evergreen-leaning AI tips from REPLACE-TOWN, Japan, for work and everyday life. We also hold occasional local meetups about how people actually use AI. Japanese is the primary language; tip pages include English where available.

<h2>Latest tips</h2>
<ul class="tip-list">
{% assign tips = site.tips | sort: 'date' | reverse %}
{% for tip in tips limit: 5 %}
  <li><a href="{{ tip.url }}#en">{{ tip.title_en | default: tip.title_ja }}</a><br>{% for tag in tip.tags %}<span class="tag">{{ tag }}</span>{% endfor %}</li>
{% endfor %}
</ul>

<p><a href="/en/tips/">All tips</a> ・ <a href="/en/about/">Events</a></p>
