---
title: ソリューションに対応したフローの概要 | Microsoft Docs
description: ソリューション内にフローを作成する場合の利点について説明します。
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
ms.date: 7/27/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 860df112928e4d005e2f11bb92db2db68c325572
ms.sourcegitcommit: d7707928484106e4a8442055111560f9a9cf7c6e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "3641085"
---
# <a name="overview"></a>概要


フローを [ソリューション](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview) でホストすると、フローが移植可能となり、フローとそのすべてのコンポーネントをある環境から別の環境に移動させることが容易になります。 典型的なユースケースとしては、独立系ソフトウェア ベンダー (ISV) がサンドボックス環境でフローを開発し、このフローをテスト環境に移動させる場合などが考えられます。 テスト後、ISV はこれらフローを購入した顧客に向けて本番環境に移行します。 このプロセスは、ソリューションでフローを作成し、ソリューションとそのコンテンツを移動させることで、はるかに簡易化を図ることができます。

ソリューション内に作成するフローは、*ソリューションに対応した*フローと呼ばれます。 1 つのソリューションに複数のフローを追加することができます。 ソリューションに対応していないフロー (ソリューションで作成されたのではないフロー) を別のソリューションに移動することはできません。

> [!NOTE]
> ソリューションの詳細な概念と、健全なアプリケーション ライフサイクル管理 (ALM) の実践を組織で実施するための情報については、[Microsoft Power Platform を使用したアプリケーションライフサイクル管理 (ALM)](/power-platform/alm/) を参照してください。

## <a name="prerequisites"></a>前提条件

ソリューションを作成するためには、以下のコンポーネントが必要となり、ソリューションに対応したフローを作成する必要があります :

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- バージョン 9.1.0.267 またはそれ以上の環境。

  バージョンを確認するには、[Power Automate 管理センター](https://admin.flow.microsoft.com) に移動して **環境** を選択し、目的の環境を選択してから **詳細** タブを選択します。

## <a name="create-a-solution"></a>ソリューションの作成

ソリューションを作成するには次のステップに従ってください :

1. [Power Automate](https://flow.microsoft.com) にサインインします。
1. ナビゲーション バーから **ソリューション** を選択します。

1. **新しいソリューション** を選択します。

   ![新しいソリューションを選択する](./media/overview-solution-flows/select-new-solution.png "新しいソリューションを選択する画面")

1. 新しいソリューションに必要となるすべての情報を指定します (**表示名**、**発行者**、**バージョン**、**名前**など)。 ソリューションの説明を入力しておくこともお勧めします。

   ![新しいソリューションを選択する](./media/overview-solution-flows/new-solution.png "新しいソリューションのプロパティ画面")

1. 上部のメニューから **保存して閉じる**を選択します。

  
   新しいソリューションは次の図のように表示されます :


   ![新しいソリューションを表示する](./media/overview-solution-flows/new-solution-created.png "*ソリューション*画面が表示された新しいソリューション")


  
## <a name="learn-more"></a>詳細はこちら

- [ソリューションにフローを作成する](./create-flow-solution.md)
- [ソリューションのエクスポート](./export-flow-solution.md)
- [ソリューションのインポート](./import-flow-solution.md)
- [ソリューション対応フローを編集する](./edit-solution-aware-flow.md)
- [ソリューション対応フローを削除する](./remove-solution-aware-flow.md)
