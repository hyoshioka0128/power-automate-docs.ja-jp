---
title: Power Apps で Microsoft Teams アプリを使用してフローを作成する | Microsoft Docs
description: Teams で Power Apps アプリを使用してフローを作成します。
author: msftman
manager: kvivek
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/16/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ea9c4d0d1e7c59d8ccc3f0ecc714bb20042c3cb1
ms.sourcegitcommit: df7fb20065cfafc153b4bc4019dff2c94f4ef567
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "4553916"
---
# <a name="create-flows-using-the-power-apps-app-in-microsoft-teams"></a>Microsoft Teams で Power Apps アプリを使用してフローを作成する

Teams の新しい Power Apps アプリでフローを作成してカスタマイズし、Teams にさらなる価値を追加できます。 350 を超えるコネクタを利用して [インスタント](../introduction-to-button-flows.md)、[スケジュール済み](../run-scheduled-tasks.md)、[自動化](../get-started-logic-flow.md) などのフローを作成できます。 これには、Teams 内の [Microsoft Dataverse for Teams テーブル](/powerapps/teams/overview-data-platform#tables-in-dataverse-for-teams) と連携するためのコネクタも含まれます。

> [!NOTE]
> プレミアム コネクタを含むすべての Power Automate [コネクタ](https://docs.microsoft.com/Connectors/connector-reference/) にアクセスするには [Power Automate ライセンス](https://flow.microsoft.com/pricing/) が必要です。 Microsoft 365 ライセンスを持つユーザーは標準コネクタをすべて使用できます。

## <a name="prerequisites"></a>前提条件 

- Teams でフローを作成する前に Power Apps アプリをインストールする必要があります。 詳細情報: [Microsoft Teams に Power Apps パーソナル アプリをインストールする](/powerapps/teams/install-personal-app)

- Teams で Power Apps アプリを使用してフローを作成する前に、そのチーム用の Dataverse for Teams 環境がすでに存在している必要があります。 Dataverse for Teams 環境は、[Teams で最初のアプリを作成する](/powerapps/teams/create-first-app) ときに、自動的にプロビジョニングされます。

## <a name="create-a-flow-in-teams"></a>Teams でフローを作成する

1. Power Apps アプリの **ビルド** タブに移動して **すべて表示する** を選択します。

1. **新規** を選択して **フロー** を選択し、作成するフローのタイプを選択します。 次の種類のフローのみを作成できます: [インスタント](../introduction-to-button-flows.md)、[スケジュール済み](../run-scheduled-tasks.md)、[自動化](../get-started-logic-flow.md)。
 
   ![フローの作成](..\media\overview-teams-flows\new-flow.png)

1. 初めてフローを作成する場合は、国/地域を選択してから **開始する** を選択する必要があります。

   ![場所を選択する](..\media\overview-teams-flows\select-location.png)

1. **自動フローを構築する** 画面が表示され、トリガーを選択してフローを作成および保存できます。

   >[!NOTE]
   >ここに表示される画面は前の手順 2 で **インスタント** と **スケジュール済み** のどちらを選択したかにより異なります。

   ![デザイナーのビュー](..\media\overview-teams-flows\build-automated-flow.png)

## <a name="work-with-your-flows"></a>フローの作業

保存したフローを見つける方法:

1. Teams にサインインします。

1. 左側のウィンドウで **Power Apps** を選択します。

   ![[Power Apps の選択]](..\media\overview-teams-flows\select-power-apps.png)

1. **ビルド** タブでフローを作成したチームを選択し、ツリー ビューで **すべて表示する** を選択します。 

   ![すべてのフロー](..\media\overview-teams-flows\all-flows.png)

## <a name="customize-a-flow"></a>フローをカスタマイズする

Teams で、インストール済みのアプリからフローを取得したか、独自に作成した可能性があります。 これらのタイプのフローのいずれかを更新またはカスタマイズできます。 

1. フローを更新する際は **ビルド** タブを選択して **すべて表示する** を選択し、このチームのアプリとフローをすべて表示します。

1. 編集するフローを選択して **編集** を選択します。  

   ![編集を選択する](..\media\overview-teams-flows\customize-flow.png)

## <a name="view-details-and-run-history"></a>詳細と実行履歴を表示する

1. フローの詳細と実行履歴を表示する場合は **ビルド** タブを選択してから **すべて表示する** を選択します。

1. 詳細を表示するフローを選択してから **詳細** を選択します。

   ![フローの詳細を表示する](..\media\overview-teams-flows\view-details-history.png)

## <a name="related-articles"></a>関連記事

[Microsoft Teams で新しい Power Apps アプリを使用する](/powerapps/teams/create-apps-overview)<br/>
[ Dataverse for Teams とは?](/powerapps/teams/overview-data-platform)<br/>
[Dataverse for Teams 環境について](/power-platform/admin/about-teams-environment)
