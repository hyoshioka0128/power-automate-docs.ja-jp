---
title: Power Automate Desktop の既知の問題と制限 | Microsoft Docs
description: この記事では、Power Automate Desktop の既知の問題と制限について説明します。
author: olegmelnykov
ms.service: flow
ms.topic: article
ms.date: 09/22/2020
ms.author: olmelnyk
ms.reviewer: olmelnyk
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3ccb79a64ab89b652a041372ffb79fbeee04856f
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711668"
---
# <a name="known-issues-and-limitations-with-power-automate-desktop"></a>Power Automate Desktop の既知の問題と制限 



この記事では、Power Automate Desktop の既知の問題と制限について詳しく説明します。

## <a name="datatables"></a>データ テーブル

- **問題**: データテーブル変数のプレビューが [変数] ウィンドウに正しく表示されない場合がある。

    **回避策**: なし。


## <a name="desktop-recorder"></a>デスクトップ レコーダー

- **問題**: 要素の追加時や画像のキャプチャ時に、非表示になるべきコンソールとフロー デザイナーが非表示にならなず、ユーザーの邪魔になることがある。

    **回避策**: なし。

- **問題**: デスクトップ レコーダーで、[スタート メニュー]、システム トレイからの一部のステップが記録されない場合がある。 

    **回避策**: なし。

## <a name="web-recorder"></a>Web レコーダー

- **問題**: 要素の追加や画像のキャプチャを行うと、コンソールとデザイナーが表示され、ユーザーの邪魔になる場合がある。

    **回避策**: UI 要素を追加するとき、またはスクリーンショットをキャプチャするときに、デザイナー ウィンドウとコンソール ウィンドウを最小化する。

## <a name="loops"></a>ループ

- **問題**: **ループアクション** の構成で、**開始**、**終了**、または **増分** に変数を使用した場合に、有効な数値式を入力した場合でも、*無効な値* メッセージが表示されることがある。 このメッセージが表示されても、アクションが保存され、正常に実行できる場合がある。

    **回避策**: なし。

## <a name="variables"></a>変数

- **問題**: 変数またはイメージの名前を変更すると、名前を変更した変数またはイメージを使用するアクションが予想どおりに機能しなくなることがある。 
    
    **回避策**: 変数またはイメージを使用するアクションの 1 つを開いて保存すると、問題が解決します。

## <a name="microsoft-excel"></a>Microsoft Excel

- **問題** : 数値比較で null 値を持つ Microsoft Excel セルが使用されている場合、エラーメッセージが表示されずにフローが予期せずに終了する場合があります。
    
    **回避策** : 各数値の比較の前に、0 (ゼロ) で null 値を持つセルを埋めます。

