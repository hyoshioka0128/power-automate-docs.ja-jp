---
title: ソリューション対応フローの作成方法に関する説明 | Microsoft Docs
description: ソリューション対応フローを作成する方法について説明します。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/11/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: fe2fdf5b1eb5dc20597a0d086ad70c810e7908e7
ms.sourcegitcommit: ad8c043d9ad0c188237c0fc3bbd8fd0c7cec83c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "3988252"
---
# <a name="create-a-flow-in-a-solution"></a>ソリューションにフローを作成する


ソリューションで作成するフローは、*ソリューション対応* フローと呼ばれます。 次の手順に従って、ソリューション対応フローを作成します。

## <a name="prerequisites"></a>前提条件

ソリューション対応フローを作成する前に、少なくとも 1 つのソリューションを用意する必要があります。

## <a name="create-the-flow"></a>フローを作成する 

1. [Power Automate](https://flow.microsoft.com) にサインインします。
1. ナビゲーション バーから **ソリューション** を選択します。

   ![ソリューション オプションが強調表示された左側のナビゲーション バーを示す画面](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. フローを作成するソリューションを選択します。

   ![ソリューションの一覧を表示する画面](./media/create-flow-solution/new-solution-created.png)

1. **新規** を選択して **フロー** を選択します。

   ![フローを強調表示して作成できるさまざまな種類のアイテムを示す画面](./media/create-flow-solution/select-new-flow.png)

   Power Automate が開きます。

1. 利用可能なコネクタとトリガーを使用して、フローを構築します。

   この例では、受信トレイにメールが届いたときに通知を送信する、単純なフローを作成します。
1. **Office 365 Outlook** を検索して選択します。
1. **新しいメールが届いたとき (V3)** トリガーを選択します。
1. **新しいステップ** を選択します。
1. 「通知」 という単語を検索し、**モバイルに通知を送信** アクションを選択します。
1. **モバイルに通知を送信** ボックスの **テキスト** フィールドに、**件名** 動的トークンを追加します。
1. フローに名前を付けた後、フローを保存します。

   フローは次のようになります:

   ![作成されたフローを示すスクリーンショット](./media/create-flow-solution/new-email-notification-flow.png)
   
1. **ソリューション** を選択して、ソリューション内のフローを確認します。

   ![ソリューション内のフローを示すスクリーンショット](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>詳細情報を見る

* [ソリューションの作成](./overview-solution-flows.md)
* [ソリューションのエクスポート](./export-flow-solution.md)
* [ソリューションのインポート](./import-flow-solution.md)
* [ソリューション対応フローを編集する](./edit-solution-aware-flow.md)
* [ソリューション対応フローを削除する](./remove-solution-aware-flow.md)
