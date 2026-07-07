---
layout: page
title: AI tips you can try today
description: Practical, evergreen AI tips from Kamakura, Japan, for work and everyday life, plus occasional local meetups.
lang: en
page_id: home
alt_lang_url: /ja/
permalink: /en/
---
Kamakura AI is a collection of practical AI tips you can try today, for work and everyday life. No hype and no tool-of-the-week coverage, just techniques that stay useful as tools change. We also hold occasional meetups in Kamakura where locals share how they actually use AI (mainly in Japanese).

<h2>Latest tips</h2>
<ul class="tip-list">
{% assign tips = site.tips | sort: 'date' | reverse %}
{% for tip in tips limit: 5 %}
  <li><a href="{{ tip.url }}#en">{{ tip.title_en | default: tip.title_ja }}</a><br>
    {% for tag in tip.tags %}<a class="tag" href="/en/tags/#{{ tag }}">{{ tag }}</a>{% endfor %}
  </li>
{% endfor %}
</ul>

<p><a href="/en/tips/">All tips</a> ・ <a href="/en/about/">Events</a></p>
