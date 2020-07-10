---
title: 承認要求と共に添付ファイルを送信する | Microsoft Docs
description: 承認要求と共に添付ファイルを送信するフローを作成する方法について説明します。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/29/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c7bc2995b520a7723c56c2f1627d6b877a88648a
ms.sourcegitcommit: 9ee79e5b559429dc0e772b6fed763856dc8b51ee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "3518079"
---
# <a name="create-approval-flows-with-attachments"></a>添付ファイル付きの承認フローを作成する

ビジネスのためにファイルの承認を得る必要がある場合があります。 幸い、Power Automate の承認を使用してこのタスクを行うことができます。 たとえば、あなたは経理担当者で、請求書の承認を得る必要があるとします。この場合、ボタンをタップして送信するファイルを選択するだけで、承認用のファイルを送信できるインスタント フローを作成できます。

この記事では、添付ファイルが送信される承認フローを作成する方法について説明します。承認者は、その要求を承認するべきかどうか判断する前に、その添付ファイルを確認する必要があります。

## <a name="create-the-flow"></a>フローを作成する

1. Power Automate にサイン インする。
1. **マイ フロー** > **新規** > **インスタント - 一から作成** の順に選択します。

    ![新しい空白のインスタント フロー](./media/approval-attachments/new-instand-blank.png)

1. フローに名前を付け、**手動でフローをトリガーします** を検索して選択した後、**作成** を選択します。

    ![フローに名前を付け、トリガーを選択する](./media/approval-attachments/name-flow-trigger.png)

1. **手動でフローをトリガーします** トリガー > **入力の追加** > **ファイル** の順に選択します。

     前の手順により、フローを実行したときに、ユーザーからファイルを要求してフローをトリガーするようにフローが構成されます。

1. **新しいステップ**を選択
1. **承認**を検索して、**承認の開始と待機** を選択します。
1. **承認の開始と待機** カードの **承認の種類** 一覧から **承認/拒否 - 最初に応答** を選択します。
1. **承認の開始と待機** カードに次の情報を入力します。

   - **タイトル** - 承認者に要求の内容を示す簡単な説明です。
   - **割り当て先** - 要求の送信先となるユーザーです。
   - **詳細** - このテキストは承認要求に表示されます。

     ![承認要求カード](./media/approval-attachments/approval-request-card.png)

1. **詳細オプションの表示** を選択して、要求に添付するファイルに関する情報を指定するフィールドを表示します。
1. **添付ファイル名 - 1** にファイル名を指定します

   >[!TIP]
   >アップロードするファイルの種類と一致するファイル拡張子を含める必要があります。

1. **添付ファイルのコンテンツ - 1** ボックスに、承認者に送信されるファイルのコンテンツを指定します。 

   この操作を簡単に行うには、**添付ファイルのコンテンツ - 1** ボックスを選択したときに表示される動的コンテンツの一覧から、**ファイルのコンテンツ** 項目を使用します。

     ![承認要求カードの詳細オプション](./media/approval-attachments/approval-request-card-advanced-options.png)

1. **保存**を選択して、 フローを保存します。

## <a name="test-your-flow"></a>フローをテスト

フローをテストするには、**テスト** を選択してから、.xlsx ファイルをアップロードします。

1. **テスト**を選択します。
1. **トリガーアクションを実行する** を選択します。

     ![フローをテスト](./media/approval-attachments/test-flow.png)

1. テストを開始するには、**テスト** > **続行** を選択します。
1. **インポート** を選択します。

     ![インポート ボタンを選択](./media/approval-attachments/import-file.png)
1. ファイルを見つけて選択した後、**開く** を選択して、承認用に送信するファイルまたは画像をアップロードします。

1. **フローの実行**を選択します。

   テストの実行が開始されます。

     ![テストの開始](./media/approval-attachments/test-started.png)

1. テストの状態を監視するには、**フロー実行ページ** を選択します。

## <a name="approve-the-request"></a>要求を承認する

承認要求の送信先にしたユーザーは、次の画像のようなメールを受信します。ここで、そのユーザーは添付ファイルを表示してから、要求を **承認** または **拒否** することができます。

![要求のメールを表示する](./media/approval-attachments/approval-request-mail.png)

>[!TIP]
>承認者は、承認センターでも要求を確認できます。

## <a name="learn-more"></a>詳細はこちら

ほとんどの承認フローでは、決定の承認を要求したユーザーに通知することをお勧めします。 承認フローに**条件**を追加して、要求の**結果**に基づいて特定のアクションを実行する方法については、[最新の承認に関する記事](modern-approvals.md#add-an-email-action-for-approvals)を参照してください。

