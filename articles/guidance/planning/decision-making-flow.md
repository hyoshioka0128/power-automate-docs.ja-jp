---
title: Power Automate での自動化の設計方法を決定するためのフローチャート | Microsoft Docs
description: この記事では、自動化を設計する方法を決定するために使用できるフローチャートを示します。
author: taiki-yoshida
ms.service: flow
ms.topic: conceptual
ms.custom: guidance
ms.date: 12/10/2020
ms.author: tayoshi
ms.reviewer: kathyos
ms.openlocfilehash: 7141936369a469989cef4e0854f5fb74b982448b
ms.sourcegitcommit: 970ad18a7ef795bff294f39ccfc8578bab9387d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "4714410"
---
# <a name="decision-making-flowchart-for-your-design"></a>設計の意思決定フローチャート

このフローチャートは、このセクションで前述した設計上の考慮事項に基づいて、自動化の設計方法を決定する際に役立ちます。

:::image type="complex" source="media/decision-making-flow.png" alt-text="設計の意思決定フローチャート":::
   矢印は、スタートから「コネクタが利用可能か」という決定につながる 「コネクタが利用可能」から、「はい」は、「スケジュールどおりに実行されている」という決定につながり、「いいえ」は「コネクタを作成できる開発者がいる」という決定につながる 「スケジュールどおりに実行されている」から、「はい」はエンドポイント「スケジュール トリガー付きのコネクタを使用した自動化」につながり、「いいえ」は「他のシステムのイベントに基づいて実行されている」という別の決定につながる 「他のシステムのイベントに基づいて実行されている」から、「いいえ」はエンドポイント「インスタント トリガー付きのコネクタを使用した自動化」につながり、「はい」はエンドポイント「自動トリガー付きのコネクタを使用した自動化」につながる 「コネクタを作成できる開発者がいる」から、「はい」はエンドポイント「カスタム コネクタを使用した自動化」につながり、「いいえ」はエンドポイント「デスクトップ フローを使用した自動化」につながる
:::image-end:::

> [!div class="nextstepaction"]
> [次のステップ : 作成フェーズ](making-phase.md)