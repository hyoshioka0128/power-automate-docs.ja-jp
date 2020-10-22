---
title: スマートフォンでフローを作成する | Microsoft Docs
description: たとえば、指定したアドレスからメールを受信した際に、プッシュ通知を送信するフローをテンプレートから作成します
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/18/2020
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4b0dfb8efd5781e67f569bafddbf223ba2105f7e
ms.sourcegitcommit: 772a71443a19ce3da5e02470eda849762ad83671
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "3821009"
---
# <a name="create-a-flow-from-your-phone-by-using-power-automate"></a>Power Automate を使用して携帯電話からフローを作成する

テンプレートを使用してスマートフォンからフローを作成します。テンプレートを見つけるには、サービスの一覧から検索するか、カテゴリを参照するか、キーワードを指定します。

このトピックの手順では、上司からメールを受け取るとプッシュ通知をスマートフォンに送信するフローを作成します。

Power Automate に慣れていない場合は、[概要を確認してください](getting-started.md)。

## <a name="prerequisites"></a>前提条件
* [Power Automate の取引先企業](sign-up-sign-in.md)。
* [Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios)、[Windows Phone](https://aka.ms/flowmobilewindows) 向けの Power Automate モバイル アプリがインストールされた [対応している デバイス](getting-started.md#use-the-mobile-app)。 このトピックのグラフィックは iPhone バージョンのアプリを示していますが、インターフェイスは Android デバイスまたは Windows Phone にも共通しています。
* このトピックで示すテンプレートを使用する場合は、以下も必要です:
  
  * Office 365 の資格情報。
  * スマートフォンでプッシュ通知を有効化すること。

## <a name="find-a-template"></a>テンプレートを探す
1. モバイル アプリを開いて画面下部の **参照** をタップします。
   
    ![参照アイコン](./media/mobile-create-flow/browse-icon.png)
   
    次の方法でテンプレートを検索できます:
   
   * 画面上部の検索ボックスにキーワードを指定します。
   * サービス一覧からオプションをタップします。
   * 下にスクロールして詳細なカテゴリを表示し、任意のカテゴリのテンプレートをタップします。
     
  
       ![[参照] タブ](./media/mobile-create-flow/browse-tab.png)
     
     このチュートリアルでは上司からメールを受け取るとプッシュ通知を送信するテンプレートを開きます。
1. サービス一覧から **すべて表示** をタップします。
   

    ![サービス一覧を表示する](./media/mobile-create-flow/list-services.png)
1. **通知** サービスのアイコンをタップします。
    
    ![プッシュ通知](./media/mobile-create-flow/push-notifications.png)
1. 検索バーに **上司** と入力して、上司からメッセージを受け取るとプッシュ通知を送信するテンプレートをタップします。
   
  
    ![テンプレートの選択](./media/mobile-create-flow/choose-template.png)
1. 選択したテンプレートの詳細を表示した画面で **このテンプレートを使用する** をタップします。
   
    ![テンプレートを確認する](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>フローを完了する
1. メッセージが表示されたら、**サインイン** をタップし、 Office 365 Outlook か Office 365 ユーザー、またはその両方の資格情報を指定します。
   
    ![Office 365 にサインインする](./media/mobile-create-flow/office-signin.png)
   
    >[!TIP]
    >他のフローを作成する際も同じ接続を使用できます。

1. 右上隅にある **作成** をタップします。
   
    ![[作成] をタップする](./media/mobile-create-flow/create.png)

      
    フローを作成しました。フローを一時停止または削除するまで上司からのメールを確認します。

    ![完成したフロー](./media/mobile-create-flow/success.png)

## <a name="next-steps"></a>次の手順
* [フロー アクティビティを監視します](mobile-monitor-activity.md)。
* [フローを管理します](mobile-manage-flows.md)。

