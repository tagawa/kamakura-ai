---
layout: page
title: ホーム
lang: ja
page_id: home
alt_lang_url: /en/
permalink: /ja/
---
<!-- REPLACE: 2-3 sentence site concept. Placeholder below. -->
このサイトは、鎌倉のAI活用ヒント集です。仕事や暮らしですぐ試せる、流行に左右されにくいコツを集めています。ときどき地元でAIについて話す会も開いています。

<h2>新着ヒント</h2>
<ul class="tip-list">
{% assign tips = site.tips | sort: 'date' | reverse %}
{% for tip in tips limit: 5 %}
  <li><a href="{{ tip.url }}">{{ tip.title_ja }}</a><br>{% for tag in tip.tags %}<span class="tag">{{ tag }}</span>{% endfor %}</li>
{% endfor %}
</ul>

<p><a href="/ja/tips/">ヒント一覧へ</a> ・ <a href="/ja/about/">イベント情報へ</a></p>
