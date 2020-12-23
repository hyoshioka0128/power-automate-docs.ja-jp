---
title: デスクトップの自動化 | Microsoft Docs
description: デスクトップ オートメーション
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
ms.openlocfilehash: a50e30b27c81555069fc2c44e04b3359bf340df2
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711656"
---
# <a name="automate-desktop-flows"></a>デスクトップ フローを自動化する



フローデザイナーには、**UI 自動化** グループが含まれており、Windows アプリケーションや要素の入力やデータ抽出を行うアクションを実行できます。

**Windows** サブカテゴリのアクションは UI ウィンドウ全体を直接操作し、**フォームの記入** アクションはテキスト フィールドやボタンなどの特定の要素を操作します。

デスクトップの自動化は、必要なアクションを手動で追加する、またはデスクトップ レコーダーを使用して実行することができます。

## <a name="interacting-with-desktop-applications"></a>デスクトップ アプリケーションとのやり取り

UI の自動化は、リポジトリ内のウィンドウと要素のみに対し、任意の UI アプリケーション インターフェイス上で実行することができます。

UI のアクションを構成するには、やり取りをするエレメントを入力します:

![ウィンドウ アクションのボタン押下](./media/ui-automation/press-button-in-window-action.png)

既存の UI 要素はリポジトリから追加することができますが、新しいものはアクションのプロパティから直接追加することもできます:

![UI アクションから新しい要素を追加する](./media/ui-automation/adding-new-elements-through-a-ui-action.png)

新しい要素を追加するには、ハイライトして、**Ctrl キーを押しながら左クリック** します:

![新しい UI 要素のキャプチャ](./media/ui-automation/capturing-new-ui-elements.png)

必要な要素をすべて追加した後は、**完了** を選択して レポジトリに保存します。

UI ウィンドウからタイトル、場所、サイズなどのデータの一部を抽出するには、**ウィンドウの詳細を取得する** アクションを使用します:

![ウィンドウ アクションの詳細を取得する](./media/ui-automation/get-details-of-window-action.png)

また、ウィンドウ内の特定の要素からデータを抽出するには、**ウィンドウの UI 要素の詳細を取得する** アクションを使用します:

![ウィンドウ アクションで UI 要素の詳細を取得する](./media/ui-automation/get-details-of-a-ui-element-in-window.png)

[アクションの参照](actions-reference/uiautomation.md)で利用可能な UI 自動化アクションのリストが表示されます。
