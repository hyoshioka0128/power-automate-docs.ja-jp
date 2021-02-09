---
title: アダプティブ カードの日単位の天気予報サンプル | Microsoft Docs
description: Teams チャネルに毎日の天気の更新情報を投稿するためのアダプティブ カード作成用サンプル
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
ms.openlocfilehash: dbd495918eabbdc8014ee755c3c03a4fc74e034d
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709063"
---
# <a name="daily-weather-report-sample"></a>日単位の天気予報のサンプル

**日単位の天気予報** サンプルは、Teams チャネルに日単位の天気の更新情報を投稿するための、MSN 天気予報で使用するために設計されたアダプティブ カードです。

![天気のサンプル](media/adaptive-cards/weather.png)

*入力/出力とメモ*

| 動的トークンの名称     | プレースホルダー テキスト | メモ                                                                          |
|------------------------|------------------|--------------------------------------------------------------------------------|
| {acCityState}          | テンプレートを参照     | テキストの表示 <br>  変数は、市区町村、都道府県、または郵便番号の値を保持するために使用できる                                                                   |
| {acDailySummary}       | テンプレートを参照     | テキストの表示                                                                   |
| {acCurrentDateTime}    | テンプレートを参照     | テキストの表示                                                                   |
| {acUrlConditionsImage} | テンプレートを参照     | テキストの表示  <br> テンプレートのコメントを参照。有効な URL に置き換える必要があります。                                                                 |
| {acCurrentTemperature} | テンプレートを参照     | テキストの表示                                                                   |
| {actempHi}             | テンプレートを参照     | テキストの表示                                                                   |
| {actempLow}            | テンプレートを参照     | テキストの表示                                                                   |


``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "{acCity}, {acState}",
            "size": "Large",
            "isSubtle": true
        },
        {
            "type": "TextBlock",
            "text": "{acCurrentDateTime}",
            "spacing": "None"
        },
        {
            "type": "TextBlock",
            "text": "{acDailySummary}",
            "spacing": "None"
        },
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "width": "auto",
                    "items": [
                        {
                            "type": "Image",
                            "url": "{acUrlConditionsImage}",
                            "size": "Large"
                        }
                    ]
                },
                {
                    "type": "Column",
                    "width": "auto",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "{acCurrentTemperature}",
                            "size": "ExtraLarge",
                            "spacing": "None"
                        }
                    ]
                },
                {
                    "type": "Column",
                    "width": "stretch",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "°F",
                            "weight": "Bolder",
                            "spacing": "Small"
                        }
                    ]
                },
                {
                    "type": "Column",
                    "width": "stretch",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Hi {actempHi}",
                            "horizontalAlignment": "Left"
                        },
                        {
                            "type": "TextBlock",
                            "text": "Lo {actempLow}",
                            "horizontalAlignment": "Left",
                            "spacing": "None"
                        }
                    ]
                }
            ]
        }
    ]
}
```
