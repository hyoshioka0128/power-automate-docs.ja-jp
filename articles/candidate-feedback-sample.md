---
title: 応募者のフィードバックのサンプル | Microsoft Docs
description: このサンプルを使用して、アダプティブ カードを作成して仕事の応募者のフィードバックを収集します。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/01/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8d2cbaa54d4256484bf8d17693e30aec85f2a4df
ms.sourcegitcommit: 89fca599830de21709b47087302a030d91e5fe29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "3549730"
---
# <a name="candidate-feedback-sample"></a>応募者のフィードバックのサンプル

**応募者のフィードバック フォーム**のサンプルは、面接のループ中にフィードバックを収集する目的で設計されたアダプティブ カードの入力フォームです。 チーム内の誰もが面接のループ中に候補者にフィードバックを提供できるよう、共有されたインスタント フローボタンと共にこれを使用することを推奨します。 データベースやその他の希望するデータソースに回答を記録することで、これを拡張し、これらの追加の営業案件に対応します。

-   その応募者との次のセッションの前にフォローアップ提案をレビューを容易にします。
-   すべての応答が記録された後の集計データのレビューを容易にします。
-   プロセスの最後に、採用/不採用の投票数を人事担当者に通知する

     ![応募者のフィードバック フォーム](media/adaptive-cards/candidate-form.png)

*入力/出力とメモ*

| 動的トークンの名称 | プレースホルダー テキスト | 注意:              |
|--------------------|------------------|---------------------|
| {acFullName}       | {acFullName}     | テキストの表示        |
| {acComments}       | {acComments}     | テキストの表示        |
| {acDecision}       |                  | 応答の**結果** |
| {acFollowUp}       |                  | 応答の**結果** |

``` json
{
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.0",
  "body": [
    {
      "type": "TextBlock",
      "size": "Medium",
      "weight": "Bolder",
      "id": "Title",
      "text": "CANDIDATE FEEDBACK FORM",
      "horizontalAlignment": "Left"
    },
    {
      "type": "Input.Text",
      "placeholder": "{acFullName}",
      "style": "text",
      "isMultiline": false,
      "maxLength": 75,
      "id": "acFullName"
    },
    {
      "type": "Input.Text",
      "placeholder": "{acComments}",
      "style": "text",
      "isMultiline": true,
      "maxLength": 200,
      "id": "acComments"
    },
    {
      "type": "TextBlock",
      "size": "Medium",
      "weight": "Bolder",
      "text": "Decision",
      "horizontalAlignment": "Left",
      "separator": true
    },
    {
      "type": "Input.ChoiceSet",
      "id": "acDecision",
      "value": "1",
      "choices": [
        {
          "title": "Hire",
          "value": "Hire"
        },
        {
          "title": "No Hire",
          "value": "No Hire"
        }
      ],
      "style": "expanded"
    },
    {
      "type": "TextBlock",
      "text": "Suggest follow-up discussion regarding:",
      "weight": "Bolder"
    },
    {
      "type": "Input.ChoiceSet",
      "id": "acFollowUp",
      "isMultiSelect": true,
      "value": "",
      "choices": [
        {
          "title": "Past experience in the topic area",
          "value": "Experience"
        },
        {
          "title": "Inclusive behaviors and work ethics",
          "value": "Inclusivity"
        },
        {
          "title": "Ability to work without supervision",
          "value": "Independent"
        }
      ]
    }
  ],
  "actions": [
    {
      "type": "Action.Submit",
      "title": "Submit"
    }
  ]
}
```


