---
date: "2021-02-11"
description:
  アジャイルとドメイン駆動設計(DDD)の原則を使用した軽量な技術のセットで、
  チームがソフトウェアシステムの近代化を開始するのに十分な計画を立てるのに役立ちます
resources:
  - name: cover
    src: images/swift.png
lastmod: "2021-03-04"
length: エンドツーエンドで行う場合は2〜4日
participants: ビジネスステークホルダー、アーキテクト、技術リード、開発者
tags:
  - Kickoff
  - Discovery
  - Framing
  - Modernization
title: Swift Method
what:
  - 付箋矢印フラグ
  - ホワイトボードテープ - 黒、緑、赤；各2ロール
  - ハサミ
  - スコッチテープ
  - ドライイレース表面(3フィート×2フィート)
  - スーパースティッキー4x6マルチカラー付箋、4パック
when:
  - 反復的な方法でアプリケーション近代化イニシアチブをジャンプスタートします。これは、現在のビジネス機能を迅速にレビューし、「あるべき」アーキテクチャを計画できる短いコンサルティングエンゲージメントである[App Navigator](https://tanzu.vmware.com/application-modernization)のコア方法です。私たちの専門家は、アーキテクチャ、境界、リスクまたは懸念のポイントを発見し、次に現在の状態から将来の状態への移行方向をマッピングするためにSwift Methodを実践します。
why:
  - ビジネスリーダーと技術実践者を整列させます。このアプローチを使用してシステムのシステムを分解し、システムが「振る舞いたい」方法と将来の目標をマッピングする概念的なアーキテクチャ計画を開発します。私たちはこれが重要なシステム近代化に特に重要であることを発見しました。- 開発チームを編成する方法について決定を通知し、ビジネスと技術の両方の観点から作業を優先順位付けます。また、現状と望ましい状態の間のパスを定義する「キャッチオール」方法としても役立ちます。
---

## この方法の使い方

{{% section %}}

### サンプルアジェンダとプロンプト

1. ビジネスと技術の人々が理解する言語を使用して、システムを[Event Storm](/practices/event-storming/)します。

1. システム内の機能間の関係をモデル化する[Boris](/practices/boris/)演習を実施します。Borisの間にリアルタイムで特定された技術機能を文書化するSNAPを実施します。

   ![SNAP analysis](images/snap.jpg)

1. 近代化の薄いスライスを特定します。

   薄いスライスは短いドメインイベントフローです。垂直スライスは、コアドメインの短いドメインイベントフローを選択し、[Boris](/practices/boris/)から出てくるサービスを活用してそれらのイベントを生成することによって特定されます。それらをそれらのイベントを生成するために必要なアーキテクチャコンポーネントと考えてください。薄いスライスは、[Event Storming](/practices/event-storming/)、[Boris](/practices/boris/)、SNAP活動によって通知されます。

   {{% callout %}}
   **ヒント**: 垂直スライスはアーキテクチャのすべての層に触れますが、機能のスライバーのみを実装します。たとえば、垂直スライス「ユーザーがパスワードでログインできるようにする」は、ユーザーインターフェイスにユーザー名とパスワードフィールドを追加し、サーバー側のロジックを実装し、データベースレコードの最終ログインフィールドを更新する可能性があります。垂直にスライスすることは、アジャイルに新しいチームにとって最も難しいマインドシフトの1つです。なぜなら、開発者があまり馴染みのないアプリの領域と相互作用する必要があるためです。
   {{% /callout %}}

1. ビジネス価値、技術的リスク、努力のバランスを目指して、薄いスライスを優先順位付けします。目標は、システムを「振る舞いたい」方法に向けてシステムを段階的に移動させることです。各連続するスライスの実装により、この目標にさらに近づきます。

1. 薄いスライスは、バックログでMVP(Minimum Viable Products)またはストーリーのコレクションとしてキャプチャされると実行可能になります。一部のケースでは、Pivotal/Tanzu Labsは顧客チームと提携して、ビジネス価値、技術的リスク、努力のバランスを目指して薄いスライスを特定して優先順位付けします。
   {{% callout %}}
   **ヒント**: システムに適したMVPを決定するには、これらのドメインが相互作用する薄い垂直エンドツーエンドスライスを考慮する必要があります。MVPは、[「モノリスを絞殺する」](https://tanzu.vmware.com/content/blog/strangling-a-monolith-by-focusing-on-roi)ことと、新しいドメインとサービスと相互作用するための戦術的パターンを活用することからのパスをマッピングします。
   {{% /callout %}}

1. スライスを定義するときに、<a href="https://docs.microsoft.com/en-us/azure/architecture/patterns/anti-corruption-layer" target="_blank">anti-corruption layer</a>、<a href="https://en.wikipedia.org/wiki/Facade_pattern" target="_blank">Facade</a>、<a href="https://www.swiftbird.us/docket-choreography" target="_blank">Docket Based Choreography</a>、<a href="https://martinfowler.com/bliki/StranglerFigApplication.html" target="_blank">Strangler</a>などの戦術的実装パターンを活用して、新しいまたは絞殺されたサービスが古いレガシーシステムと共存できるようにします

1. **_目標_**(プラクティスは近日公開) / OKRに結びついた優先順位付けされたユーザーストーリーのバックログを作成します。ユーザーストーリーをMVPまたはリリースにマップします。

   {{% callout %}}
   **ヒント**: ユーザーストーリーインパクトマッピングは、ストーリーをMVPとリリースにマッピングするために適用できる技術です。ユーザーストーリーマッピングとDDDを組み合わせる方法を説明する<a href="https://blog.eriksen.com.br/en/mapping-domain-knowledge" target="_blank">ブログ投稿</a>があります。
   {{% /callout %}}

1. 実地実験、フィードバック、反復的な進捗を開始します。
   {{% /section %}}

{{% section %}}

### 成功/期待される成果

- 現在のシステム機能を迅速に発見し、望ましいターゲットアーキテクチャを作成し、基礎となる懸念領域を特定し、優先順位付けに同意する
- 概念的なソリューション、戦術的な修正、潜在的なトレードオフについて議論して理解し、段階的で測定された方法でフレーミングされる
- 仮定を検証/無効化し、ソリューション/修正を通知するのに役立つアーキテクチャ作業
- サービスを段階的に近代化するアプローチを開発する
- 「すべてをテーブルに」アプローチを使用して関連するビジネス成果を持つソリューションの定義
- 小さく始まり、スケールし、顧客の開発者とアーキテクトが自信を持って前進できるようにする戦術的ステップの計画。
  {{% /section %}}

{{% section %}}

### ファシリテーターのメモとヒント

優れたファシリテーターは、DDDの観点からビジネス機能をサポートすることに基づいて、システムをどのように設計すべきかを引き出すことができるはずです。

この概念的なアーキテクチャは、システムの良い最初のカット方向を表しています。既存のシステムを近代化するためのツールとして使用される場合、[Boris](/practices/boris/)は可能性のあるターゲットアーキテクチャを明らかにします。Swift Methodの他の活動は、現在の状態から近代化された状態への移行方法を定義するのに役立ちます。
{{% /section %}}

{{% section %}}

### 関連プラクティス

Swift Methodには多くの活動が含まれています：

- [Event Storming](/practices/event-storming/)
- [Boris](/practices/boris/)
  {{% /section %}}

{{% section %}}

### 実例

Uber Eatsスタイルのアプリケーションの[Boris](/practices/boris/)とSwift Method近代化の詳細な説明については、<a href="https://miro.com/app/board/o9J_kzaSk0E=/" target="_blank">Event StormingとBorisトレーニングMiroボード</a>を参照してください

![Visual of the Swift Method's various steps and how they flow into one another](images/example-1.png)
{{% /section %}}

{{% section %}}

### 推奨文献

<a href="https://tanzu.vmware.com/content/white-papers/tackle-application-modernization-in-days-and-weeks-not-months-and-years" target="_blank">Tackle Application Modernization in Days and Weeks, Not Months and Years</a> (white paper)

<a href="https://www.youtube.com/watch?v=7-fRtd8LUwA" target="_blank">Swift Method: Event Storming, Boris the Spider and Other Techniques</a> (YouTube video) talk at ExploreDDD 2019 by Shaun Anderson

<a href="https://www.youtube.com/watch?v=s5qeE4qii6M" target="_blank">A Deep Dive into Modernization Patterns to Get Your Mission Critical Applications to the Cloud</a> (YouTube video)

<a href="https://tanzu.vmware.com/content/slides/the-modern-family-modernizing-applications-to-pivotal-cloud-foundry-getting-out-of-the-big-ball-of-mud" target="_blank">Tools to Slay the Fire Breathing Monoliths in Your Enterprise</a> (blog post)

<a href="https://www.eventstorming.com/" target="_blank">EventStorming.com</a> (website)
{{% /section %}}
