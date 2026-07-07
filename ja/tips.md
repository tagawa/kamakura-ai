---
layout: page
title: AIヒント集
description: すぐ試せるAI活用のコツを新着順に。プロンプトの基本から仕事術・暮らしの活用まで。
lang: ja
page_id: tips
alt_lang_url: /en/tips/
permalink: /ja/tips/
---
すぐ試せるAI活用のコツを、新着順に並べています。

<ul class="tip-list">
{% assign tips = site.tips | sort: 'date' | reverse %}
{% for tip in tips %}
  <li><a href="{{ tip.url }}">{{ tip.title_ja }}</a><br>{% for tag in tip.tags %}<span class="tag">{{ tag }}</span>{% endfor %}</li>
{% endfor %}
</ul>
