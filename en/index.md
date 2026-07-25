---
layout: page
title: AI tips you can try today
description: Practical, evergreen AI tips from Kamakura, Japan, for work and everyday life, plus occasional local meetups.
lang: en
page_id: home
alt_lang_url: /ja/
permalink: /en/
# next_event_date: 2026-07-30
# next_event_title: Kamakura AI Night
---
Kamakura AI is a collection of practical AI tips you can try today, for work and everyday life. No hype and no tool-of-the-week coverage, just techniques that stay useful as tools change. We also hold occasional meetups in Kamakura where locals share how they actually use AI (mainly in Japanese).

{% assign today_int = site.time | date: '%Y%m%d' | plus: 0 %}
{% assign event_int = page.next_event_date | date: '%Y%m%d' | plus: 0 %}
{% if page.next_event_date and event_int >= today_int %}
<p class="next-event">Next event: <a href="/en/events/">{{ page.next_event_date | date: '%-m/%-d' }} {{ page.next_event_title }}</a></p>
{% endif %}

<h2>Latest tips</h2>
<ul class="tip-list">
{% assign tips = site.tips | where_exp: 'tip', 'tip.date <= site.time' | sort: 'date' | reverse %}
{% for tip in tips limit: 5 %}
  <li><a href="{{ tip.url }}#en">{{ tip.title_en | default: tip.title_ja }}</a><br>
    {% for tag in tip.tags %}<a class="tag" href="/en/tags/#{{ tag }}">{{ tag }}</a>{% endfor %}
  </li>
{% endfor %}
</ul>

<p><a href="/en/tips/">All tips</a> ・ <a href="/en/about/">Events</a></p>
