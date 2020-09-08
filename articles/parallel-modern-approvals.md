---
title: 最新のパラレル承認ワークフローを作成する | Microsoft Docs
description: 最新のパラレル承認ワークフローを作成する
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
ms.date: 08/07/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f338e4fd96dd0ff34c618e9bbe3ab97163990145
ms.sourcegitcommit: a7a7f603d44a12e989efcbc138acda6956a8273c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "3720669"
---
# <a name="create-parallel-approval-workflows-with-power-automate"></a>Power Automate を使用してパラレル承認ワークフローを作成する

パラレル承認ワークフローでは、請求書、発注書、休暇申請などの項目を複数のユーザーが承認する必要があります。各ユーザーの承認は、他のすべての承認者から独立しています。

このチュートリアルでは、Power Automate を使用してパラレル承認ワークフローを自動化するフローを作成します。 このフローにより、従業員の休暇申請プロセス (その従業員が日常的にサポートするすべてのユーザーまたはチームからの承認を求める) が自動化されます。 従業員は [SharePoint リスト](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7) を使用して休暇を申請します。 休暇の承認は、従業員の直属のマネージャー、営業チーム、および人事チームから得る必要があります。 各休暇申請は、決定を行う各承認者に転送されます。 このフローでは、状態の変化を示す電子メールが送信され、決定情報によって SharePoint が更新されます。

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]

## <a name="prerequisites"></a>前提条件

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]


作成する SharePoint Online リストには、次の列を含める必要があります。

| タイトル                   | 1 行テキスト    |
|-------------------------|------------------------|
| 従業員のコメント       | 1 行テキスト    |
| 直属のマネージャー コメント | 複数行テキスト |
| 営業チームのコメント     | 複数行テキスト |
| 人事チームのコメント        | 複数行テキスト |
| 直属のマネージャーの承認 | はい/いいえ                 |
| 営業チームの承認     | はい/いいえ                 |
| 人事チームの承認        | はい/いいえ                 |
| 休暇開始日     | 日付と時刻          |
| 休暇終了日       | 日付と時刻          |

SharePoint Online リストの名前と URL をメモします。 これらの項目は、後で **SharePoint - 項目が作成されたとき** トリガーを構成するために使用します。

## <a name="create-your-flow-from-the-blank-template"></a>空白のテンプレートからフローを作成する

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>トリガーの追加

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![SharePoint 情報](includes/media/parallel-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>休暇申請を作成した従業員のマネージャーを取得する

[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

## <a name="name-and-save-your-flow"></a>フローに名前を付けて保存する

フローの名前を指定し、**保存** を選んで、これまでに行った作業を保存します。

   > [!NOTE]
   > **保存** アイコンを定期的に選択して、フローへの変更を保存します。

## <a name="add-an-approval-action-for-immediate-manager"></a>直属のマネージャー用の承認アクションを追加する

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

   > [!IMPORTANT]
   > このアクションを実行すると、**担当者** ボックス内のメール アドレスに休暇申請が送信されるため、**マネージャー取得 (v2)** の一覧から取得した **電子メール** トークンを挿入してください。

## <a name="insert-a-parallel-branch-approval-action-for-the-sales-team"></a>営業チーム用のパラレル分岐承認アクションを挿入する

1. **マネージャー取得 (v2)** カードと **開始して承認を待つ** カードの間にある下向き矢印を選択します。
1. 下向き矢印を選択した後に表示されるプラス記号を選択します。
1. **並列分岐の追加** を選択します。

    ![マネージャーの構成を取得する](./media/parallel-modern-approvals/add-parallel-branch.png)
5. 休暇申請を営業チームに送信する **開始して承認を待つ** アクションを検索して選択し、構成します。 **開始して承認を待つ** アクションを追加する方法がわからない場合は、[直属のマネージャー用の承認アクションを追加するために使用したステップ](parallel-modern-approvals.md#add-an-approval-action-for-immediate-manager) を参照してください。

   > [!IMPORTANT]
   > **承認を開始 2** アクションの **担当者** ボックスにある営業チームのメール アドレスを使用します。

## <a name="insert-a-parallel-branch-approval-action-for-the-human-resources-team"></a>人事チーム用のパラレル分岐承認アクションを挿入する

[営業チーム用のパラレル分岐の挿入](parallel-modern-approvals.md#insert-a-parallel-branch-approval-action-for-the-sales-team) 手順を繰り返して追加し、休暇申請を人事に送信する **承認の開始** アクションを構成します。

> [!IMPORTANT]
> **承認の開始 3** アクションの **担当者** ボックスにある人事チームのメール アドレスを使用します。

以上の手順に従うと、フローは次の例のようになります:

   ![パラレル分岐が含まれるフロー](./media/parallel-modern-approvals/flow-with-parallel-branches.png)

## <a name="options-after-adding-parallel-branches"></a>パラレル分岐を追加した後のオプション

パラレル分岐にアクションを追加した後、フローにステップを追加するには 2 つの方法があります:

* **分岐内にステップを挿入:** カードの上または下にある *新しいステップの挿入* (**+**) ボタンを使用します。  このボタンは、分岐を選択するか、コネクタの矢印の上にカーソルを置くと表示されます)。 このボタンを選択すると、その **特定の分岐** にステップが追加されます。 このボタンは次のとおりです: ![新しいステップの挿入](./media/parallel-modern-approvals/Insert-new-step.png "+ 記号ボタンを使用して、分岐内にステップを挿入する")

* **フローにステップを追加:** ワークフロー全体の下部にある大きい **+ 新しいステップ**ボタンを使用します。 このボタンによって追加したステップは、以前のすべての分岐が完了した後に実行されます。  このボタンは次のとおりです: ![新しいステップを追加](./media/parallel-modern-approvals/new-step.png "[+ 新しいステップ] ボタンを使用して、フロー全体にステップを追加する")

次のセクションでは、各ブランチ内にステップを追加します:

* 休暇申請が承認されたか拒否されたかをチェックする条件を追加します。
* 決定を従業員に通知する電子メールを送信します。
* SharePoint 内の休暇申請を承認の決定情報によって更新します。

次に、*+ 新しいステップ* ボタンを使用して、休暇申請に関するすべての決定をまとめた電子メールを送信します。

次に進みましょう:

## <a name="add-a-condition-to-each-branch"></a>各分岐に条件を追加する

1. 最初の **開始して承認を待つ** 分岐を選択します。
1. カードの下の小さい *新しいステップの挿入* (**+**) ボタン (コネクタの矢印の上にカーソルを置くと表示される丸付きの + ボタン) を選択します。
1. 表示されるメニューから **アクションの追加** を選択し、アクションの一覧の **条件** を選択します。
1. **条件** カードの最初のボックスをオンにして、動的コンテンツ一覧の **開始して承認を待つ** カテゴリから **応答** トークンを選択します。

    ![パラレル分岐条件が含まれるフロー](./media/parallel-modern-approvals/configure-approval-condition.png)
1. 一覧 (**条件カード** の中ほどにある) が **と等しい** に設定されていることを確認します。
1. 最後のボックスに **承認** (このテキストでは大文字と小文字が区別されます) と入力します。
1. 条件カードは、次の例のようになります:

    ![パラレル分岐条件が含まれるフロー](includes/media/parallel-modern-approvals/condition-card.png)

   > [!NOTE]
   > この条件は、**承認を開始** アクションから従業員のマネージャーに送信される応答をチェックします。

1. **承認を開始 2** (営業への承認要求) と **承認を開始 3** (人事への承認要求) の分岐について、前のステップを繰り返します。

## <a name="add-email-actions-to-each-branch"></a>各分岐に電子メール アクションを追加する

**条件** 分岐の **はいの場合** の側で、次のステップを実行します。

   注: フローが、これらのステップを使用して電子メールを送信するのは、要求が承認された場合です。

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

![事前承認済みの電子メール テンプレートを構成する](includes/media/parallel-modern-approvals/yes-email-config.png)

要求が却下されたときに電子メールを送信するには、**条件** 分岐の **いいえの場合** の側を使用した後、前のステップを繰り返して却下の電子メール用のテンプレートを追加します。

**開始して承認を待つ 2** (営業への承認要求) と **開始して承認を待つ 3** (人事への承認要求) の分岐について、前のステップを繰り返します。

## <a name="update-the-vacation-request-with-the-decision"></a>決定によって休暇申請を更新する

決定が行われたときに SharePoint を更新するには、次の手順を実行します。

   注: 以下のステップを分岐の **はいの場合** と **いいえの場合** の両方の側で必ず実行してください。

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

  ![アイテムの更新の構成](./media/parallel-modern-approvals/configure-update-item.png)

**承認を開始 2** と **承認を開始 3** の分岐について、前のステップを繰り返します。

## <a name="complete-the-flow"></a>フローの完了

1. **+ 新しいステップ** を選択する
1. 各承認の結果を要約した電子メールを送信するには、上記のステップを使用します。 この電子メールを休暇を申請した従業員に送信します。 カードは次の例のようになります:

    ![アイテムの更新の構成](./media/parallel-modern-approvals/final-email-card.png)

## <a name="learn-more-about-modern-approvals"></a>最新の承認に関する詳細

[最新の承認の概要](modern-approvals.md)
