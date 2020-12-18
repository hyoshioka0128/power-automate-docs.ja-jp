---
title: ビジネス プロセス フローでカスタム コントロールを使用する | Microsoft Docs
description: ビジネス プロセス フローのステップでカスタム コントロールを使用する方法について説明します。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/15/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a487962c7a190c83f043de7d405abc1715083b68
ms.sourcegitcommit: df7fb20065cfafc153b4bc4019dff2c94f4ef567
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "4553268"
---
# <a name="use-custom-controls-in-business-process-flows"></a>ビジネス プロセス フローでカスタム コントロールを使用する

[!INCLUDE[cc-data-platform-banner](./includes/cc-data-platform-banner.md)]

ビジネス プロセス フローでは、作業を行うためのガイド付きの方法が、ステージとステップという形式で提供されます。 ステージによって自分がプロセスのどの段階にいるかがわかり、ステップは必要な結果につながるアクション項目です。 ビジネス プロセス内のステップは、 Microsoft Dataverse のフィールドにバインドされます。 フィールドの種類 (テキスト ボックス、ドロップダウンなど) の既定の視覚化だけでなく、カスタム コントロールを使用して、ビジネス プロセス フローのステップに豊富な視覚化 (スライダー、放射状ノブ、LinkedIn コントロールなど) を追加し、ご自分のビジネス プロセスを使用するユーザーに魅力的なエクスペリエンスを提供することができます。

## <a name="adding-custom-controls-to-a-business-process"></a>ビジネス プロセスにカスタム コントロールを追加する

たとえば、リードから営業案件への営業プロセスの **推定予算金額** ステップに放射状ノブを追加し、**意思決定者の特定** ステップにフリップ スイッチを追加する必要があるとします。 

![サンプル リードを表示するスクリーンショット](./media/custom-controls/overview.png)

ビジネス プロセス フローにカスタム コントロールを追加する手順は、次のとおりです:

1. 関連するエンティティ フォームでカスタム コントロールを構成します。
1. ビジネス プロセス フローのフォームを生成してエクスポートします。
1. 関連するエンティティ フォームからビジネス プロセス フローのフォームに、カスタム コントロールの構成をコピーします。
1. カスタマイズを Dataverse にインポートし直します。

ビジネス プロセス フローのステップに [カスタム コントロールを追加する詳細なチュートリアル](https://powerusers.microsoft.com/t5/Power-Automate-Community-Blog/Preview-Custom-Controls-in-Business-Process-Flows/ba-p/263237) のこれらの手順を実行します。






