---
title: Power Automate プロジェクトの Microsoft Dataverse への分析データの追加 | Microsoft Docs
description: 自動化のボトルネックを特定するために、各アクティビティまたはステップの開始時刻を記録するアクションを設定することができます。
author: taiki-yoshida
ms.service: flow
ms.topic: conceptual
ms.custom: guidance
ms.date: 12/10/2020
ms.author: tayoshi
ms.reviewer: kathyos
ms.openlocfilehash: eeefb98cfa313eba44aff501403b072504aa4db5
ms.sourcegitcommit: 970ad18a7ef795bff294f39ccfc8578bab9387d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "4714413"
---
# <a name="adding-analytical-data-to-microsoft-dataverse"></a>Microsoft Dataverse への分析データの追加

自動化のボトルネックを特定するために、各アクティビティまたはステップの開始時刻を記録するアクションをオートメーション内に設定することができます。 これを行うには、ステップ名、開始時刻、および終了時刻を記録するテーブルを作成します。

![分析データを保存するアクションの追加](media/store-analytical-data.png "分析データを保存するアクションの追加")

これにより、自動化の各エンドツーエンドの実行が完了するまでにかかった時間を追跡し、自動化をさらに改善する方法を見つけることができます。

このデータを Dataverse に保存する場合、Power BI を使用して、プロセスのどの部分が完了するのに最も時間がかかったかを特定することができます。

> [!div class="nextstepaction"]
> [次のステップ : 設計の意思決定フローチャート](decision-making-flow.md)