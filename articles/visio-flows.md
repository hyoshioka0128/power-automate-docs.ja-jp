---
title: Microsoft Visio でフローを設計する | Microsoft Docs
description: Visio に関する組織の専門知識を活用し、フローを作成するための開始点として一般的なモデルを構築します。
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/25/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a667bbcc9983979d9fef115308d852280241ae6f
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709759"
---
# <a name="design-flows-in-microsoft-visio"></a>Microsoft Visio でフローを設計する


Power Automate デザイナーは、ロジックのあらゆる細部を構成できる多機能ツールです。 ただし、フローの構築を開始する前にフロー ロジックをスケッチする場合があります。 その際、Power Automate 内から直接、Microsoft Visio を使用します。

>[!TIP]
> さまざまなプロセスで一般的なモデルが共有されますが、組織全体で細かな違いがあります。 Visio を使用してマスター ワークフロー モデルを作成し、他のユーザーが特殊なパラメーターで調整することで、組織内の時間を節約できます。

## <a name="prerequisites"></a>前提条件

- Power Automate アカウント。
- Microsoft Visio デスクトップ アプリ (英語版)。
- Microsoft Visio の使用に関する専門知識。

## <a name="design-a-workflow-in-visio"></a>Visio でワークフローを設計する

1. [Power Automate](https://flow.microsoft.com) にサインインする。
1. 左側パネルから **テンプレート** を選択します。

     ![左側パネルからテンプレートを選択します](./media/visio-flows/templates-from-left-panel.png)

1. 一覧から **Visio** を選択します。

     ![Visio テンプレートへのフィルター](./media/visio-flows/select-visio.png) 

1. 表示された **Visio** テンプレートの一覧から **Flow の基本的な BPMN 図** テンプレートを選択します。

     ![Visio テンプレートを選択する](./media/visio-flows/visio-templates.png) 

     >[!IMPORTANT]
     >Visioは、インターネットからのファイルがデバイスに害を及ぼす可能性があることを警告しています。 問題なければ、警告メッセージ上の **はい** を選択します。

     ![インターネットからのファイルに関する警告に注意](./media/visio-flows/visio-warning.png)

1. Visio デザイナーが起動します。

     ![Visio デザイナーのビュー](./media/visio-flows/visio-designer.png)


1. BPMN 基本図形を使用し、[ワークフローを設計します](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a)。

   ![BPMN 基本図形](./media/visio-flows/bpmn-basic-shapes.png)

## <a name="prepare-to-export-your-workflow-to-power-automate"></a>Power Automate にワークフローをエクスポートする準備をする

Power Automate にエクスポートできるように次の手順でワークフローを準備します。

1. **プロセス** タブを選択します。
1. アイコンの **Power Automate** グループから **エクスポートの準備** を選択します。

   ![エクスポートの準備アイコンを選択する](./media/visio-flows/prepare-export-icon.png)
   
   **エクスポートの準備** グループが開きます。

   ![エクスポートの準備グループ](./media/visio-flows/prepare-export-group.png)

1. **エクスポートの準備** グループの **Flow のマッピング** タブで、BPMN 図を Power Automate にマッピングします。 

1. **エクスポートの準備** グループの **トリガーとアクション** タブで、各図形を選択したら、Power Automate でその図形を表わすトリガーまたはアクションを選択することで、BPMN 図を Power Automate のトリガーとアクションにマッピングします。

**エクスポートの準備** コントロールに問題が残っていない場合、ワークフローをエクスポートする準備ができています。

![問題なし](./media/visio-flows/prepare-export-no-issues.png) 

## <a name="export-your-workflow"></a>ワークフローをエクスポートする
1. **Flow にエクスポート** ボタンを選択し、ワークフロー図を Power Automate にエクスポートします。
1. フローに名前を付け、**フローの作成** ボタンを選択します。
   
   ![フローを作成する](./media/visio-flows/export-create-flow.png)

1. これに似たような成功レポートが表示されます。

    ![成功しました](./media/visio-flows/export-create-flow-success.png)

これで、他のあらゆるフローと同様に、Power Automate デザイナーからフローを実行したり、編集したりできます。

>[!TIP]
> Visioの共有機能とコメント機能を使用して、複数の関係者と共同作業を行い、完全なワークフローをすばやく作成します。

## <a name="learn-more"></a>詳細情報を見る

- [Power Automate の概要](getting-started.md) 
- [複数ステップのフローを作成する](multi-step-logic-flow.md)
- [Microsoft Visio でクラウド フローを設計する](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a)

     
