---
title: Power Automate で Microsoft 365 メールをカスタマイズする | Microsoft Docs
description: Power Automate を使用して Microsoft 365 メールをカスタマイズします。
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
ms.openlocfilehash: ab795e0758444d83cf3cee00e8accf9c978ff597
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709698"
---
# <a name="customize-email-in-flows"></a>フロー内のメールをカスタマイズする


Power Automate のメールに関するシナリオの方法のトップは次の通りで、それらをアーカイブする例も含みます。

1. [美しくフォーマットされたメール](#send-a-beautifully-formatted-email) を送信します。

1. メールに[イメージを追加](#add-an-image-to-your-email) 追加します。

1. [配布リストへのメール](#send-email-to-a-distribution-list) を送信します。

1. [共有メールボックス](#send-automatic-replies-from-a-shared-mailbox) からの自動返信を送信します。

1. メールの [日付と時刻の形式](#change-the-date-and-time-format-of-an-email) を変更します。


## <a name="send-a-beautifully-formatted-email"></a>美しくフォーマットされたメールを送信する 

HTML を使用してメールを美しくフォーマットできます。 以下は、HTML でメッセージを美しくするために使用できる 2 つのオプションです。

### <a name="option-1-write-html-directly-into-the-flow"></a>オプション 1: HTML をフローに直接書き込む

1. Power Automate デザイナーのリッチ テキスト エディター内にある **\</\>** ボタンを選択します。 

   ![メールの本文に HTML を入力できるボタンのスクリーンショット](./media/email/html-button.png)

1. メールの本文にあらゆる HTML コンテンツを入力します。

### <a name="option-2-copy-html-from-an-outlook-email"></a>オプション 2: Outlook のメールから HTML をコピーする

または、HTML がわからない場合、または HTML を使いたいと思わない場合は、次の手順に従ってください。

1. Outlook でメールを作成し、色、コンテンツ プレースホルダー、画像、テーブルなどでスタイルを設定します。
1. あなた自身にメールを送ります。
1. 自分宛に送信したメールを Outlook で開きます。 必ず新しいウィンドウを使用してください。 Outlook のプレビュー ウィンドウは使用しないでください。
1. **メッセージ** タブ > **その他のアクション** > **その他のアクション** > **ソースを表示** の順に移動します。

   ![Outlook で**その他のアクション**メニューを表示する手順を示すスクリーンショット](./media/email/other-actions.png)

   メールの HTML 表現がテキスト エディタで開きます。 
   
1. ファイルで **\<html\>** を検索します。 
1. **\<html\>** と **\</html\>** 間でコンテンツをコピーします。 
1. Power Automate に戻り、リッチ テキスト エディタの **メールを送る** アクションの **\</\>** ボタンをクリックし、Outlook からコピーしたコンテンツを貼り付けます。

## <a name="add-an-image-to-your-email"></a>イメージをメールに追加する

Outlook は、メールに含めた画像を取得して、プレーン テキストに変換します。 プレーン テキストをコピーして Power Automate に貼り付ける代わりに、次の手順を実行します。 

1. Google ドライブ、OneDrive for Business などのクラウド ベースのストレージに画像をアップロードします。 
1. イメージに匿名の訪問者 URL を取得します。 
1. Power Automate **メールを送る** アクションで、リッチ テキスト エディタの HTML セクションに移動し、HTMLで **\<image src=** を検索し、**src** プロパティの値を、イメージをアップロードしたクラウド ベースのストレージ プロバイダーからのイメージの URL へ変更します。 

   **src** は、**\<image src="https://url/to/your/images.png"/\>** と類似したものになる必要があります。

   >[!IMPORTANT]
   >インライン イメージは 100KB サイズに制限されています。 これは、イメージの品質に影響を与える可能性があります。

## <a name="send-email-to-a-distribution-list"></a>配布リストにメールを送信する

**メールを送る** アクションは、メールが有効化されたセキュリティ グループまたは配布リストにメッセージを送信できます。 メールが有効なセキュリティ グループまたは配布リストの各メンバーは、自分のメールボックスではなく、グループのメールボックスでメールを受信します。 

または、ユーザーがメールボックスでメールを受信できるようにする場合は、次の手順に従います。 

1. [Azure AD](https://docs.microsoft.com/connectors/azuread/) コネクタから、[グループ メンバーの取得](https://docs.microsoft.com/connectors/azuread/#get-group-members) アクションを追加して、配布リストを選択します。

1. アクション **Azure AD-Get グループ メンバー** で、**各自に適用** アクションを追加します。

1. **各自に適用** 内で、**メールを送る** アクションを追加し、**グループメンバーを取得する** アクションから **送信先** フィールドの動的コンテンツとしてグループ メンバーを追加します。

   ![すべてのグループメンバーを取得し、各メンバーにメールを送信するクラウド フローのスクリーンショット](./media/email/group-members-flow.png)


## <a name="send-automatic-replies-from-a-shared-mailbox"></a>共有メールボックスからの自動返信を送信する

これは Outlook Web App で実行できる

1.  ご使用の Office 365 資格情報を使い、[https://outlook.office365.com](https://outlook.office365.com/) で Outlook Web App にログインします。

1.  右上のプロフィール画像 (またはプレースホルダー イメージ) を選択します。

1.  **別のメールボックスを開く。** を選択する

1.  共有メールボックスの名前またはメール アドレスを入力して選択します。

1.  右上で **アイコンの設定** を選択し、**自動返信する。** を選択する

1.  自動返信を設定します。 完了しました。

### <a name="change-the-date-and-time-format-of-an-email"></a>メールの日付と時刻の形式を変更する 

規定では、受信するメールに UTC タイムゾーンが表示されます。 ただし、ユーザーはそれをローカル タイムゾーンに変更したい場合があります。 この[記事](https://support.microsoft.com/help/4557244/converting-time-zone-in-microsoft-power-automate) の手順に従い、タイム ゾーンを変換します。


## <a name="more-information"></a>詳細情報

- [フロー付きのメール](email-overview.md) の概要
- [メールを管理するフロー](create-email-flows.md) を作成する
- トップの[メールに関するシナリオ](email-top-scenarios.md)


