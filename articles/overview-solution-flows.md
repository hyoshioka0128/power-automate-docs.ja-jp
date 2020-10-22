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
ms.date: 08/14/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a0e986c9d98d8a928cde139f9e21a78331c4f039
ms.sourcegitcommit: c748e9804f4f03d18f3c81d40f1d6fc5862a24c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "3968747"
---
# <a name="overview"></a>概要


フローを [ソリューション](/power-platform/alm/solution-concepts-alm) でホストすると、フローが移植可能となり、フローとそのすべてのコンポーネントをある環境から別の環境に移動させることが容易になります。 典型的なユースケースとしては、独立系ソフトウェア ベンダー (ISV) がサンドボックス環境でフローを開発し、このフローをテスト環境に移動させる場合などが考えられます。 テスト後、ISV はこれらフローを購入した顧客に向けて本番環境に移行します。 このプロセスは、ソリューションでフローを作成し、ソリューションとそのコンテンツを移動させることで、はるかに簡易化を図ることができます。

ソリューション内に作成するフローは、*ソリューションに対応した*フローと呼ばれます。 1 つのソリューションに複数のフローを追加することができます。 ソリューションに対応していないフロー (ソリューションで作成されたのではないフロー) を別のソリューションに移動することはできません。

> [!NOTE]
> ソリューションの詳細な概念と、健全なアプリケーション ライフサイクル管理 (ALM) の実践を組織で実施するための情報については、[Microsoft Power Platform を使用したアプリケーションライフサイクル管理 (ALM)](/power-platform/alm/) を参照してください。

## <a name="prerequisites"></a>前提条件

ソリューションを作成するためには、以下のコンポーネントが必要となり、ソリューションに対応したフローを作成する必要があります :

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- バージョン 9.1.0.267 またはそれ以上の環境。

  バージョンを確認するには、[Power Platform 管理センター](https://admin.powerplatform.microsoft.com/) に移動して **環境** を選択し、目的の環境を選択してから **詳細** タブを選択します。

## <a name="create-a-solution"></a>ソリューションの作成

ソリューションを作成するには次のステップに従ってください :

1. [Power Automate](https://flow.microsoft.com) にサインインします。
1. ナビゲーション バーから **ソリューション** を選択します。

1. **新しいソリューション** を選択します。

   ![新しいソリューションを選択する](./media/overview-solution-flows/select-new-solution.png "新しいソリューションを選択する画面")

1. 新しいソリューションに必要となるすべての情報を指定します (**表示名**、**発行者**、**バージョン**、**名前**など)。 ソリューションの説明を入力しておくこともお勧めします。

   ![新しいソリューションの選択](./media/overview-solution-flows/new-solution.png "新しいソリューション プロパティ画面")

1. 上部のメニューから **保存して閉じる**を選択します。

  
   新しいソリューションは次の図のように表示されます :


   ![新しいソリューションが表示される](./media/overview-solution-flows/new-solution-created.png "*ソリューション* 画面に表示される新しいソリューション")


  
## <a name="learn-more"></a>詳細はこちら

- [ソリューションにフローを作成する](./create-flow-solution.md)
- [ソリューションのエクスポート](./export-flow-solution.md)
- [ソリューションのインポート](./import-flow-solution.md)
- [ソリューション対応フローを編集する](./edit-solution-aware-flow.md)
- [ソリューション対応フローを削除する](./remove-solution-aware-flow.md)
