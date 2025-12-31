---
title: "Postmortem"
linkTitle: "Postmortem"
description: "製品またはユーザーに影響を与えるインシデントから学ぶための演習。SREコミュニティでは、この演習はインシデント振り返りと呼ばれます。"
tags: ["Delivery"]
length: "1時間"
participants: "コアデリバリーチーム、ステークホルダー、サポートチーム"
lastmod: "2021-07-28"
date: "2021-07-28"
why:
  - Postmortemsは、否定的なインシデントの再発を減らすのに役立ちます
when:
  - チームがインシデントまたはニアミスについて学ぶべきことがあることに同意したとき
  - インシデント中またはそれが解決された直後、セッションがインシデントの解決を妨げない限り
  - ステークホルダーまたは別のチーム(例：サポートチーム)がpostmortemセッションを要求したとき

what:
  - ホワイトボードまたは[Miro](https://miro.com/)のようなデジタル版
  - 付箋
  - マスキングテープ
  - マーカー

remote: false
miro_template_url: ""
---

## この方法の使い方

まず、インシデントを定義しましょう：

- ライブ製品のイベントで、ユーザーの製品との相互作用を中断するもの
- 開発プロセスに大きな影響を与える予期しない否定的なイベント
- [エラーバジェット](https://cloud.google.com/blog/products/management-tools/sre-error-budgets-and-maintenance-windows)違反

### サンプルアジェンダとプロンプト

1. **セッション前に**、インシデントについてできるだけ多くの情報を収集します。たとえば、関連するチームに情報を要求するアンケートを送信する場合があります。チームが進行中にインシデントについてメモを取った場合は、これらも収集します。

   さらに、セッション前にタイムラインを作成し、postmortemセッション中にそれを検証することが役立ちます。

   タイムラインの例：

   ![Postmortem Timeline](images/timeline.jpg)

   postmortemセッションに適切な人々を招待してください。例えば：

   - コアチーム：プロダクトマネージャー、エンジニア、デザイナー
   - 関連する当事者、インシデントに関与している主要な役割を持つ人。例えば：
     - プラットフォームチームのメンバー
     - セキュリティチームのメンバー

1. **postmortemの目標を説明します(5分)**

   次のように言うかもしれません：

   > 「最近のインシデントの原因は何でしたか？どのように修正しましたか？さらに、これを将来回避するためのアクションアイテムを定義し、postmortem文書に文書化したいと思います。誰かを責める人を見つけようとしているわけではありません。」

   {{< callout >}}
   **ヒント**: 何が起こったか、そして将来それを回避する方法を特定したいので、非難のない文化を受け入れてください。各チームメンバーに心理的安全性を提供してください。
   {{< /callout >}}

1. **インシデントタイムラインを提示します(5分)**

   インシデントタイムラインを表示し、チームと確認します。

1. **Postmortemトピックのブレインストーミング(5分)**

   チームに付箋またはデジタルワークスペースに書いてもらいます：

   - What went wrong - 最近のインシデントの原因は何でしたか？
   - What went well - インシデントを修正するためにうまくいったことは何ですか？
   - Where we got lucky - 私たちを助けてくれたイベント/ものはありますか？

1. **クイックトピッククラスタリング(5分)**

   チームに、類似のトピックに基づいて付箋をクラスター化するように依頼します。

1. **各クラスターについて議論します(20分)**

   各クラスターが議論されるのに十分な時間を許可します。特定のクラスターが追加の時間を必要とする場合は、その特定のトピックについてのフォローアップセッションを検討してください。

   さらに、「what went wrong」列のクラスターについては、「なぜこれが起こったのですか？」と「再び起こった場合、どのように影響を減らすことができますか？」と尋ねます。

   {{< callout >}}
   **ヒント**: [「五つのなぜ」メソッド](https://en.wikipedia.org/wiki/Five_whys)の使用を検討してください。繰り返しますが、個人の責任ではなく、プロセスによる根本原因に焦点を当ててください。  
   {{< /callout >}}

1. **アクションアイテムについて議論します(15分)**

   インシデントを解決し、将来それを回避するために取ることができるアクションについてチームと議論します。これらのアクションの所有者を定義します。

1. **postmortem所有者に同意します(4分)**

   チームとしてpostmortem所有者を決定します。その責任は次のとおりです：

   - 将来の参照のためのpostmortem文書を作成します。次のものが含まれます：
     - インシデントの概要
     - インシデントを解決するためのアクションアイテム
     - [根本原因分析](https://asq.org/quality-resources/root-cause-analysis)
     - インシデントが将来発生するのを回避するための学習と次のステップ
   - postmortemの状態についてステークホルダーと通信します
   - postmortemミーティングのすべてのアクションアイテムが完了していることを確認するためのレビューミーティングを計画します

1. **フォローアップをスケジュールします(1分)**

   アクションをレビューするためのフォローアップpostmortemセッションについてチームと合意します。チームがすべてのpostmortemアクションを完了するまで、インシデントをクローズしないでください。

## 成功/期待される成果

この演習の終わりに、チームはインシデントが何であり、どのように発生したかについて明確な整列を持ちます。さらに、チームはインシデントの再発を防止または影響を減らすための一連の計画を持ちます。

## ファシリテーターのメモとヒント

postmortem文書の例：

- Googleからのpostmortemの例：[Shakespeare Sonnet++ Postmortem](https://sre.google/sre-book/example-postmortem/)
- [@dastergon](https://github.com/dastergon)からの[Postmortem Templates](https://github.com/dastergon/postmortem-templates)
- [@danluu](https://github.com/danluu)からの["A List of Post-mortems!"](https://github.com/danluu/post-mortems)
- [GoogleのGitHubからの「sredocs」](https://github.com/google/sredocs)

## 推奨文献

[Atlassian Incident management](https://www.atlassian.com/incident-management)

[Google Postmortem culture](https://sre.google/sre-book/postmortem-culture/)

Book: Life of a production system incident (coming soon!)
