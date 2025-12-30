---
title: "2x2 優先順位付け"
linkTitle: "2x2 優先順位付け"
description: "2つの対照的な基準に対してオプションの優先順位を付け、現在最も重要なオプションを特定します。"
# Note: remove any tags that are not relevant.
tags:
  [
    "Scoping",
    "Kickoff",
    "Discovery",
    "Framing",
    "Inception",
    "Transition",
    "Modernization",
    "Delivery",
  ]
length: "1時間以上"
participants: "コアチーム、ステークホルダー、専門家"
# custom "cover" image example: "boris/boris.png"
image: "2x2/2x2-populated.png"
lastmod: "2021-06-15"
why:
  - チーム内で共通の理解と合意を構築することで、最適な進め方をより簡単に決定できるようになります。
when:
  - 複数のオプションが提示され、チームが最も重要な項目を決定する必要がある際に、進め方について意見が対立している場合。
what:
  - "ホワイトボードまたは[Miro](https://miro.com/)のようなデジタル版"
  - ドライイレースマーカー
  - 付箋
  - マーカー
  - マスキングテープ

# If this practice or workshop has a Miro template: remote: true
remote: true
miro_template_url: "https://miro.com/templates/2x2-prioritization-matrix/"
---

## この方法の使い方

{{% section %}}

### サンプルアジェンダとプロンプト

1. 準備：グループとして、2つの関連する優先順位付け基準に合意します。

   {{< callout >}}**例**：影響 vs. 実現可能性、価値 vs. 複雑さ、リスク vs. 緩和の容易さ{{< /callout >}}

1. 2つの垂直に交差する軸を作成し、選択した基準の1つで各軸にラベルを付けます。

   ![空の2x2グリッド](images/2x2-empty.png)

   {{< callout >}}
   **ヒント**：右上の象限が最も重要/最優先を表すように軸にラベルを付けます。これは、このプラクティスを繰り返し使用する際に役立つ慣例です。
   {{< /callout >}}

1. ランダムにオプションを選択し、中央付近に配置します。

1. 別のオプションを選択し、グループとして、グリッド上の他のオプションに対して、垂直方向と水平方向に相対的に配置します。

   {{< callout >}}
   **ヒント**：2つのオプションを同じ行または列に配置しないでください。曖昧さを避けるために、各オプションは各軸上で明確に一意な水平位置と垂直位置に配置する必要があります。
   {{< /callout >}}

1. すべてのオプションがグリッドに配置されるまで、ステップ4を繰り返します。最優先のオプションは右上の象限にあるはずです。

   {{< callout >}}
   **ヒント**：オプションが特定の半分または象限に偏っている場合、各軸の両側にほぼ半分ずつ配置されるようにオプションを再配置できます。これにより曖昧さがなくなり、優先順位の決定が容易になります。
   {{< /callout >}}

   ![入力済みの2x2グリッド](images/2x2-populated.png)

{{% /section %}}

{{% section %}}

### 成功/期待される成果

グループが焦点を当てるオプション（または複数のオプション）を決定したら、完了です。
{{% /section %}}

{{% section %}}

### ファシリテーターのメモとヒント

- 右上の象限に優先ソリューションが多すぎる場合は、その象限内で軸を再描画して、ソリューションをさらに分離します。軸は絶対的なものではなく相対的なものであるため、これが可能であることを覚えておいてください。管理可能な状態になるまで調整を続けてください。

  ![再描画された2x2軸グリッド](images/2x2-regrid.png)

- オプションが多すぎると、このプラクティスはより困難で時間がかかるようになります。20以上のアイテムがある場合は、選択した基準に関連性のないオプションを削除することを検討してください。
  選択した優先順位付け基準に対して評価できる人を参加させます（例：デザイナーはユーザビリティについて、エンジニアは技術的な複雑さについて話すべきです）。
- X/Y軸の前に2x2のプロンプトを開発します。軸がプロンプトに共鳴しない場合、グループは配置と焦点に苦労するでしょう。
- XおよびY軸の修飾子を選択する際は、以下を考慮してください：
  - Y軸にはあまり議論の余地のない修飾子を選択してください。より強いyes/noステートメントを持つ修飾子は、初期配置に役立ち、グループがアイテムを失格にする（X軸より下に配置する）際の議論を減らすことができます。
  - X軸に沿って議論が起こることを望むので、議論の余地がより多い修飾子を選択してください。
    {{% /section %}}

{{% section %}}

## 関連プラクティス

[Insight Prioritization](/practices/insight-prioritization/)

[Problem Prioritization](/practices/problem-prioritization/)

[Solution Prioritization](/practices/solution-prioritization/)
{{% /section %}}

{{% section %}}

## 実例

![頻度と強度で問題をプロットした2x2チャート](/practices/problem-prioritization/images/example-2.jpg)

![2x2チャートが描かれたホワイトボードの前で優先順位について話し合うグループ](/practices/problem-prioritization/images/example-3.jpg)

![優先順位付けられた上位の問題がある2x2チャート](/practices/problem-prioritization/images/example-5.jpg)

![優先順位付けられたソリューションのデジタル2x2](/practices/solution-prioritization/images/example-6.jpg)
{{% /section %}}

{{% section %}}

## 推奨文献

[ProductPlanの2×2 Prioritization Matrix](https://www.productplan.com/glossary/2x2-prioritization-matrix/)
{{% /section %}}
