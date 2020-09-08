---
title: 承認ワークフローの自動化の簡略化。  | Microsoft Docs
description: SharePoint、Dynamics CRM、Salesforce、OneDrive for Business、Zendesk、または WordPress と統合される承認ワークフローを自動化します。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/27/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e536612ab2cd3bba2f478d5ce38861ec24310a0b
ms.sourcegitcommit: 71dd515fb482312e2878c3eb8642441780290cb5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "3742454"
---
# <a name="create-and-test-an-approval-workflow-with-power-automate"></a>Power Automate での承認ワークフローを作成し、テストします

Power Automate では、SharePoint、Dynamics 365、Salesforce、OneDrive for Business、Zendesk、WordPress など、複数のサービスにわたりドキュメントやプロセスの承認を管理できます。

承認ワークフローを作成するには、**承認 - 承認を開始** アクションを任意のフローに追加します。 このアクションを追加すると、フローでドキュメントまたはプロセスの承認を管理できるようになります。 たとえば、請求書、作業指示書または販売見積りを承認する、ドキュメントの承認フローを作成できます。 また、休暇申請、超過作業時間、出張計画を承認する、プロセスの承認フローを作成することもできます。

承認者は、受信トレイ、 Power Automate  Web サイトの [承認センター](https://flow.microsoft.com/manage/approvals/received/) 、または Power Automate アプリから要求に対応できます。

## <a name="create-an-approval-flow"></a>承認フローを作成する
ここで、作成し、テストするフローの概要を次に示します:

   ![フローの概要](./media/modern-approvals/create-flow-overview.png)

フローでは次の手順を実行します:

1. 誰かが SharePoint Online リストで休暇申請を作成したときに開始されます。
1. 休暇申請を承認センターに追加し、それを承認者に電子メールで送信します。
1. 休暇を申請したユーザーに、承認者の決定内容を含む電子メールを送信します。
1. SharePoint Online リストを事前承認者の決定とコメントによって更新します。

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]

## <a name="prerequisites"></a>前提条件

このチュートリアルを完了するには、以下にアクセスする必要があります:

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

SharePoint Online リストで次の列を作成します：

| 列 | 型 |
| ------ | ------ |
| タイトル | 1 行テキスト |
|開始日 | 日付と時間 |
| 終了日 | 日付と時間 |
| コメント | 1 行テキスト |
| 承認済み | はい/いいえ |
| マネージャーコメント | 1 行テキスト |

SharePoint Online リストの名前と URL をメモします。 これらの項目は、後で **SharePoint - 新しい項目が作成されたとき** トリガーを構成する際に使用します。

## <a name="create-your-flow-from-the-blank-template"></a>空白のテンプレートからフローを作成する
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>トリガーの追加

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

**サイト アドレス** と **リスト名** は、このチュートリアルで先に示された項目です。

![SharePoint 情報](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>プロファイル アクションの追加

1. **新しいステップ** を選択し、次に **プロファイル** と **アクションの選択** 検索ボックスに入力します。

1. **Office 365 ユーザー - 自分のプロファイルの取得** アクションを検索して選択します。

    ![プロファイルの検索](./media/modern-approvals/search-for-profile.png)

1. フローに含めるプロファイルのフィールドを選択し、**作成** をクリックして、これまでの作業を保存します。

## <a name="add-an-approval-action"></a>承認アクションの追加

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> このアクションを実行すると、**担当者** ボックス内の電子メール アドレスに承認要求が送信されます。
>
> シナリオで必要な場合は、Common Data Service を使用する承認要求にファイルを添付できます。

## <a name="add-a-condition"></a>条件を追加する

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>承認に電子メール アクションを追加する

休暇申請が承認された場合に電子メールを送信するには、次のステップに従います:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![承認された電子メールのテンプレートを構成する](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>承認された要求の更新アクションを追加する

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> **サイト アドレス**、**リスト名**、**ID**、および **タイトル** は必須です。

![アイテムの更新の構成](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>却下に電子メール アクションを追加する

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![却下された要求の構成](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>却下された要求に更新アクションを追加する

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > **サイト アドレス**、**リスト名**、**ID**、および **タイトル** は必須です。

   ![アイテムの更新カード](./media/modern-approvals/configure-update-item-no.png)

4. 行った作業を保存するには **保存** を選択します。

以上の手順に従うと、フローは次のスクリーンショットのようになります:

![フローの概要](./media/modern-approvals/completed-flow.png)

これでフローが作成されたので、テストしてみましょう!

## <a name="request-an-approval"></a>承認の要求

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]


## <a name="create-long-running-approvals"></a>長期にわたる承認の作成

フローが 30 日以上実行される可能性が高い場合は、Common Data Service に承認を保存することを検討してください。 これにより、元のフローの実行がタイムアウトした後でも、承認リクエストへの応答に基づいて動作するフローを作成できます。これを行うには、**承認を作成する（v2）** アクションに基づいて、2 つのフローを使用します。1 つは承認リクエストを送信し、もう 1 つは承認リクエストへの応答に基づいてビジネスロジックを実行します。 [長期にわたる承認](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/increased-run-duration) について詳細情報を確認します。

>[!TIP]
> 最新の電子メール クライアントを使用している場合、要求が引き続き必要かどうかを気にする必要はありません。これは、Power Automate によって承認が完了していることを示すように電子メールが自動的に更新されるためです。

## <a name="cancel-an-approval-requests"></a>承認要求の取り消し

場合によっては、送信した承認要求を取り消す必要があります。 要求に間違いがあったか、または関連するものではなくなった可能性があります。 どちらの場合も、要求を送信したユーザーは、次の手順に従って取り消すことができます:

1. 承認の選択
1. 作業ウィンドウで **承認の取り消し** を選択します。

>[!TIP]
>いつでも **履歴** タブを選択して、取り消した承認要求を表示できます。

>[!NOTE]
> 取り消し機能は、**承認の作成 (v2)** アクションでサポートされています。

## <a name="request-approvals-from-guest-users"></a>ゲスト ユーザーからの承認の要求

組織外のユーザーに承認要求を送信できます。 これを行うには、[他のテナントのユーザーをゲストとして招待する](https://docs.microsoft.com/azure/active-directory/b2b/add-user-without-invite) を使用して、Azure Active Directory（Azure AD）ゲストユーザーを使用します。

ゲストにロールを割り当てると、承認プロセスに参加するために必要なアクセス許可がゲストに付与されます。

これでフローの作成およびテストが終了したので、フローの使い方を他のユーザーに知らせてください。

## <a name="learn-more"></a>詳細はこちら

* [承認待ちの要求](approve-reject-requests.md) を表示し、管理する
* [シーケンシャル承認フロー](sequential-modern-approvals.md) を作成します。
* [パラレル承認フロー](parallel-modern-approvals.md) を作成します。
* [Android](https://aka.ms/flowmobiledocsandroid) 向けの Power Automate モバイル アプリ、[iOS](https://aka.ms/flowmobiledocsios)、[Windows Phone](https://aka.ms/flowmobilewindows) をインストールします。
