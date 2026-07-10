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
{% assign tips = site.tips | where_exp: 'tip', 'tip.date <= site.time' | sort: 'date' | reverse %}
{% for tip in tips %}
  <li><a href="{{ tip.url }}">{{ tip.title_ja }}</a><br>
    {% for tag in tip.tags %}<a class="tag" href="/ja/tags/#{{ tag }}">{{ site.data.tags[tag] | default: tag }}</a>{% endfor %}
  </li>
{% endfor %}
</ul>
