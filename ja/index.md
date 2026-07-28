---
layout: page
title: 今日から試せるAI
description: 鎌倉発、仕事と暮らしで今日から試せる実践AIヒント集。流行に左右されない長く使えるコツと、地元イベントの情報。
lang: ja
page_id: home
alt_lang_url: /en/
permalink: /ja/
next_event_date: 2026-07-30
next_event_title: 鎌倉・旅するAI Night
---

仕事や暮らしで使えるAI活用のコツを集めています。流行のツール紹介ではなく、長く使えるものだけ。エンジニアでなくても試せます。

{% assign today_int = site.time | date: '%Y%m%d' | plus: 0 %}
{% assign event_int = page.next_event_date | date: '%Y%m%d' | plus: 0 %}
{% if page.next_event_date and event_int >= today_int %}
<p class="next-event">次回: <a href="/ja/events/">{{ page.next_event_date | date: '%-m/%-d' }} {{ page.next_event_title }}</a></p>
<figure class="event-banner">
  <img src="/assets/events/kamakura-ai-night_banner.webp" width="1196" height="520" alt="鎌倉・旅するAI Night のPR画像。">
</figure>
{% else %}
<p class="next-event">鎌倉でときどき、<a href="/ja/events/">AIを使って手を動かす会</a>を開いています。</p>
{% endif %}

<h2>新着ヒント</h2>
<ul class="tip-list">
{% assign tips = site.tips | where_exp: 'tip', 'tip.date <= site.time' | sort: 'date' | reverse %}
{% for tip in tips limit: 5 %}
  <li><a href="{{ tip.url }}">{{ tip.title_ja }}</a><br>
    {% for tag in tip.tags %}<a class="tag" href="/ja/tags/#{{ tag }}">{{ site.data.tags[tag] | default: tag }}</a>{% endfor %}
  </li>
{% endfor %}
</ul>

<p><a href="/ja/tips/">ヒント一覧へ</a> ・ <a href="/ja/events/">イベント情報へ</a></p>
