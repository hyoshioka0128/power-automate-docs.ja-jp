---
title: 既知の問題と制限 | Microsoft Docs
description: このセクションでは、Power Automate Desktop プレビューの既知の問題と制限について説明します。
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
ms.openlocfilehash: b0f05c20d420bd4bf2e49e05e53f85b6a641f934
ms.sourcegitcommit: c3eee935e8e8c64963817d2a692a38e8c90400b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "3835126"
---
# <a name="known-issues-and-limitations-with-power-automate-desktop-preview"></a>Power Automate Desktop (プレビュー) の既知の問題と制限

[!INCLUDE [cc-beta-prerelease-disclaimer.md](../../includes/cc-beta-prerelease-disclaimer.md)]

この記事では、Power Automate Desktop (プレビュー) の既知の問題と制限について詳しく説明します。

## <a name="datatables"></a>データテーブル

- **問題**: データテーブル変数のプレビューが [変数] ウィンドウに正しく表示されない場合がある。
- **回避策**: なし。


## <a name="desktop-recorder"></a>デスクトップ レコーダー

- **問題**: デスクトップ レコーダーで一部の SAP UI コントロールがキャプチャされない場合がある。 アプリケーション。
- **回避策**: この SAP アプリケーションを自動化するには、手動アクションを使用します。

- **問題**: 要素の追加時や画像のキャプチャ時に、非表示になるべきコンソールとフロー デザイナーが非表示にならなず、ユーザーの邪魔になることがある。
- **回避策**: なし。

- **問題**: デスクトップ レコーダーで、[スタート] メニュー、システム トレイ、またはデスクトップのショートカットからの一部のステップが記録されない場合がある。 


## <a name="web-recorder"></a>Web レコーダー

- **問題**: 要素の追加や画像のキャプチャを行うと、コンソールとデザイナーが表示され、ユーザーの邪魔になる場合がある。
- **回避策**: UI 要素を追加するとき、またはスクリーンショットをキャプチャするときに、デザイナー ウィンドウとコンソール ウィンドウを最小化する。

- **問題**: 既定では、選択した言語が日本語の場合、Web レコーダーが動作しない。

- **回避策**: ブラウザの変数名をアルファベットのテキストに変更します (例: "Browser1")。 この設定は、Web レコーダーのダイアログの下部にある **詳細設定** オプションで指定できます。

## <a name="loops"></a>ループ
- **問題**: **ループアクション**の構成で、**開始**、**終了**、または**増分** に変数を使用した場合に、有効な数値式を入力した場合でも、*無効な値*メッセージが表示されることがある。 このメッセージが表示されても、アクションが保存され、正常に実行できる場合がある。
- **回避策**: なし。

## <a name="variables"></a>変数
- **問題**: 変数またはイメージの名前を変更すると、名前を変更した変数またはイメージを使用するアクションが予想どおりに機能しなくなることがある。 
- **回避策**: 変数またはイメージを使用するアクションの 1 つを開いて保存すると、問題が解決します。