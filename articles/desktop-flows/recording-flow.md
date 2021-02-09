---
title: デスクトップ フローにおける記録 | Microsoft Docs
description: デスクトップ フローにおける記録
author: rokontol
ms.service: flow
ms.topic: article
ms.date: 09/22/2020
ms.author: rokontol
ms.reviewer: rokontol
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d0d58fcf31fa5e2d46d6c05e450b0949bc21d34c
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711641"
---
# <a name="record-flows-in-power-automate-desktop"></a>Power Automate Desktop でフローを記録する



デスクトップ レコーダーを使用して、自動化するタスクを実行するだけでフローを設計できます。

## <a name="desktop-recorder"></a>デスクトップ レコーダー
フロー デザイナーで、ツールバーの **デスクトップ レコーダー** を選択してデスクトップアクションを記録します:

![デスクトップ レコーダー ボタン](./media/recording-flow/desktop-recorder-button.png)

デスクトップ レコーダー ウィンドウで **記録開始** を選択し、アクションを記録します。

![記録開始ボタン](./media/recording-flow/start-recording-button.png)

デスクトップ レコーダーは、UI の要素に関連するマウスとキーボードのアクティビティを追跡し、それぞれのアクションを個別に記録します。

![デスクトップ フローの記録](./media/recording-flow/recording-flow.png)

 **録音の一時停止** を選択してアクションの記録を一時停止します:
 
![記録の一次停止開始ボタン](./media/recording-flow/pause-recording-button.png)
 
 **+** を選択して記録したアクションにコメントを追加します:

![コメント ボタン](./media/recording-flow/comment-button.png)

### <a name="known-issues-and-limitations"></a>既知の問題と制限事項

- **問題**: 要素の追加時や画像のキャプチャ時に、非表示になるべきコンソールとフロー デザイナーが非表示にならなず、ユーザーの邪魔になることがある。

- **回避策**: なし。

- **問題**: デスクトップ レコーダーで、[スタート メニュー]、システム トレイからの一部のステップが記録されない場合がある。

- **回避策**: なし。

 ## <a name="web-recorder"></a>Web レコーダー

フロー デザイナーで、ツールバーの **Web レコーダー** を選択して web に関連するアクションを記録します:

![Web レコーダー ボタン](./media/recording-flow/web-recorder-button.png)

アクティビティを記録する Web ブラウザーを選択します。またオプションで既に開いているブラウザーのインスタンスを選択して、次に添付します:

![記録するブラウザの選択](./media/recording-flow/select-browser-for-recording.png)

レコーダーは、Web ブラウザ内での活動を記録し、一連の Web アクションを生成します:

![Web フローの記録](./media/recording-flow/recording-web-flow.png)

デスクトップレコーダーと同様に、**+** ボタンからコメントを追加することができます。また、右上のボタンをを使用して記録の一時停止、再開、リセットをすることができます。

### <a name="known-issues-and-limitations"></a>既知の問題と制限事項

- **問題**: 要素の追加や画像のキャプチャを行うと、コンソールとデザイナーが表示され、ユーザーの邪魔になる場合がある。


- **回避策**: なし。

 ## <a name="recording-vs-building-a-desktop-flow"></a>記録 vs デスクトップ フローの構築

レコーダを使用して作成されたアクションは、記録の終了後に手動で編集できます。 すでに開発中のデスクトップ フローでレコーダーを使用して、記録されたステップをレコーダーに追加します。

> [!NOTE]
> レコーダを使用して、フローのバックボーンを作成します。 単純なタスクの中には、すでに編集が必要ないものもありますが、ほとんどの記録されたタスクは、修正を加えることで最適な結果を得ることができます。 条件やループなど、特定の種類のアクションは記録できません。 また、削除をした方がよい記録には、冗長なアクションが含まれている場合もあります。