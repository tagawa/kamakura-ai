---
layout: page
title: AI tips you can try today
description: Practical, evergreen AI tips from Kamakura, Japan, for work and everyday life, plus occasional local meetups.
lang: en
page_id: home
alt_lang_url: /ja/
permalink: /en/
---
Practical AI habits for work and everyday life. Not tool news; only the things that stay useful. No engineering background needed.

{% include next-event-date.html %}
{% if next_event_date %}
<p class="next-event">Next event: <a href="/en/events/">{{ next_event_date | date: '%-m/%-d' }} {{ site.data.next_event.title_en }}</a></p>
{% else %}
<p class="next-event">We hold occasional <a href="/en/events/">hands-on AI work sessions</a> in Kamakura (mainly in Japanese).</p>
{% endif %}

<h2>Latest tips</h2>
<ul class="tip-list">
{% assign tips = site.tips | where_exp: 'tip', 'tip.date <= site.time' | sort: 'date' | reverse %}
{% for tip in tips limit: 5 %}
  {% assign primary = tip.tags | first %}{% assign fam = site.data.tags[primary].group | default: "context" %}<li>{% include icon.html group=fam %}<a class="tip-link" href="{{ tip.url }}#en">{{ tip.title_en | default: tip.title_ja }}</a>
    <span class="tip-lede">{{ tip.description_en }}</span>
    {% for tag in tip.tags %}{% include tag.html tag=tag lang='en' %}{% endfor %}
  </li>
{% endfor %}
</ul>

<p><a href="/en/tips/">All tips</a> · <a href="/en/events/">Events</a></p>
