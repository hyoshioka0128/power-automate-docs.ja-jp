---
title: bttn でフローを開始する | Microsoft Docs
description: bttn でフローを開始する方法について説明する
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
ms.date: 05/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4eaafb1a551cc3333cde2058aebc41076b0267bd
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79194165"
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>Button Corporation (プレビュー) から物理ボタン (bttn) でフローを実行する

フローをトリガーするには、bttn ([Button Corporation](https://my.bt.tn/) によって作成された物理ボタン) を押します。 たとえば、以下のタスクを実行するフローをトリガーする bttn を押すことができます。

* 位置情報を使用してヘルプデスクに問い合わせる
* 自分のチームに電子メールを送信する
* 予定表をブロックする
* 供給物を並べ替える

> [!IMPORTANT]
> bttn は、フローで使用する前に[登録](https://my.bt.tn/)する必要があります。
> 
> [!TIP]
> フローを作成する前に、[bttn Web サイト](https://my.bt.tn/)で名前、場所、電子メール アドレスなどのすべての bttn プロパティを構成してください。
> 
> 

[Flic 物理ボタン](flic-button-flows.md)を使用してフローをトリガーすることもできます。

## <a name="prerequisites"></a>前提条件
* [Power Automate](https://flow.microsoft.com) へのアクセス。
* 少なくとも 1 つの[登録済み bttn](https://my.bt.tn/) がある

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>bttn によってトリガーされるフローを作成する
このチュートリアルでは、ヘルプデスク テンプレートを使用して、[bttn](https://my.bt.tn/) を 1 回押すだけでトリガーできるフローを作成します。 フローを実行すると、サポート要求が生成されてヘルプデスクに送信されます。 サポート要求により、ヘルプが必要な部屋の位置がヘルプ デスクに提供されます。 このチュートリアルではテンプレートからこのフローを作成する方法を示しますが、フローのすべての側面を完全に制御できる空のテンプレートを使用することもできます。

これらのテンプレートのいずれかを使用すると、bttn 用のフローを簡単に作成し、Zendesk、Google、SharePoint などに接続できます。

![bttn のテンプレート](./media/bttn-button-flows/bttn-templates.png)

ヒント:このチュートリアルの目的上、bttn には一般的なオフィス ビル内の会議室を表す名前を付けます。

bttn の設定は (bttn Web サイトからの) この例のようになります。

![bttn のテンプレート](./media/bttn-button-flows/bttn-config.png)

これで、bttn を登録して構成できました。フローの作成を開始しましょう。

### <a name="sign-in-and-select-a-template"></a>サインインしてテンプレートを選択する
1. [Power Automate](https://flow.microsoft.com) にサインインします。
   
    ![サインイン](./media/bttn-button-flows/sign-into-flow.png)
   
    注意:代わりに、[Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios)、または [Windows Phone](https://aka.ms/flowmobilewindows) 用の Power Automate モバイル アプリでフローを作成することもできます。
2. 検索ボックスに「**bttn**」と入力し、検索アイコンを選択します。
   
    ![検索](./media/bttn-button-flows/bttn-search-template.png)
   
    検索アイコンを選択した後、bttn とともに使用できるすべてのテンプレートが表示されます。
3. **Use Bttn to call technical support for meeting room (bttn を使用して会議室の技術サポートを呼び出す)** テンプレートを選択します。
   
    ![サポート テンプレート](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-power-automate-to-connect-to-your-bttn"></a>自分の bttn に接続する許可を Power Automate に与える
1. メッセージが表示されたら、bttn および Office 365 Outlook サービスにサインインします。これによって **[続行]** ボタンが有効になります。
   
    ![資格情報](./media/bttn-button-flows/bttn-provide-credentials.png)
2. bttn サービスにサインインする際、Power Automate が bttn を使用することを承認します。
   
    **重要**: Power Automate が bttn を使用することを承認しないと、Power Automate から bttn を表示して接続することができません。
   
    ![承認](./media/bttn-button-flows/authorize-bttn.png)
3. 両方のサービスにサインインした後、 **[続行]** を選択します。
   
    ![続行](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>フローをトリガーする bttn を選択する
1. **[When a bttn is pressed]\(bttn が押されたとき)** カードで、bttn ID の一覧を開き、使用する bttn を選択します。
   
    ![bttn を選択する](./media/bttn-button-flows/bttn-id.png)
   
    フローはこの例のようになります。
   
    ![フローの概要](./media/bttn-button-flows/bttn-done.png)
2. フローに名前を付けて、 **[フローの作成]** を選択して保存します。
   
    ![フローの保存](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>フローをテストして結果を確認する
1. bttn 上のボタンを押します。
2. フローの実行履歴を表示し、正常に実行されたことを確認します。
   
    実行履歴は Power Automate Web サイトまたはモバイル デバイス上でチェックすることができます。
   
    注意:他のユーザーがサポート リクエスト電子メールで **[Acknowledge]\(確認)** を選択するまで、実行状態は **running (実行中)** に設定されます。
3. サポート チームに電子メールが送信されたことを確認することもできます。
   
    これまでのステップに従った場合、サポート電子メールは次の例のようになります。
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>トラブルシューティング
* フローがトリガーされなかった場合、Button Corporation のサイトにサインインし、ボタン アクティビティ (ボタン押し) が記録されているかどうかを確認します。
* Power Automate サイトで実行済みアクティビティをドリル ダウンし、エラー メッセージがないかどうかをチェックすることもできます。

## <a name="more-information"></a>詳細
* [ボタン フローを共有する](share-buttons.md)
* [ボタン トリガー トークン](introduction-to-button-trigger-tokens.md)を使用してボタン フローの実行時に現在のデータを送信する方法について説明します。
* [Android 向け Power Automate アプリをインストールする](https://aka.ms/flowmobiledocsandroid)。
* [iOS 向け Power Automate アプリをインストールする](https://aka.ms/flowmobiledocsios)。

