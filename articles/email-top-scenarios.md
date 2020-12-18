---
title: 上位 Office 365 Outlook のシナリオ | Microsoft Docs
description: トップ Office 365 Outlook のシナリオ。
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
ms.date: 11/10/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: cffe4c29ca819b903f7cde8e2f97e262e280bd5b
ms.sourcegitcommit: 83f74a9693056aad121481ecf38691b999441104
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "4513177"
---
# <a name="create-flows-for-popular-email-scenarios"></a>一般的なメール シナリオのフローを作成する

メールを管理するために Power Automate を使用できる主なシナリオのいくつかを次に示します:

1. アカウントからのメールを送信します。

1. 配布リスト (DL) または共有メールボックスからメールを送信します。

1. オプションを投票してメールを送信します。

1. *承認* プロセスを構築してメールで同僚に通知します。

1. *リマインダー* メールを承認者に送信します。

1. 要約表を含むダイジェスト メールを毎日送信します。

## <a name="send-email-from-your-account"></a>自分のアカウントからのメールの送信

自分のアカウントからメールを送信するには、[メールを送信する (V2)](https://docs.microsoft.com/connectors/office365/#send-an-email-(v2)) アクションを使用します。 

1 人以上の受信者にメールを送信できます。 リッチ テキスト エディタを **太字** へ使用して、Outlook で行うのと同じように、色を追加し、メールをフォーマットします。 動的コンテンツを使用して、前のアクションから静的テキストまたは値を追加できます。 **代理人として送信** オプションを使用して、メールを他の誰かとして、または他の誰かに代わってメールを送信できます。 Outlook の **送信済みアイテム** フォルダの送信したすべてのメールを見つけることができます。 このオプションを使用するには、他の人に代わって送信するための Outlook のアクセス許可が必要です。

たとえば、アイテムが承認されるとメールを送信するフローがある場合、承認されたアイテムのリンクを添付ファイルとして追加できます。

![メールの本文で動的コンテンツを使用するメールの例を表示するスクリーンショット](./media/email/dynamic-content.png)

## <a name="send-email-with-voting-options"></a>オプションを投票してメールを送信する

<!--todo add a link to actionable email-->
**オプション付きのメールを送信する** アクションを使用して、*実用的* メールを使用して投票オプションを含むメールを送信します。 ユーザー オプション フィールドを使用して、投票オプションを提供します。

   !["オプション付きのメールを送信" カードを示すスクリーンショット](./media/email/email-options.png)

受信者は、次のようなメールを受信します。

   ![投票ボタン付きメールのスクリーンショット](./media/email/voting-buttons.png)

フローでは、投票された返信をキャプチャして、どこかに保存する必要があります。 メールの送信、Excel への保存、Teams への投稿ができます。ユーザーが何を選択したかがわからなくなるので、必ず保存してください。

## <a name="send-an-email-from-a-distribution-list-dl-or-shared-mailbox"></a>配布リスト (DL) または共有メールボックスからメールを送信する

[共有メールボックスからメールを送信する (V2)](https://docs.microsoft.com/connectors/office365/#send-an-email-from-a-shared-mailbox-(v2)) アクションを使用して、共有メールボックスからメールを送信する共有メールボックス アドレスを指定します。 

配布リスト (DL) 管理者は、最初にあなたに共有メールボックスへの [権限](https://docs.microsoft.com/microsoft-365/admin/manage/send-email-as-distribution-list?view=o365-worldwide) を与える必要があります/このアクションを使用すると、それはそのアカウントから直接送信されるため、共有メールボックスの送信済みフォルダーにメールが表示されます。

![共有メールボックス (V2) カードからメールを送信することを示すスクリーンショット](./media/email/shared-mailbox.png)

## <a name="build-an-approval-process-and-send-notifications-via-email"></a>承認プロセスを構築してメールを通じて通知を送信する 

Power Automate を使用して、[メールでユーザーに通知する承認プロセスを構築](https://o365hq.com/blog/build-an-approval-process-with-power-automate) できます。

## <a name="send-reminder-email-to-approvers"></a>リマインダー メールを承認者に送信する

[承認リクエストのリマインダー メール](https://flow.microsoft.com/blog/approval-reminders-using-parallel-branches) を送信することもできます。

## <a name="send-a-daily-digest-email-with-a-table"></a>テーブルを持つダイジェスト メールを毎日送信する

テーブル付きの毎日のダイジェスト メールを送信できる 3 つの方法は次のとおりです。

1. [データ操作 – 選択](https://docs.microsoft.com/power-automate/data-operations#use-the-select-action) アクションを使用して、メールに表示する列名とデータを含むテーブルを作成します。
式を使用してデータをさらにフォーマットできます。 次の例では、このフローは概算時間の間のカレンダー イベントを取得し、タイムゾーンを変換してから、イベントを含むテーブルを作成します。

   ![テーブル付きのフローの例を示しているスクリーンショット](./media/email/table.png)

1. [HTML テーブルを作成する](https://docs.microsoft.com/power-automate/data-operations#use-the-create-html-table-action) アクションを追加してから、選択アクションからの出力を HTML アクションに追加します。

1. [メールを送信する (V2](https://docs.microsoft.com/connectors/office365/#send-an-email-(v2)) アクションを追加して、HTML テーブルからの出力をメールの本文に追加してから、**HTML です** プロパティを true にします。

   ![HTML が選択されていることを示すスクリーンショット](./media/email/html-selected.png)

   >[!TIP]
   >メールアクションで **HTML です** を必ず選択してください。


## <a name="more-information"></a>詳細情報

- [フロー付きのメール](email-overview.md) の概要
- [メールを管理するフロー](create-email-flows.md) を作成する
- [フロー内のメールをカスタマイズする](email-customization.md)


