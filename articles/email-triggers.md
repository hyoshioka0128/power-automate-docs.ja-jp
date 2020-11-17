---
title: メールのプロパティに基づいてフローを実行する | Microsoft Docs
description: メールの件名、送信者のアドレス、受信者のアドレスなどのプロパティに基づいてフローを開始します。
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
ms.date: 10/16/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a09209e892fb7f1fe5e9244e90996ef54f44818b
ms.sourcegitcommit: 4f57dea6e1579144353d9e1a3ffba455178c11bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "4042574"
---
# <a name="trigger-a-flow-based-on-email-properties"></a>メールのプロパティに基づいてフローをトリガーする

次のメール プロパティの 1 つまたは複数が指定した条件を満たすときに実行されるフローを作成するには、**新しいメールが届いたとき (V3)** トリガーを使用します。

| プロパティ | を使用する場合 |
| --- | --- |
| フォルダー |特定のフォルダーにメールが届くたびにフローをトリガーします。 このプロパティは、メールをさまざまなフォルダーに振り分けるルールを使用している場合に役立ちます。 |
| To |メールの送信先アドレスに基づいてフローをトリガーします。 このプロパティは、異なるメール アドレスに送信されたメールを同じ受信トレイで受信する場合に役立ちます。 |
|CC|メールの CC アドレスに基づいてフローをトリガーします。 このプロパティは、異なるメール アドレスに送信されたメールを同じ受信トレイで受信する場合に役立ちます。
| From |送信者のメール アドレスに基づいてフローをトリガーします。 |
| 重要度 |送信されたメールの重要度に基づいてフローをトリガーします。 メールは高、標準、または低の重要度を指定して送信することができます。 |
| 添付ファイルあり |着信メール内の添付ファイルの有無に基づいてフローをトリガーします。 |
| 件名フィルター |メールの件名に特定の語句がないかどうかを検索します。 その後、フローは検索結果に基づく *アクション* を実行します。 |

> [!IMPORTANT]
> 各 [Power Automate プラン](https://flow.microsoft.com/pricing/) には実行クォータが含まれています。 可能な限り、常にフローのトリガーのプロパティを確認してください。 これにより、実行クォータが不必要に使用されることを回避できます。 条件でプロパティをチェックすると、定義したフィルター条件が満たされない場合でも、すべての実行がプランの実行クォータに対してカウントされます。 

たとえば、条件でメールの *差出人* アドレスをチェックすると、関係する *差出人* アドレスであるかどうかに関わらず、すべての実行がプランの実行クォータに対してカウントされます。
> 
> 

次のチュートリアルでは、**新しいメールが届いたとき (V3)** トリガーですべてのプロパティをチェックします。 詳細については、[課金についてよく寄せられる質問](billing-questions.md#what-counts-as-a-run) と [価格](https://ms.flow.microsoft.com/pricing/) のページを参照してください。

## <a name="prerequisites"></a>前提条件
* [Power Automate](https://flow.microsoft.com) にアクセスできるアカウント
* Microsoft 365 Outlook アカウント
* [Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios)、または [Windows Phone](https://aka.ms/flowmobilewindows) 向けの Power Automate モバイル アプリ
* Office、Outlook、プッシュ通知サービスへの接続

## <a name="trigger-a-flow-based-on-an-emails-subject"></a>メールの件名に基づいてフローをトリガーする
このチュートリアルでは、新しいメールの件名に "lottery" という語が含まれる場合に携帯電話にプッシュ通知を送信するフローを作成します。 その後、そのようなメールには *既読* としてマークが付けられます。

>[!NOTE]
>このチュートリアルではプッシュ通知を送信しますが、ワークフローの必要に適したその他のアクションを自由に使用できます。 たとえば、メールの内容を、Google スプレッドシート、または Dropbox に格納されている Microsoft Excel ワークブックなどの別のリポジトリに格納できます。

それでは開始しましょう。

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. **件名フィルタ―** ボックスで、フロー内で受信メールのフィルター処理に使用するテキストを入力します。
   
     この例では、件名に "lottery" という語が含まれるメールに注目します。
   
    ![詳細オプション](./media/email-triggers/email-triggers-subject-text.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. 先ほど指定した **件名フィルター** に一致するメールが届いたときに受信するモバイル通知の詳細を入力します。
   
    ![通知の詳細を表示するスクリーンショット](./media/email-triggers/email-triggers-4.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. ページ上部にある **保存** を選択します。
   
    ![保存フローオプションを表示するスクリーンショット](./media/email-triggers/email-triggers-subject-notification.png)

ご報告:  これで、件名に "lottery" という語を含むメールを受信するたびにプッシュ通知を受信できます。

## <a name="trigger-a-flow-based-on-an-emails-sender"></a>メールの送信者に基づいてフローをトリガーする
このチュートリアルでは、特定の送信者 (メール アドレス) からのメールが届いた場合に携帯電話にプッシュ通知を送信するフローを作成します。 また、このフローではそのようなメールに *既読* のマークが付けられます。

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. **差出人** ボックスで、送信者のメール アドレスを入力します。 
   
     このアドレスから送信されたすべてのメールに対してアクションが実行されます。
   
    ![メールのプロパティ](./media/email-triggers/email-triggers-from.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. 先ほど入力したメール アドレスからのメッセージが届いたときに受信するモバイル通知の詳細を入力します。
   
    ![通知の詳細](./media/email-triggers/email-triggers-sender-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. フローの名前を指定した後、ページ上部の **フローの作成** を選択することによって保存します。
   
    ![フローを保存する](./media/email-triggers/email-triggers-sender-5.png)

## <a name="trigger-a-flow-when-emails-arrive-in-a-specific-folder"></a>メールが特定のフォルダーに届いたときにフローをトリガーする
アドレスなどの特定のプロパティに基づいてメールをさまざまなフォルダーに振り分けるルールを使用している場合は、この種類のフローを使用できます。

はじめに

> [!NOTE]
> メールを受信トレイ以外のフォルダーに振り分けるルールがまだ存在しない場合は、そのようなルールを作成し、テスト メールを送信することによって動作を確認します。
> 
> 

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-specific-folder](includes/sign-in-use-blank-select-email-trigger-and-specific-folder.md)]

1. 特定のメールをルーティングするフォルダーを選択します。 すべてのメール フォルダーを表示するには、最初に **ピッカーの表示** アイコンを選択します。これは、**新規メール受信時 (V3)** カードの **フォルダー** ボックスの右側にあります。
   
    ![フォルダーの選択](./media/email-triggers/email-triggers-2.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. 先ほど選択したフォルダーにメールが届いたときに受信するモバイル通知の詳細を入力します。 まだである場合は、通知サービス用の資格情報を入力します。
   
    ![通知の詳細](./media/email-triggers/email-triggers-folder-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. フローの名前を指定した後、ページ上部の **フローの作成** を選択することによって保存します。
   
    ![フローを保存する](./media/email-triggers/email-triggers-7.png)

このチュートリアルで先ほど選択したフォルダーに振り分けられるメールを送信することによって、フローをテストします。

