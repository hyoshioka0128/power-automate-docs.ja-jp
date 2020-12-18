---
title: フローを作成してタスクを自動化する | Microsoft Docs
description: フローを作成して、イベント (SharePoint  リストに行を追加するなど) が発生したときに 1 つ以上のアクション (メールの送信など) を自動的に実行します。
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
ms.openlocfilehash: ca1a7f570eb76528c8d384cd08f92bb816f1e397
ms.sourcegitcommit: df7fb20065cfafc153b4bc4019dff2c94f4ef567
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "4553172"
---
# <a name="create-a-flow-in-power-automate"></a>Power Automate でフローを作成する

イベントによってトリガーされたら 1 つまたは複数のタスクを自動的に実行するフローを作成します。 たとえば、指定したキーワードを含むツイートを送信した場合にメールで通知するというフローを作成するとします。 この例では、ツイートを送信するのがイベント、メールを送信するのがアクションです。

## <a name="prerequisites"></a>前提条件

* [flow.microsoft.com](https://flow.microsoft.com) のアカウント
* Twitter アカウント
* Office 365 の資格情報

## <a name="specify-an-event-to-start-the-flow"></a>フローを開始するイベントを指定する

最初にフローを開始するイベントや *トリガー* を選択する必要があります。

1. [Power Automate](https://flow.microsoft.com) で左側のナビゲーション バーから **マイ フロー** を選択します。

1. **新規** を選択した後、**ブランクから自動作成** を選択します。 

    <!-- ![Flows option in the left navigation bar](./media/get-started-logic-flow/create-logic-flow.png) -->

1. **名前の追加もしくは名前の生成** フィールドでフローに名前を付けます。

1. **すべてのトリガーを検索する** フィールドに **Twitter** と入力します。

1. **Twitter - 新しいツイートの投稿時** を選択します。

   ![フローに名前を付けて Twitter トリガーを検索します](./media/get-started-logic-flow/name-search-trigger.png)


<!-- 1. Select the **Search hundreds of connectors and triggers** box at the bottom of the screen, enter **Twitter** in the box that says **Search all connectors and triggers**, and then select **Twitter - When a new tweet is posted**.

    ![Twitter event](./media/get-started-logic-flow/twitter-search.png) -->

1. 画面の下部にある **作成** ボタンを選択します。


   >[!TIP]
   >コネクタはさまざまな種類の認証をサポートします。 たとえば、SQL Server では、 Azure AD、SQL Server 認証、Windows 認証、SQL 接続文字列がサポートされています。 ユーザーはコネクタの構成時に使用する認証の種類を選択します。

1. Power Automate にまだ Twitter アカウントを接続していない場合は、**Twitter にサインインする** を選択し、資格情報を入力します。

1. **検索するテキスト** ボックスに、検索するキーワードを入力します。

    ![Twitter キーワード](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>アクションを指定する

1. **新しいステップ** を選択します。

    <!-- ![Add action](./media/get-started-logic-flow/add-action-icon.png) -->

1. **コネクタとアクションを検索する** と表示するボックスに **メールを送信する** と入力して **メールを送信する (V2)** を選択します。

    ![アクションの一覧](./media/get-started-logic-flow/send-email.png)

1. プロンプトが表示されたら [サインイン] ボタンを選択し、資格情報を入力します。

1. 表示されたフォームの **宛先** ボックスに電子メール アドレスを入力し、表示された取引先担当者の一覧から名前を選択します。

1. **件名** ボックスに **新しいツイートの送信元** と入力してから、空白を入力します。

    ![プレースホルダー付きの件名](./media/get-started-logic-flow/message-token.png)
1. トークンのリストで **ツイートの投稿者** トークンを選択して、そのプレースホルダーを追加します。

    ![パラメーターを追加する](./media/get-started-logic-flow/add-parameter.png)
1. **本文** ボックスを選択し、次に **ツイート テキスト** トークンを選択してからプレースホルダーを追加します。

   オプションで、トークン、他のテキスト、またはその両方をメール本文に追加できます。
1. 画面上部付近から **保存** を選択します。

    <!-- ![Select the Create flow button](./media/get-started-logic-flow/create-button.png) -->
<!-- 1. Select **Done** to update the list of flows.

     ![Select the done button](./media/get-started-logic-flow/done-button.png) -->

## <a name="test-your-flow"></a>フローをテスト

キーワードを指定してツイートを送信するか、他のユーザーが該当するツイートを投稿するまで待ちます。

ツイートが投稿されてから 1 分以内に、新しいツイートについてメールで通知します。

> [!TIP]
> **メールを送信する (V2)** アクションを使用して、フォントのカスタマイズ、太字、斜体、下線の使用、色とハイライトのカスタマイズ、リストやリンクの作成など、メールの書式を設定します。

![メールを多機能編集する](media/get-started-logic-flow/email-rich-text.png)

## <a name="manage-a-flow"></a>フローの管理

1. [Power Automate](https://flow.microsoft.com) で左側のナビゲーション バーから **マイ フロー** を選択します。
1. フローの一覧から次のいずれかを実行します:

   * フローを一時停止する場合は、切り替えを **オフ** に設定します。

       ![フローを一時停止する](./media/get-started-logic-flow/pause-flow.png)
   * フローを再開する場合は、切り替えを **オン** に設定します。

       ![フローを再開する](./media/get-started-logic-flow/resume-flow.png)
   * フローを編集する場合は、編集するフローに対応する鉛筆アイコンを選択します。

       ![フローを選択します](./media/get-started-logic-flow/select-flow.png)
   * フローを削除する場合は、**...** アイコンを選択して **削除** を選択し、表示されるメッセージ ボックスで **削除** を選択します。

       ![[削除] アイコン](./media/get-started-logic-flow/delete-icon.png)
   * フローの実行履歴を表示する場合は **マイ フロー** ページからフローを選択し、開いたページの **28 日間の実行履歴** セクションで履歴を確認します。

       ![実行履歴](./media/get-started-logic-flow/run-history.png)

     実行リストからフロー実行を選択して、各ステップの入力と出力を確認します。

> [!NOTE]
> 1 つのアカウントが持てるフローは最大 600 件です。 既に 600 件のフローがある場合は、1 つ削除してからフローを作成してください。
>
>

## <a name="next-steps"></a>次の手順

* さまざまな通知方法など、フローに [手順を追加します](multi-step-logic-flow.md)。
* 毎日、特定の日付、特定の分数ごとにアクションを実行する場合は、[スケジュールに従ってタスクを実行します](run-scheduled-tasks.md)。
* [アプリにフローを追加して](https://powerapps.microsoft.com/tutorials/using-logic-flows/)、クラウドでアプリがロジックを開始可能にします。
* [チーム フローを開始し](create-team-flows.md)、他のユーザーを招待して一緒にフローを設計します。
