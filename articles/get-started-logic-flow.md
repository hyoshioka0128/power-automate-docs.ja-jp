---
title: フローを作成してタスクを自動化する | Microsoft Docs
description: フローを作成して、イベント (SharePoint リストに行を追加するなど) が発生したときに 1 つ以上のアクション (メールの送信など) を自動的に実行します。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/04/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 569408367130c6f5121b30d2c8c14833b142b934
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "74368791"
---
# <a name="create-a-flow-in-power-automate"></a>Power Automate でフローを作成する
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

> [!VIDEO https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]

イベントによってトリガーされた後は 1 つまたは複数のタスクを自動的に実行するフローを作成します。 たとえば、指定したキーワードが含まれるツイートを誰かが送信したときにメールで通知するフローを作成するとします。 この例では、ツイートの送信がイベント、メールの送信がアクションになります。

## <a name="prerequisites"></a>前提条件

* [flow.microsoft.com](https://flow.microsoft.com) のアカウント
* Twitter アカウント
* Office 365 の資格情報

## <a name="specify-an-event-to-start-the-flow"></a>フローを開始するイベントを指定する

最初に、どのようなイベントまたは*トリガー*でフローを開始するのか選択する必要があります。

1. [flow.microsoft.com](https://flow.microsoft.com) で、上部のナビゲーション バーの **[自分のフロー]** を選択し、 **[一から作成]** を選択します。

    ![左側のナビゲーション バーのフロー オプション](./media/get-started-logic-flow/create-logic-flow.png)
1. 画面の下部にある **[Search hundreds of connectors and triggers]\(多数のコネクタやトリガーを検索する\)** ボックスをオンにして、 **[Search all connectors and triggers]\(すべてのコネクタとトリガーを検索する\)** ボックスに「**Twitter**」と入力し、 **[Twitter - When a new tweet is posted]\(Twitter - 新しいツイートが投稿されたら\)** を選びます。

    ![Twitter イベント](./media/get-started-logic-flow/twitter-search.png)

   >[!TIP]
   >コネクタでは、さまざまな種類の認証がサポートされています。 たとえば、SQL Server では、Azure AD、SQL Server 認証、Windows 認証、SQL 接続文字列がサポートされています。 ユーザーは、コネクタの構成時に使用する認証の種類を選択します。

1. 自分の Twitter アカウントを Power Automate にまだ接続していない場合、 **[Sign in to Twitter]\(Twitter にサインイン\)** を選択し、資格情報を入力してください。

1. **[検索文字列]** ボックスに、検索するキーワードを入力します。

    ![Twitter キーワード](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>アクションの指定

1. **[新しいステップ]** を選択し、 **[アクションの追加]** を選択します。

    ![アクションの追加](./media/get-started-logic-flow/add-action-icon.png)

1. **[すべてのコネクタとアクションを検索する]** と表示されているボックスで、「**メールの送信**」と入力するか貼り付けて、 **[Office 365 Outlook - 電子メールの送信]** を選択します。

    ![アクションの一覧](./media/get-started-logic-flow/send-email.png)

1. メッセージが表示されたら、サインイン ボタンを選択し、資格情報を入力します。

1. 表示されたフォームの **[To]** (宛先) ボックスに電子メール アドレスを入力するか貼り付けます。次に、表示された連絡先の一覧から名前を選択します。

    ![空の電子メール メッセージ](./media/get-started-logic-flow/blank-email.png)
1. **[Subject]** (件名) ボックスに「**New tweet from: (新しいツイートの送信元:)** 」と入力するか貼り付け、空白を入力します。

    ![プレースホルダーが含まれる件名](./media/get-started-logic-flow/message-token.png)
1. トークンの一覧で、 **[ツイート作成者]** トークンを選択し、そのプレースホルダーを追加します。

    ![パラメーターの追加](./media/get-started-logic-flow/add-parameter.png)
1. **[本文]** ボックスを選び、 **[ツイート テキスト]** トークンを選んでそのプレースホルダーを追加します。
1. (任意) トークン、その他のコンテンツ、またはその両方を電子メールの本文に追加します。
1. 画面上部でフローに名前を付けて、 **[フローの作成]** を選択します。

    ![[フローの作成] ボタンの選択](./media/get-started-logic-flow/create-button.png)
1. **[完了]** を選んでフローの一覧を更新します。

     ![完了ボタンを選択](./media/get-started-logic-flow/done-button.png)
1. 指定したキーワードを使ってツイートを送信するか、または他のユーザーがそのようなツイートを投稿するまで待ちます。

     ツイートが投稿されてから 1 分以内に、新しいツイートについてメールで通知されます。

> [!TIP]
> **メールの送信 (V2)** アクションを使用し、フォントをカスタマイズするメールの書式を設定したり、太字、斜体、下線を使用したり、色と強調表示をカスタマイズしたり、リストやリンクを作成したりします。

![メールの多機能編集](media/get-started-logic-flow/email-rich-text.png)

## <a name="manage-a-flow"></a>フローの管理

1. [flow.microsoft.com](https://flow.microsoft.com) で、上部のナビゲーション バーの **[自分のフロー]** を選択します。
1. フローの一覧で、次のいずれかを実行します。

   * フローを一時停止するには、 **[オフ]** に切り替えます。

       ![フローの一時停止](./media/get-started-logic-flow/pause-flow.png)
   * フローを再開するには、 **[オン]** に切り替えます。

       ![フローの再開](./media/get-started-logic-flow/resume-flow.png)
   * フローを編集するには、編集するフローに対応している鉛筆アイコンを選択します。

       ![フローの選択](./media/get-started-logic-flow/select-flow.png)
   * フローを削除するには、 **[...]** アイコンを選択し、 **[削除]** を選択し、表示されたメッセージ ボックスで **[削除]** を選択します。

       ![削除アイコン](./media/get-started-logic-flow/delete-icon.png)
   * フローの実行履歴を表示するには、 **[マイ フロー]** ページからフローを選択します。ページの **[実行履歴]** セクションに履歴が表示されます。

       ![実行履歴](./media/get-started-logic-flow/run-history.png)

     実行の一覧からフロー実行を選択して、各ステップの入力と出力を表示します。

> [!NOTE]
> アカウントには最大 600 個のフローを作成できます。 既に 600 個のフローがある場合は、1 つ削除してからフローを作成してください。
>
>

## <a name="next-steps"></a>次の手順

* フローに、さまざまな通知方法などの[ステップを追加](multi-step-logic-flow.md)します。
* アクションを毎日、特定の日付に、または一定時間 (分) 後に実行する場合は、[スケジュールに従ってタスクを実行](run-scheduled-tasks.md)します。
* [フローをアプリに追加](https://powerapps.microsoft.com/tutorials/using-logic-flows/)して、アプリがクラウド内のロジックを開始できるようにします。
* [チーム フローを作成](create-team-flows.md)し、他のユーザーを招待して共同でフローを設計します。
