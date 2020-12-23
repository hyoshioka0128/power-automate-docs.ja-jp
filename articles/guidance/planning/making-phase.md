---
title: Power Automate プロジェクトの作成フェーズ | Microsoft Docs
description: この記事では、Power Automate クラウドまたはデスクトップの自動化の設定に役立つ関連ドキュメントを紹介します。
author: taiki-yoshida
ms.service: flow
ms.topic: conceptual
ms.custom: guidance
ms.date: 12/10/2020
ms.author: tayoshi
ms.reviewer: kathyos
ms.openlocfilehash: 6197b18289dc73997dc94769d64d3ccc254c1057
ms.sourcegitcommit: 970ad18a7ef795bff294f39ccfc8578bab9387d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "4714412"
---
# <a name="making-phase"></a>作成フェーズ

プロセスを自動化する方法を計画および設計する手順は以上です。
次のステップでは、自動化の設定をします。

## <a name="basic-steps-for-cloud-flows"></a>クラウド フローの基本的な手順

1.  [Power Automate](https://flow.microsoft.com) でクラウド フローを作成します。

2. [コネクタ](/connectors/)でフローを開始するイベントまたはトリガーを指定します。 自動化をトリガーする方法に基づいて、Power Automate フローをトリガーするために使用するイベントを指定します。

3.  [アクション](../../multi-step-logic-flow.md)および[条件](../../add-condition.md)を追加します。

詳細: [Power Automate でクラウド フローを作成する](../../overview-cloud.md)、[Power Automate でテンプレートからフローを作成する](../../get-started-logic-template.md)

## <a name="basic-steps-for-desktop-flows"></a>デスクトップ フローの基本的な手順

1.  [Power Automate Desktop](../../desktop-flows/introduction.md) で新しいデスクトップ フローを作成します。

2.  アクションを追加し、構成を設定します。

3.  入力と出力を定義します。

4.  作成したデスクトップ フローをテストします。

5.  必要に応じて、クラウド フローと Power Automate Desktop 間のトリガーとリンクを設定します。

> [!div class="nextstepaction"]
> [次のステップ: テスト戦略](testing-strategy.md)