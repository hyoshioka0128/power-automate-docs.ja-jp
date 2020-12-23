---
title: Power Automate プロジェクトのパフォーマンス問題の診断 | Microsoft Docs
description: フローの実行中に遅延または速度低下が発生している場合は、その日の Power Automate 制限に達成したかもしれません。 この記事では、これらの問題を明らかにする方法について説明します。
author: taiki-yoshida
ms.service: flow
ms.topic: conceptual
ms.custom: guidance
ms.date: 12/10/2020
ms.author: tayoshi
ms.reviewer: kathyos
ms.openlocfilehash: 90f4a0ff7b8f316baae8eadae3982bf9dcc2de64
ms.sourcegitcommit: 970ad18a7ef795bff294f39ccfc8578bab9387d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "4714416"
---
# <a name="diagnosing-performance-issues"></a>パフォーマンス問題の診断

フローの実行中に遅延または速度低下が発生している場合は、その日の Power Automate 制限に到達したかもしれません。 詳細: [制限と割り当てを依頼](/power-platform/admin/api-request-limits-allocations)

## <a name="action-analytics"></a>アクション分析

自動化が限界に達しているかどうかを確認するには、アクション分析を使用して、アクションをどれだけ使用しているかについての洞察を深めることができます。

**アクション分析の確認**

1.  **自分のフロー** に移動します。

2.  分析するフローを選択します。

3.  **分析する。** を選択する

4.  **アクション** タブを選択します。

![フロー アクション リクエストのチャート](media/flow-action-runs.png "フロー アクション リクエストのチャート")

自動化が遅くなった場合は、フロー設計を再検討し、実行されるアクションの数を減らすのに役立つ追加の効率を確認することをお勧めします。

超過が原因で常に遅延しているフローの場合、フロー所有者はフロー実行が遅延しないようにするためのヒントとコツとともに、これらの超過についての通知も受け取ります。

次の画像は、アクション制限に対して一貫して実行されているフローに対して送信された電子メールの例を示しています。

![フローが予想よりも多くのアクションを実行しており、使用するアクションが少ない場合はオフになるというパフォーマンス アラート](media/performance-alert-email.png "フローが予想よりも多くのアクションを実行しており、使用するアクションが少ない場合はオフになるというパフォーマンス アラート")

## <a name="limits-from-connected-services"></a>接続済みサービスからの制限

Power Automate と似ていて、ほとんどの Web サービスとアプリは、サービス保護制限と不正使用検出アルゴリズムも実装する傾向があります。

誤って構成されたフローはこれらの制限に達することがあり、通常はエラー \[429\] またはタイムアウト \[5xx\] としてご使用のフローランに現れます。 これらの制限は、フロー内で使用しているコネクタまたはサービスによって異なることに注意が重要です。
