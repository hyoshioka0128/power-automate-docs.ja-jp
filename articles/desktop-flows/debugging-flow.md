---
title: デスクトップ フローのデバッグ | Microsoft Docs
description: フロー デザイナーのデバッグ オプションを使用してフローをデバッグします。
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
ms.openlocfilehash: 8618768255767ad20ea71127a7390b38a79ce1e8
ms.sourcegitcommit: be18d735934f4094fa8d894e232bd5a1acb31f6a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "4727545"
---
# <a name="debug-a-desktop-flow"></a>デスクトップ フローのデバッグ



システムに変更があった場合、デスクトップ フローにエラーが含まれていて実行できない場合には、フローをデバッグする必要があります。 
<!--note from editor: It would be good to link to the topics about these things. -->

次のツールを使用してデスクトップ フローをデバッグします:
* [エラー ペイン](errors.md)
* [ブレークポイント](#adding-breakpoints)
* [フロー アクションごとに実行する](#run-a-desktop-flow-by-action)
* [実行遅延を設定する](#the-status-bar)

## <a name="run-stop-and-pause-in-flow-designer"></a>フロー デザイナーからの実行、停止、一時停止

**実行** を選択してフローを実行します。 フローを実行すると、**実行** が **一時停止** になります。 フローの実行中に **一時停止** を選択すると、その時点までの変更を一時停止して検査することができます。 フローが一時停止している間に **実行** を選択して再開します。 **次のアクションの実行** ボタンは、アクションごとにフロー アクションを実行し、各アクションが完了した後に一時停止します。 **停止** ボタンはフローを完全に停止します。

![ツールバーの表示](\media\run-stop-pause\toolbar.png)

## <a name="adding-breakpoints"></a>ブレークポイントを追加する

ワークスペースの実行中のオーダー番号の左側をクリックして、赤い点で表示されるフローにブレークポイントを配置します。 ブレークポイントを追加して、フローを一時停止するアクションを指定します。 **実行** または  **次のアクションの実行** を選択して、フローの実行を再開します。 ブレークポイントを選択して削除します。

![ブレークポイントの追加](\media\adding-breakpoints\add-breakpoint.png)

## <a name="run-a-desktop-flow-by-action"></a>アクションを使用してデスクトップ フローを実行する

**次のアクションを実行する** ボタンは、アクションごとにフロー アクションを実行します。 各アクションが完了すると、フローは一時停止します。 変数ペインを開いて、一時停止した時点での変数の値を確認します。 この機能はデバッグに役立ちます。

## <a name="the-status-bar"></a>状態バー

ウィンドウ下部の状態バーには、フローの状態と選択したアクションの数が表示されます。 さらに、現在のフローにおけるアクションとサブフローの合計数を表示します。 実行遅延は、フローデザイナーで各アクションを実行した後にフローが待機する時間を示します。 遅延を選択し、スライダーでミリ秒単位で調整してこの値を変更します。 状態バーには、エラーが存在する場合はエラーの数も表示されます。 [エラー]を選択して、[エラー]ペインをポップ アップします。 **フロー内を検索** を使用すると、結果の数を含む追加の要素を表示します。 検索結果の数を選択して、[コードで検索] ペインをポップアップ表示します。

![ステータス バー](\media\status-bar\status-bar.png)