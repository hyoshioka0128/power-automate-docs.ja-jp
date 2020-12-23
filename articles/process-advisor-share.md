---
title: Process Advisor プロセスの共有 (プレビュー) | Microsoft Docs
description: Power Automate で Process Advisor のプロセスを共有する方法。
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
ms.openlocfilehash: 71bea9374c0cafda081f5ee81cac9ce70c048242
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711669"
---
# <a name="share-processes-preview"></a>プロセスの共有 (プレビュー)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Process Advisor でプロセスを作成すると、自分にだけ表示されます。 しかし、他の人から意見を聞くことは、作成したプロセスを実現するさまざまな方法を理解するための鍵です。 プロセスを組織内の他のユーザーに共有して、管理または貢献してもらえるようにします。 Process Advisor のプロセスを共有するには、主に 2 つの方法があります。

- 共同所有者にプロセスを共有する。
- 投稿者にプロセスを共有する。

プロセスの共同所有者または投稿者の場合、Process Advisor のプロセス ページに一覧表示されます。
重要: プロセスへの所有者と寄稿者の追加または削除を行うには、共同所有者である必要があります。

## <a name="share-action"></a>共有操作

共有アクションは、共同所有者となっている各プロセスに関する Process Advisor のプロセス画面で使用可能です。 また、環境のシステム管理者や、Process Advisor システム エンティティに対する共有アクセス許可を持った任意のセキュリティ ロールでも、これを使用できます。
共有アクションは、同じ条件で、Process Advisor のプロセス詳細画面でも使用可能です。
記録レベルでは共有は必要ありません。 共同所有者とプロセスを共有すると、プロセスに関連付けられた記録を管理できるようになります。

## <a name="share-panel"></a>共有パネル

> [!div class="mx-imgBorder"]
> ![共有画面](media/process-advisor-visualize/analytics-screen.png "共有のスクリーンショット")

共有アクションを選択すると、共有パネルが表示されます。 共有パネルで、組織内の Microsoft Dataverse のユーザーとチームを選択し、それらとプロセスを共有します。

他のユーザーとプロセスを共有する場合、電子メールでの招待を自動的に送信するオプションが選択されます。 この電子メールの招待状には、プロセスを共有したことが示されています。 共同所有者または投稿者として、プロセスの管理または新しい記録の追加をサポートすることが求められます。 電子メールの招待状には、共有されたプロセスへのリンクがあります。

## <a name="share-a-process-with-a-contributor"></a>投稿者にプロセスを共有する

プロセスに投稿者を追加することは、プロセスを共有する最も一般的な方法です。 プロセスの協同所有者はすべて、次の操作を実行できます。

- プロセスの詳細を表示します。
- 記録を追加してラベルを付けます。
- プロセスに追加された独自の記録を管理します (記録のラベル付けと削除を含む)。

## <a name="share-a-process-with-a-co-owner"></a>共同所有者にプロセスを共有する

共同所有者をプロセスに追加することにより、他のユーザーが投稿者の記録にラベルを付けて検証し、プロセスを管理し、そしてプロセスの分析とダッシュボードを視覚化することができるようになります。 プロセスの協同所有者はすべて、次の操作を実行できます。

- 詳細を表示します。
- 名前や説明などのプロパティを更新します。
- 共同所有者と投稿者を招待します。
- 記録を追加してラベルを付けます。
- プロセスに追加されたすべての記録を管理します (他のユーザーの記録のラベル付けと削除を含む)。
- プロセスを分析します。
- 分析されたプロセスの分析を表示します。
- プロセスを削除します。
