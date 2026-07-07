---
layout: page
title: 今日から試せるAIヒント集
description: 鎌倉発、仕事と暮らしで今日から試せる実践AIヒント集。流行に左右されない長く使えるコツと、地元イベントの情報。
lang: ja
page_id: home
alt_lang_url: /en/
permalink: /ja/
---
鎌倉AIは、仕事や暮らしで「今日から試せる」AI活用のヒント集です。流行のツール紹介ではなく、長く使える実践的なコツだけを集めています。ときどき、鎌倉でAIの使い方を持ち寄って話す会も開いています。

<h2>新着ヒント</h2>
<ul class="tip-list">
{% assign tips = site.tips | sort: 'date' | reverse %}
{% for tip in tips limit: 5 %}
  <li><a href="{{ tip.url }}">{{ tip.title_ja }}</a><br>
    {% for tag in tip.tags %}<a class="tag" href="/ja/tags/#{{ tag }}">{{ site.data.tags[tag] | default: tag }}</a>{% endfor %}
  </li>
{% endfor %}
</ul>

<p><a href="/ja/tips/">ヒント一覧へ</a> ・ <a href="/ja/about/">イベント情報へ</a></p>
