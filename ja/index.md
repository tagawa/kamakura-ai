---
layout: page
title: 今日から試せるAI
description: 鎌倉発、仕事と暮らしで今日から試せる実践AIヒント集。流行に左右されない長く使えるコツと、地元イベントの情報。
lang: ja
page_id: home
alt_lang_url: /en/
permalink: /ja/
---

仕事や暮らしで使えるAI活用のコツを集めています。流行のツール紹介ではなく、長く使えるものだけ。エンジニアでなくても試せます。

{% include next-event-date.html %}
{% if next_event_date %}
<p class="next-event">次回: <a href="/ja/events/">{{ next_event_date | date: '%-m/%-d' }} {{ site.data.next_event.title_ja }}</a></p>
<figure class="event-banner">
  <img src="/assets/events/kamakura-ai-night_banner2.webp" width="1240" height="539" alt="AIに取り組む時間@鎌倉 のPR画像。">
</figure>
{% else %}
<p class="next-event">鎌倉でときどき、<a href="/ja/events/">AIを使って手を動かす会</a>を開いています。</p>
{% endif %}

<h2>新着ヒント</h2>
<ul class="tip-list">
{% assign tips = site.tips | where_exp: 'tip', 'tip.date <= site.time' | sort: 'date' | reverse %}
{% for tip in tips limit: 5 %}
  {% assign primary = tip.tags | first %}{% assign fam = site.data.tags[primary].group | default: "context" %}<li>{% include icon.html group=fam %}<a class="tip-link" href="{{ tip.url }}">{{ tip.title_ja }}</a>
    <span class="tip-lede">{{ tip.description_ja }}</span>
    {% for tag in tip.tags %}{% include tag.html tag=tag lang='ja' %}{% endfor %}
  </li>
{% endfor %}
</ul>

<p><a href="/ja/tips/">ヒント一覧へ</a> ・ <a href="/ja/events/">イベント情報へ</a></p>
