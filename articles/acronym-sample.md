---
title: アダプティブ カードの頭字語フォームのサンプル | Microsoft Docs
description: 頭字語を収集して Microsoft Dataverse に格納するアダプティブ カードを作成します。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/04/2020
ms.author: deonhe
ms.openlocfilehash: e4ed09619baa29828294d8566b726ef3e6770d61
ms.sourcegitcommit: df7fb20065cfafc153b4bc4019dff2c94f4ef567
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "4553556"
---
# <a name="acronyms-form-sample"></a>頭字語フォームのサンプル

**頭字語フォーム** のサンプルは、頭字語を収集して、Microsoft Dataverse に格納するよう設計されたアダプティブ カードの入力フォームです。 これらの頭字語は、この継続的なデータ収集のため、どこからでも検索することができます。

![頭字語ロガー](media/adaptive-cards/acronym-logger.png)

*入力/出力とメモ*

| 動的トークンの名称 | プレースホルダー テキスト                        | 注意:              |
|--------------------|-----------------------------------------|---------------------|
| {acAcronym}        | 頭字語の省略形を入力する  | 応答の **結果** |
| {acDefinition}     | 上記の頭文字の定義を入力する | 応答の **結果** |

``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Acronym Logger",
            "id": "Title",
            "spacing": "Medium",
            "horizontalAlignment": "Center",
            "size": "ExtraLarge",
            "weight": "Bolder",
            "color": "Accent"
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "TextBlock",
                    "text": "Acronym",
                    "wrap": true,
                    "spacing": "Medium"
                },
                {
                    "type": "Input.Text",
                    "id": "acAcronym",
                    "placeholder": "Enter the abbreviation for the acronym"
                },
                {
                    "type": "TextBlock",
                    "text": "Definition",
                    "wrap": true
                },
                {
                    "type": "Input.Text",
                    "placeholder": "Enter a definition of the acronym above",
                    "id": "acDefinition",
                    "isMultiline": true
                }
            ]
        }
    ],
    "actions": [
        {
            "type": "Action.Submit",
            "title": "Submit",            "id": "btnSubmit"
        }
    ]
}

```
