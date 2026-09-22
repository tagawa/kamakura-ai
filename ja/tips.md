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
  {% assign primary = tip.tags | first %}{% assign fam = site.data.tags[primary].group | default: "context" %}<li>{% include icon.html group=fam %}<a class="tip-link" href="{{ tip.url }}">{{ tip.title_ja }}</a>
    <span class="tip-lede">{{ tip.description_ja }}</span>
    {% for tag in tip.tags %}{% include tag.html tag=tag lang='ja' %}{% endfor %}
  </li>
{% endfor %}
</ul>
