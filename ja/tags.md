---
layout: page
title: タグ別ヒント
lang: ja
page_id: tags
alt_lang_url: /en/tags/
permalink: /ja/tags/
description: 鎌倉AIのヒントをタグ別に一覧。
---
{% assign all_tags = "" | split: "" %}
{% for tip in site.tips %}{% for t in tip.tags %}{% assign all_tags = all_tags | push: t %}{% endfor %}{% endfor %}
{% assign all_tags = all_tags | uniq | sort %}
{% assign tips_sorted = site.tips | sort: 'date' | reverse %}
{% for tag in all_tags %}
<h2 id="{{ tag }}">{{ site.data.tags[tag] | default: tag }}</h2>
<ul class="tip-list">
{% for tip in tips_sorted %}{% if tip.tags contains tag %}
  <li><a href="{{ tip.url }}">{{ tip.title_ja }}</a></li>
{% endif %}{% endfor %}
</ul>
{% endfor %}