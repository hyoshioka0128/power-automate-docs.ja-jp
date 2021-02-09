---
title: 複数の承認者が存在する最新の承認ワークフローを作成する | Microsoft Docs
description: '複数の承認者が存在する最新の承認ワークフローを作成する '
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/13/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 240d043eaa9d38b371bff9bc7bd736dee48033e8
ms.sourcegitcommit: 7b39517611bff350c760e76d0d6eed03739194a7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "3710708"
---
# <a name="manage-sequential-approvals-with-power-automate"></a>Power Automate を使用してシーケンシャル承認を管理する

一部のワークフローでは、最終承認者が承認する前に事前承認が必要です。 たとえば、ある会社には、$1000.00 を超える請求書では財務部門による承認の前に事前承認を要求するシーケンシャル承認ポリシーが存在する可能性があります。

このチュートリアルでは、従業員の休暇申請を管理するシーケンシャル承認フローを作成します。

> [!NOTE]
> ここでは、SharePoint は例としてのみ使用されます; これは、承認フローを作成するために必要なものではありません。 Power Automate が統合してフローを促進する 200 を超えるサービスのいずれかを使用できます。 SharePoint 2010 を使用している場合は、[SharePoint 2010 ワークフローの廃止](https://go.microsoft.com/fwlink/?linkid=2138686) を参照してください

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]


## <a name="detailed-steps-in-the-flow"></a>フローの詳細なステップ

このフローは次のようなものです:

1. 従業員が [SharePoint Online リスト](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7) で休暇申請を作成したときに開始されます。
1. 休暇申請を承認センターに追加した後、申請を事前承認者に電子メールで送信します。
1. 事前承認の決定を従業員に電子メールで送信します。
1. SharePoint Online リストを事前承認者の決定とコメントによって更新します。
   注: 申請が事前承認された場合に、フローは以下のステップに進みます:
1. 最終承認者に申請を送信します。
1. 最終決定を従業員に電子メールで送信します。
1. SharePoint リストを最終決定によって更新します。

このイメージは、上記のステップをまとめたものです:

   ![シーケンシャル承認フローの図](./media/sequential-modern-approvals/visio-overview.png)

## <a name="prerequisites"></a>前提条件

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

このチュートリアルの目的上、作成する SharePoint Online リストには、次の列を含める必要があります。

作成する SharePoint Online リストには、次の列を含める必要があります。

| タイトル                   | 1 行テキスト    |
|-------------------------|------------------------|
| 変更済み                | 日付と時刻          |
| 作成済                 | 日付と時刻          |
| 休暇開始日     | 日付と時刻          |
| 休暇終了日       | 日付と時刻          |
| コメント                | 1 行テキスト    |
| 承認済み                | はい/いいえ                 |
| マネージャー コメント        | 複数行テキスト |
| 変更済み                | 日付と時刻          |
| 作成済                 | 日付と時刻          |
| 事前承認済み            | はい/いいえ                 |
| 作成者               | ユーザーまたはグループ        |
| 変更者             | ユーザーまたはグループ        |

SharePoint Online リストの名前と URL をメモします。 これらの項目は、後で **SharePoint - 新しい項目が作成されたとき** トリガーを構成するときに使用します。

## <a name="create-your-flow"></a>フローを作成する

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>トリガーの追加

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![SharePoint 情報](./media/sequential-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>休暇申請を作成した従業員のマネージャーを取得する
[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

   > [!NOTE]
   > 作業しながらフローへの変更を定期的に保存することをお勧めします。

## <a name="add-an-approval-action-for-pre-approvals"></a>事前承認用の承認アクションを追加する
[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

注: このアクションを実行すると、**担当者** ボックス内の電子メール アドレスに事前承認要求が送信されます。

## <a name="add-a-condition"></a>条件を追加する
[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

> [!NOTE]
> この条件は、**開始して承認を待つ** アクションからの応答をチェックします。
> 
> 

## <a name="add-an-email-action-for-pre-approvals"></a>事前承認用の電子メール アクションを追加する
[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![事前承認済みの電子メール テンプレートを構成する](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-pre-approved-requests"></a>事前承認された要求用の更新アクションを追加する
[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![アイテムの更新の構成](./media/sequential-modern-approvals/update-item-preapproval.png)

## <a name="get-the-pre-approvers-manager"></a>事前承認者のマネージャーを取得する

1. 先ほどの [休暇申請を作成した従業員のマネージャーを取得する](sequential-modern-approvals.md#get-the-manager-for-the-person-who-created-the-vacation-request) ステップを使用して追加し、別の **マネージャー取得** アクションを構成します。 今回は事前承認者のマネージャーを取得します。
2. 完了すると、**マネージャー取得 2** カードはこのイメージのようになります。 **このフローで使用されるアプリやサービスから動的なコンテンツを追加します** カードでは、**マネージャー取得** カテゴリから取得した **電子メール** トークンを使用してください。
   
   ![事前承認者のマネージャーを取得する](includes/media/modern-approvals/get-pre-approver-manager.png)

## <a name="add-the-final-approval-action"></a>最終承認アクションを追加する
1. 先ほどの [事前承認用の承認アクションを追加する](sequential-modern-approvals.md#add-an-approval-action-for-pre-approvals) ステップを使用して追加し、別の **開始して承認を待つ** アクションを構成します。 このアクションを使用すると、最終承認を求める電子メール要求が送信されます。
2. 完了したカードはこのイメージのようになります:
   
    ![承認の構成](./media/sequential-modern-approvals/provide-approval-config-info.png)

## <a name="add-the-final-approval-condition"></a>最終承認条件を追加する
1. [条件を追加する](sequential-modern-approvals.md#add-a-condition) のステップを繰り返して追加し、最終承認者の決定を確認する **条件** を構成します。

## <a name="send-email-with-final-approval"></a>最終承認情報を含む電子メールを送信する
1. [事前承認用の電子メール アクションを追加する](sequential-modern-approvals.md#add-an-email-action-for-pre-approvals) のステップを使用して追加し、休暇申請が承認されたときに電子メールを送信するアクションを構成します。
2. 完了すると、カードはこのイメージのようになります:
   
   ![最終承認の電子メール テンプレート](./media/sequential-modern-approvals/vacatioin-request-approved-email-template.png)

## <a name="update-sharepoint-with-approval"></a>承認を得て SharePoint を更新
1. [事前承認された要求用の更新アクションを追加する](sequential-modern-approvals.md#add-an-update-action-for-pre-approved-requests) のステップに従って追加し、休暇申請が承認されたときに SharePoint を更新するアクションを構成します。
2. 完了すると、カードはこのイメージのようになります:
   
    ![アイテムの更新の構成](./media/sequential-modern-approvals/configure-update-item-approved.png)

## <a name="send-email-with-pre-approval-rejection"></a>事前承認の却下情報を含む電子メールを送信する
[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

   ![却下された要求の構成](./media/sequential-modern-approvals/configure-rejected-email.png)

注: このアクションは **条件** カードの下にある **いいえの場合、何もしない** 分岐に追加する必要があります。

## <a name="update-sharepoint-with-pre-approval-rejection"></a>事前承認の却下で SharePoint を更新
[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   ![要求が却下された場合に SharePoint を更新する](./media/sequential-modern-approvals/update-sharepoint-with-rejection.png)

## <a name="send-email-with-final-rejection"></a>最終的な却下情報を含む電子メールを送信する
1. [事前承認の却下情報を含む電子メールを送信する](sequential-modern-approvals.md#send-email-with-pre-approval-rejection) のステップを使用して追加し、休暇申請が最終承認者によって却下されたときに電子メールを送信するアクションを構成します。
   
    注: このアクションは **条件 2** カードの下にある **いいえの場合、何もしない** 分岐に追加する必要があります。
2. 完了すると、カードはこのイメージのようになります:
   
   ![却下された要求の構成](./media/sequential-modern-approvals/final-rejection-email-card.png)

## <a name="update-sharepoint-with-final-rejection"></a>最終的な却下で SharePoint を更新

1. [事前承認の却下で SharePoint を更新](sequential-modern-approvals.md#update-sharepoint-with-pre-approval-rejection) のステップに従って追加し、最終承認者が休暇申請を却下したときに SharePoint を更新するアクションを構成します。
1. 完了すると、カードはこのイメージのようになります:
   
   ![アイテムの更新カード](./media/sequential-modern-approvals/final-rejection-update-sharepoint.png)
1. **フローの更新** を選択して、行った作業を保存します。

以上の手順に従うと、フローは次のイメージのようになります:

![フローの概要](./media/sequential-modern-approvals/completed-flow.png)

フローを作成したので、実際に実行してみましょう。

## <a name="request-an-approval"></a>承認の要求

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

要求は次のイメージのようになります:

![休暇申請](./media/sequential-modern-approvals/vacation-request.png)

## <a name="view-pending-approval-requests"></a>承認待ちの要求を表示する

[!INCLUDE [view-pending-approvals](includes/view-pending-approvals.md)]

## <a name="pre-approve-a-request"></a>要求を事前承認する

[!INCLUDE [approve-request-from-different-locations](includes/approve-request-from-different-locations.md)]

## <a name="approve-the-request"></a>要求を承認する

要求を承認するステップは、[要求を事前承認する](sequential-modern-approvals.md#pre-approve-a-request) ステップと同じです

注: 最終承認者が休暇申請を取得するのは、その申請が事前承認された後だけです。

## <a name="reject-a-request"></a>要求を却下する

[!INCLUDE [reject-a-request](includes/reject-a-request.md)]

## <a name="more-information"></a>詳細

[1 人の承認者による最新の承認のチュートリアル](modern-approvals.md)

