---
title: Microsoft Teams にアダプティブ カードを投稿するフローの作成方法を理解する | Microsoft Docs
description: アダプティブ カードを使用して、充実したフォーマットのされたコンテンツを Microsoft Teams に投稿するフローの作成方法について説明します。
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 7e35e4dac38b8aaa7b33c4407465b0d857375850
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4708368"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Microsoft Teams でアダプティブ カードを使用する


[アダプティブ カード](https://adaptivecards.io) を Microsoft Teams チャネルに投稿するフローを作成できます。 アダプティブ カードを使用すると、豊富な書式設定を使用して、投稿をわかりやすく、対話型で、魅力的なものにすることができます。 アダプティブ カードには、画像、グラフ、美しく書式設定されたテキストなどのコンポーネントを含めることができます。

## <a name="create-a-cloud-flow-that-posts-adaptive-cards-to-a-team"></a>アダプティブ カードをチームに投稿するクラウド フローを作成する

次の手順に従って、戦略と計画チームの一般チャネルにアダプティブ カードを投稿するクラウド フローを作成します。 作成するフローでは、**独自のアダプティブ カードをフロー ボットとしてチャネルに投稿する (プレビュー)** アクションを使用して、アダプティブ カードのコンテンツをチームのチャネルに毎週投稿します。

1. Microsoft Teams にサインインします。
1. 左側のナビゲーション バーで **Teams** アイコンを選択し、**戦略と計画** チームを選択します。

    ![チームの選択](media/create-adaptive-cards-teams/select-teams-team.png)

1. 画面の上部にある **フロー** タブを選択します。
1. **+** (一から作成) アイコンを選択します。
1. **繰り返し** を検索し、**繰り返し** トリガーを選択します。

    ![繰り返しカード](media/create-adaptive-cards-teams/select-recurrence.png)

1. 次のように、毎週、選択したタイム ゾーンで繰り返すようにスケジュールを設定します。
    
    ![繰り返しカード](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. **新しいステップ** を選択します。
1. **アダプティブ** を検索し、 **Microsoft Teams** を選択します。続いて **独自のアダプティブ カードをフローのボットとしてチャネルに投稿する (プレビュー) アクション** を選択します。

   ![アダプティブ カード](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. **独自のアダプティブ カードをフロー ボットとしてチャネルに投稿する (プレビュー)** カードで、**チーム**、**チャネル**、**メッセージ** を指定して、アダプティブ カードの **メッセージ** の投稿先になるチームとチャネルを示します。

   ![アダプティブ カード](media/create-adaptive-cards-teams/adaptive-card-message.png)

   このサンプル JSON コンテンツは、**メッセージ** に使用できます。

    ````
        {
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "speak": "Our team meeting is starting soon. Do you want to snooze  or do you want to send a late notification to the attendees?",
    "body": [
        {
        "type": "TextBlock",
        "text": "Strategy and Planning Weekly Team meeting",
        "size": "large",
        "weight": "bolder"
        },
        {
        "type": "TextBlock",
        "text": "Conf Room 112/3377 (10)",
        "isSubtle": true
        },
        {
        "type": "TextBlock",
        "text": "12:30 PM - 1:30 PM",
        "isSubtle": true,
        "spacing": "none"
        },
        {
        "type": "TextBlock",
        "text": "Snooze for"
        },
        {
        "type": "Input.ChoiceSet",
        "id": "snooze",
        "style": "compact",
        "value": "5",
        "choices": [
            {
            "title": "5 minutes",
            "value": "5",
            "isSelected": true
            },
            {
            "title": "15 minutes",
            "value": "15"
            },
            {
            "title": "30 minutes",
            "value": "30"
            }
        ]
        }
    ],
    "actions": [
        {
        "type": "Action.Submit",
        "title": "Snooze",
        "data": {
            "x": "snooze"
        }
        },
        {
        "type": "Action.Submit",
        "title": "I'll be late",
        "data": {
            "x": "late"
        }
        }
    ]
    }
    ````


1. フローに名前を付けて保存します。


## <a name="run-the-flow"></a>フローを実行します

繰り返し時間が経過すると、フローによってアダプティブ カードのコンテンツが定義したチーム チャネルに投稿されることに注意してください。

![フローを実行します](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>詳細情報を見る

- [アダプティブ カードのサンプル](https://adaptivecards.io/samples/) の使用を開始する。
- 簡単な方法で[アダプティブ カードのコンテンツ](https://adaptivecards.io) を作成する。



