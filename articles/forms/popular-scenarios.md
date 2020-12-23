---
title: 主なシナリオ | Microsoft Docs
description: Microsoft Forms 内のフローを使用する一般的なシナリオ。
services: ''
suite: flow
documentationcenter: na
author: Dean-Haas
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2020
ms.author: napienko
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0753987cf21e5ecc76510109cea6fdb6303b255a
ms.sourcegitcommit: cdc567f1760c85fa8030b17a6c158254b92d16bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "4723457"
---
# <a name="top-scenarios"></a>主なシナリオ

Power Automate でフォームを使用できる主なシナリオのいくつかを次に示します。

- 新しいフォームの回答があったときに電子メールを送信します。
- 回答を送信した後、フォームの回答者に電子メールを送信します。
- フォームの内容を記載した承認を送信します。
- Microsoft Forms の回答を Excel にアップロードします。
- フォームから添付ファイルを取得し、添付ファイル付きの電子メールを送信します。

## <a name="send-an-email-when-there-is-a-new-form-response"></a>新しいフォームの回答があったときに電子メールを送信する

Microsoft Form 設定内で「各回答の電子メール通知を取得する」という通知を有効にすることはできますが、Power Automate を使用してカスタマイズされた電子メール通知を作成することもできます。

まず、[回答が送信されたとき](/connectors/microsoftforms.md/#triggers)のトリガーを追加します。

フォームが組織内のユーザーのみを対象としている場合は、フォームは自動的に回答者の電子メールを記録しているため、[それぞれに適用] コントロールを使用する必要があります。 デモはこのシナリオを示し、「回答通知の回答 ID 一覧」を選択するよう求めます。 ただし、フォームが公開されていて、リンクを知っている人なら誰でも返信できる場合は、フォームの返信として電子メールを要求する必要があり、[それぞれに適用] コントロールを追加する必要はありません。

   > [!div class="mx-imgBorder"]
   > ![設定画面](..\media\forms\only-people-in-my-org-setting.png "このフォームに記入できるユーザーを示す画面")

次に、[回答の詳細の取得](/connectors/microsoftforms/#actions)アクションを追加します。 動的コンテンツを表示するには、[回答 ID] テキスト フィールドをクリックします。 [回答 ID] オプションを選択します。これは、トリガーの原因となった回答の詳細を取得することを意味します。 その後、[電子メールの送信 (V2)](/connectors/office365/#send-an-email-(v2)) アクションを選択します。 アクション カード内で、[動的コンテンツの追加] をクリックして、電子メールでフォームの回答を使用できるようにします。



## <a name="send-an-email-to-the-form-responder-after-they-submit-a-response"></a>回答を送信した後、フォームの回答者に電子メールを送信する

Microsoft Form 設定内で、[電子メールのレシートを回答者に送信](https://support.microsoft.com/office/send-an-email-receipt-of-responses-951f29b7-dbd8-446b-8ebe-b924cc620bb20)の通知を有効にすることはできますが、Power Automate を使用してカスタマイズされた電子メール通知を作成することもできます。
これは、[電子メールの送信 (V2)](https://docs.microsoft.com/connectors/office365/#send-an-email-(v2)) アクションが回答者に送信されていることを除いて、主なシナリオ #1 と似ています。

## <a name="send-an-approval-with-contents-of-the-form"></a>フォームの内容を記載した承認を送信する

フォームの動的コンテンツを使用して承認を作成します。 この例では、コンテンツはフィードバックであり、「製品の何を改善できるか?」という質問で表されます。

Microsoft Forms トリガーとアクションを追加した後、3 番目のステップは[開始して承認を待機](/modern-approvals#add-an-approval-action.md)するアクションです。

   > [!div class="mx-imgBorder"]
   > ![開始して承認を待機するフロー画面](..\media\forms\flow-start-and-wait-for-approval.png "開始して承認を待機する完成したフローを示す画面")

[ドキュメント](/sequential-modern-approvals.md)で他の承認例を確認できます。

## <a name="upload-microsoft-forms-responses-to-excel"></a>Microsoft Forms の回答を Excel にアップロードする

新しい Excel Online シートを作成し、シートにテーブルを追加します。 [Excel ドキュメント](https://support.microsoft.com/en-us/office/overview-of-excel-tables-7ab0bb7d-3a9e-4b56-a3c9-6c94334e492c)でテーブルの詳細を確認できます。

   > [!div class="mx-imgBorder"]
   > ![Excel 画面](..\media\forms\excel.png "例の列を含む空白の Excel テーブルを示す画面")

   > [!div class="mx-imgBorder"]
   > ![Excel フロー画面](..\media\forms\excel-flow.png "完成した Excel フローを示す画面")

回答を Excel シートに入力する前に、承認を追加して回答を承認することもできます。 [Microsoft Forms の回答を承認して Excel スプレッドシートに行を追加する](https://preview.flow.microsoft.com/galleries/public/templates/66f56b919fd64aeabec37245ed927c47/approve-a-microsoft-forms-response-to-add-a-row-to-an-excel-spreadsheet/)のテンプレートが役立ちます!

## <a name="get-an-attachment-from-a-form-and-send-it-in-an-email-message"></a>フォームから添付ファイルを取得し、電子メール メッセージで送信する

回答者がファイルをアップロードするためのセクションをフォームに追加したことを確認してください。
   > [!div class="mx-imgBorder"]
   > ![フォームのアップロード セクション](..\media\forms\forms-upload.png "フォームのアップロード セクションを示す画面")

フォームのトリガーとアクションを追加した後、JSON の解析アクションを追加します。 このアクションを追加する前にフローを実行して、サンプルから JSON スキーマを生成することをお勧めします。
   > [!div class="mx-imgBorder"]
   > ![JSON の解析アクション](..\media\forms\flow-parse-json.png "JSON の解析アクションを追加する")

サンプル全体を貼り付けたら、OneDrive から[パスを使用してファイルのコンテンツを取得](/connectors/onedrive/#get-file-content-using-path)して Microsoft Form を見つけることができます。 次に、‘/’ の後に次の式を追加します: **first(body('Parse_JSON'))?['id']**。 これにより、回答者がアップロードする 1 つのファイルが抽出されます。 
   > [!div class="mx-imgBorder"]
   > ![共有リンクの作成](..\media\forms\create-share-link.png "Power Automate で「共用リンクを作成」する")

最後に、Office 365 から[電子メールの送信 (V2)](/connectors/office365/#send-an-email-(v2)) アクション カードを使用して、そのアップロードを電子メールで送信できます。 式 **first(body('Parse_JSON'))?['id']** を含めます
 
ここでブログ投稿を調べることにより、フォームから添付ファイルを取得するシナリオと承認フローを作成するシナリオを組み合わせることができます。
