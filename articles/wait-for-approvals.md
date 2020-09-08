---
title: フローでの承認待ち | Microsoft Docs
description: フローでは、ユーザーが変更を承認または拒否するなどの外部イベントが発生するのを待ってから、決定の通知を送信するなどのアクションを実行できます。
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2018
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4cd78984e505843277e76b8e8c54636b0b001f71
ms.sourcegitcommit: a09a957460f7495c0b103e1d832f65963025fbac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2020
ms.locfileid: "3696887"
---
# <a name="wait-for-approval-in-power-automate"></a>Power Automate で承認を待つ


> [!VIDEO https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]
>

SharePoint で項目を作成した場合に、承認電子メールを担当者に送信し、その項目が承認されたか拒否されたかが、その担当者から通知されるフローを作成します。 このチュートリアルに厳密に従うために、ここではトリガー アクションとしてシンプルな SharePoint リストを作成しますが、Dropbox、OneDrive などの別のデータ ソースを使用することもできます。

## <a name="prerequisites"></a>前提条件

* **Project Tracker** という名前の簡単な SharePoint リストを作成し、**タイトル** という名前の列を追加し、**割り当て先** という名前のユーザー列またはグループ列を追加します。

   ![Project Tracker SPO リストのイメージ](./media/wait-for-approvals/project-tracker.png)

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]

## <a name="add-an-event-to-trigger-the-flow"></a>フローをトリガーするイベントの追加

1. [Power Automate](https://flow.microsoft.com) にサインインし、上部のナビゲーション バーの **マイ フロー** を選んで、**一から作成** を選びます。

1. **多数のコネクタやトリガーを検索する** ボックスを選び、**新しいアイテム** と入力して、**SharePoint - アイテム作成時** に移動します。

1. メッセージが表示されたら、SharePoint にサインインします。
1. **サイトのアドレス** に、リストを含む SharePoint サイトの URL を入力します。

1. **リスト名** で、前に作成したリストを選びます。 説明のとおりに設定してきた場合、名前は **Project Tracker** です。

    ![SPO リスト名のイメージ](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>結果アクションの追加

1. **新しいステップ** ボタンを選んで、**アクションの追加** を選択します。

1. **すべてのコネクタとアクションを検索する** ボックスに、**メールの送信** と入力するか貼り付けて、**Office 365 - 電子メールとオプションの送信** を選びます。

1. メッセージが表示されたら、Office 365 Outlook にサインインします。

1. **宛先** フィールドを選び、**電子メールに割り当て** トークンを選びます。

    **担当者** 列のユーザーがメールを受け取って、項目を承認または拒否します。 フローをテストするために項目を作成する場合は、このフィールドに自身を指定します。 このようにして自分で項目を承認または拒否し、さらにその通知メールも受け取ります。

    > [!NOTE]
    > **件名** フィールドと **ユーザー オプション** フィールドは、ニーズに合わせてカスタマイズできます。

    ![承認の電子メールをフィールドに送信のイメージ](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>条件を追加する

1. **新しいステップ** ボタンを選んで、**条件の追加** を選択します。

    ![条件追加のイメージ](./media/wait-for-approvals/add-a-condition.png)
1. 最初のボックスを選び、**SelectedOption** トークンを選択します。
1. 最後のボックスを選び、**承認** と入力します。

    ![条件カードのイメージ](./media/wait-for-approvals/condition-card-2.png)

1. **はいの場合** の領域で **アクションの追加** を選択します。

1. **すべてのコネクタとアクションを検索する** ボックスに、**メールの送信** と入力するか貼り付けて、**Office 365 - 電子メールを送信** を選びます。

1. **宛先** フィールドに、受信者 (**電子メールで作成** など) を入力します。

1. **件名** ボックスで、件名を指定します。

    たとえば、**DisplayName に割り当て済み** を選択し、両側にスペースを入れて **承認済み** と入力してから、**タイトル** を選択します。

1. **本文** ボックスで、電子メールの本文を指定します (**プロジェクトの次のフェーズに進む準備ができました** など)。

    > [!NOTE]
    > SharePoint リストに項目を作成したユーザーに、プロジェクトが承認されたか拒否されたかが通知されます。

    ![はいの場合の電子メールの送信のイメージ](./media/wait-for-approvals/if-yes-send-email-card-3.png)

1. **いいえの場合** の領域では、プロジェクトが却下されたことを反映するために、**件名** と **本文** を変更する以外は、直前の 5 つの手順を繰り返します。

     ![いいえの場合の電子メールの送信のイメージ](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>フローの完了およびテスト

1. フローに名前を付けて、**フローの作成** を選択します。

     ![フロー作成のイメージ](./media/wait-for-approvals/create-flow.png)
1. SharePoint リストに項目を作成します。

    承認メールが指定した受信者に送信されます。 受信者がそのメールで **承認** または **却下** を選ぶと、メールで返信が届きます。

## <a name="learn-more"></a>詳細はこちら

* [1 人の承認者による最新の承認のチュートリアル](modern-approvals.md)
* [シーケンシャル承認](sequential-modern-approvals.md) を作成する
* [パラレル承認](parallel-modern-approvals.md)を作成する
* [外出先で要求](mobile-approvals.md) を承認する
