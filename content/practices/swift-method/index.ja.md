---
date: "2021-02-11"
description:
  アジャイルとDomain Driven Design(DDD)の原則を使用した
  一連の軽量技術で、チームがソフトウェアシステムの近代化を開始するのに十分な計画を立てるのに役立ちます
resources:
  - name: cover
    src: images/swift.png
lastmod: "2021-03-04"
length: エンドツーエンドで実行する場合は2〜4日
participants: ビジネスステークホルダー、アーキテクト、テクニカルリード、開発者
tags:
  - Kickoff
  - Discovery
  - Framing
  - Modernization
title: Swift Method
what:
  - 粘着性のある矢印フラグ
  - ホワイトボードテープ - 黒、緑、赤；各2ロール
  - はさみ
  - スコッチテープ
  - ドライイレース表面(3フィート x 2フィート)
  - スーパースティッキー4x6マルチカラー付箋、4パック
when:
  - 反復的な方法でアプリケーション近代化イニシアチブを開始します。これは[App Navigator](https://tanzu.vmware.com/application-modernization)のコアメソッドであり、現在のビジネス機能を迅速にレビューし、「将来の」アーキテクチャを計画する短いコンサルティングエンゲージメントになる可能性があります。私たちの専門家はSwift Methodを実践して、アーキテクチャ、境界、リスクまたは懸念のポイントを発見し、現在の状態から将来の状態への方向をマップします。
why:
  - ビジネスリーダーと技術実務者を整列させます。このアプローチを使用して、システムのシステムを分解し、システムが「動作したい」方法で将来の目標をマップする概念的なアーキテクチャ計画を開発します。私たちは、これが重要なシステムの近代化に特に重要であることを発見しました。- 開発チームを編成する方法、およびビジネスと技術の両方の観点から作業を優先順位付けする方法についての決定を通知します。また、現状と望ましい状態の間のパスを定義する「包括的な」方法としても役立ちます。
---

## この方法の使い方

{{% section %}}

### サンプルアジェンダとプロンプト

1. ビジネスと技術の人々が理解する言語を使用して、システムを[Event Storm](/practices/event-storming/)します。

1. システムの機能間の関係をモデル化する[Boris](/practices/boris/)演習を実施します。Borisが識別した技術的機能をリアルタイムで文書化するSNAPを実施します。

   ![SNAP analysis](images/snap.jpg)

1. 近代化の薄いスライスを特定します。

   薄いスライスは短いドメインイベントフローです。垂直スライスは、コアドメインの短いドメインイベントフローを選択し、[Boris](/practices/boris/)から出てくるサービスを活用してそれらのイベントを生成することで識別されます。それらをそれらのイベントを生成するために必要なアーキテクチャコンポーネントと考えてください。薄いスライスは、[Event Storming](/practices/event-storming/)、[Boris](/practices/boris/)、およびSNAP活動によって通知されます。

   {{% callout %}}
   **ヒント**: 垂直スライスは、アーキテクチャのすべての層に触れますが、機能のスライバーのみを実装します。たとえば、垂直スライス「ユーザーがパスワードでログインできるようにする」は、ユーザーインターフェイスにユーザー名とパスワードフィールドを追加し、サーバー側のロジックを実装し、データベースレコードの最後のログインフィールドを更新する可能性があります。垂直にスライスすることは、アジャイルに新しいチームにとって行う最も困難なマインドシフトの1つです。なぜなら、開発者がなじみのないアプリの領域と対話する必要があるからです。
   {{% /callout %}}

1. ビジネス価値、技術的リスク、労力のバランスを取ることに目を向けて、薄いスライスを優先順位付けします。目標は、システムを「動作したい」方法に向けて段階的に移動することです。各連続するスライスの実装により、この目標に近づきます。

1. 薄いスライスは、MVP(Minimum Viable Products)またはストーリーのコレクションとしてバックログにキャプチャされると実行可能になります。場合によっては、Pivotal/Tanzu Labsは、ビジネス価値、技術的リスク、労力のバランスを取ることに目を向けて、薄いスライスを特定および優先順位付けするために顧客チームと提携します。
   {{% callout %}}
   **ヒント**: システムに適切なMVPを決定するには、これらのドメインが互いに相互作用する薄い垂直エンドツーエンドスライスを考慮する必要があります。MVPは、[「モノリスを絞殺する」](https://tanzu.vmware.com/content/blog/strangling-a-monolith-by-focusing-on-roi)からのパスをマップし、新しいドメインとサービスと相互作用するための戦術的パターンを活用します。
   {{% /callout %}}

1. スライスを定義するときに、<a href="https://docs.microsoft.com/en-us/azure/architecture/patterns/anti-corruption-layer" target="_blank">腐敗防止層</a>、<a href="https://en.wikipedia.org/wiki/Facade_pattern" target="_blank">Facade</a>、<a href="https://www.swiftbird.us/docket-choreography" target="_blank">Docket Based Choreography</a>、および<a href="https://martinfowler.com/bliki/StranglerFigApplication.html" target="_blank">Strangler</a>のような戦術的実装パターンを活用して、新しいまたは絞殺されたサービスが古いレガシーシステムと共存できるようにします

1. **_目標_**(プラクティスは近日公開予定)/ OKRに結びついた優先順位付けされたユーザーストーリーのバックログを作成します。ユーザーストーリーをMVPまたはリリースにマップします。

   {{% callout %}}
   **ヒント**: ユーザーストーリーインパクトマッピングは、ストーリーをMVPとリリースにマッピングするために適用できる技術です。これは、User Story MappingをDDDと組み合わせる方法を説明する<a href="https://blog.eriksen.com.br/en/mapping-domain-knowledge" target="_blank">ブログ投稿</a>です。
   {{% /callout %}}

1. 実践的な実験、フィードバック、反復的な進捗を開始します。
   {{% /section %}}

{{% section %}}

### 成功/期待される成果

- 現在のシステム機能を迅速に発見し、意欲的なターゲットアーキテクチャを作成し、根本的な懸念領域を特定し、優先順位付けに同意する
- 概念的なソリューション、戦術的修正、潜在的なトレードオフを議論して理解し、段階的で測定可能な方法でフレーミングする
- 仮定を検証/無効化し、ソリューション/修正を通知するのに役立つアーキテクチャ作業
- サービスを段階的に近代化するアプローチを開発
- 「テーブルにすべてを置く」アプローチを使用して、関連するビジネス成果を持つソリューションの定義
- 小さく始まり、スケールし、顧客の開発者とアーキテクトが自信を持って前進できるようにする戦術的ステップの計画。
  {{% /section %}}

{{% section %}}

### ファシリテーターのメモとヒント

優れたファシリテーターは、DDD視点からビジネス機能をサポートすることに基づいて、システムをどのように設計すべきかを引き出すことができるはずです。

この概念的なアーキテクチャは、システムの良い最初のカット方向を表しています。既存のシステムを近代化するためのツールとして使用する場合、[Boris](/practices/boris/)は可能性の高いターゲットアーキテクチャを明らかにします。Swift Methodの他の活動は、現在の状態から近代化された状態への移行方法を定義するのに役立ちます。
{{% /section %}}

{{% section %}}

### 関連プラクティス

Swift Methodには、次のような多くの活動が含まれています：

- [Event Storming](/practices/event-storming/)
- [Boris](/practices/boris/)
  {{% /section %}}

{{% section %}}

### 実例

Uber Eatsスタイルのアプリケーションの[Boris](/practices/boris/)とSwift Method of modernizationの詳細な説明については、<a href="https://miro.com/app/board/o9J_kzaSk0E=/" target="_blank">Event StormingとBoris Training Miroボード</a>を参照してください

![Visual of the Swift Method's various steps and how they flow into one another](images/example-1.png)
{{% /section %}}

{{% section %}}

### 推奨文献

<a href="https://tanzu.vmware.com/content/white-papers/tackle-application-modernization-in-days-and-weeks-not-months-and-years" target="_blank">Tackle Application Modernization in Days and Weeks, Not Months and Years</a> (ホワイトペーパー)

<a href="https://www.youtube.com/watch?v=7-fRtd8LUwA" target="_blank">Swift Method: Event Storming, Boris the Spider and Other Techniques</a> (YouTubeビデオ) ExploreDDD 2019でのShaun Andersonによるトーク

<a href="https://www.youtube.com/watch?v=s5qeE4qii6M" target="_blank">A Deep Dive into Modernization Patterns to Get Your Mission Critical Applications to the Cloud</a> (YouTubeビデオ)

<a href="https://tanzu.vmware.com/content/slides/the-modern-family-modernizing-applications-to-pivotal-cloud-foundry-getting-out-of-the-big-ball-of-mud" target="_blank">Tools to Slay the Fire Breathing Monoliths in Your Enterprise</a> (ブログ投稿)

<a href="https://www.eventstorming.com/" target="_blank">EventStorming.com</a> (ウェブサイト)
{{% /section %}}
