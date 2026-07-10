---
title_ja: "AIに直させる前に、元のコピーを残す"
title_en: "Save a copy before letting AI change your work"
description_ja: "AIに文書や表を直させて元に戻せなくなる事態を防ぐため、大きな修正の前にコピーを残す方法。"
description_en: "How to avoid unrecoverable AI edits by saving a dated copy of your document before any large rewrite."
tags: [workflow, safety]
date: 2026-06-24
source: "adapted from version-control practice"
---
**状況**: 文書や表をAIに手直しさせたら、頼んでいない部分まで壊れて、元に戻せなくなった。

**やったこと**: 大きな書き換えや「修正」を頼む前に、日付入りのコピーを保存する(ファイル複製、シートのタブ複製で十分)。結果が悪ければ、プロンプトで元に戻そうとせず、コピーを開き直して、より狭い依頼でやり直す。

**結果・ポイント**: プログラマーがAIに触らせる前に保存(コミット)するのと同じ発想。失敗のコストが数時間から数秒に変わる。「戻せる」と分かっていれば大胆に試せる。

<!--en-->
**Situation**: You let AI "fix" a document or spreadsheet and it broke parts you never asked it to touch, with no way back.

**What to do**: Before any substantial rewrite, save a dated copy (duplicate the file or sheet tab; that's enough). If the result is worse, don't prompt your way back; reopen the copy and retry with a narrower request.

**Result / key point**: Same idea as programmers committing before AI touches code. A failed edit costs seconds instead of hours, and knowing you can revert lets you experiment boldly.
