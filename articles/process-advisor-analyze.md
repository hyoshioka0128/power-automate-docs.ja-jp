---
title: プロセスの分析 | Microsoft Docs
description: Process Advisor のプロセス分析機能の使用方法。
services: ''
suite: flow
documentationcenter: na
author: nijemcevic
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2020
ms.author: tatn
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 255ddfa397af28dda4ca6db8d11a9dcb5944983c
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711691"
---
# <a name="analyze-processes"></a>プロセスの分析

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

**Process Advisor (プレビュー)** > **プロセス** 画面でプロセスを選択して、詳細画面に移動します。 ここで、ほとんどのプロセス管理活動にアクセスします。

> [!NOTE]
> 分析を表示する前に、Power Platform 管理者は、[Power Platform 管理センター](https://admin.powerplatform.microsoft.com/)で、組織の[TDS エンドポイント設定を有効にする](https://docs.microsoft.com/power-platform/admin/settings-features)必要があります。

## <a name="analyze-feature"></a>分析機能

ここで行うべき重要なことは、記録の状態を確認し、プロセスを分析することです。 コマンド バーの **分析** オプションを使用し開始します。

- プロセスが分析された後、コマンド バーで **分析** を選択すると、プロセス マップと関連する分析が使用可能になります。
- **詳細** ウィンドウのプロセス状態には、分析の状態と、プロセスが以前に分析されたかどうかが表示されます。
- 分析は、分析の準備ができているすべての記録のプロセス レベルで行われます。
- **記録** ウィンドウの **状態** 列にある記録の状態に注意してください。特定の状態の記録のみが分析の対象となります。

この短いビデオは、分析機能のナビゲーション方法について説明しています: [分析の機能](https://go.microsoft.com/fwlink/?linkid=2147426)

## <a name="recording-status"></a>記録の状態

各記録には、次のいずれかの状態があります。

- **進行中**: 記録は進行中ですが、記録がまだ開始されていない可能性もあります。 記録はデスクトップ クライアントで行われるため、Web ポータルは保存されるまでその状態を認識しません。 記録後に表示できるようにするために何らかの処理が必要なため、記録が保存された後に状態を確認することもできます。
- **失敗**: 記録処理中にエラーが発生しました。 新しい記録を作成してください。
- **未分析**: 記録は処理され、表示および編集できますが、分析の準備完了とマークされていません。
- **分析の準備完了**: 記録は分析の準備完了とマークされており、次にプロセスを分析するときに考慮されます。
- **分析済み**: 記録は分析されており、**分析** 画面で表示できる分析出力の一部です。

さらに、分析された記録の横には、次のアイコンのいずれかが表示される場合があります。

- ![分析の準備未完了](media/process-advisor-analyze/icon-not-ready.png "この記録は準備ができていません")記録が分析されたにもかかわらず、分析の準備未完了とマークされており、プロセスが再度分析された場合には含まれません。
- ![変更済み](media/process-advisor-analyze/icon-modified.png "この記録は修正されました")記録が変更されており、前の分析と同期していない可能性があることを示します。 再度分析すると、記録が分析出力およびプロセス マップと同期されます。
