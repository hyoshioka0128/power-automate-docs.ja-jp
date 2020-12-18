---
title: Microsoft 365 メールでの一般的な問題のトラブルシューティング | Microsoft Docs
description: Microsoft 365 メールでの一般的な問題のトラブルシューティング。
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
ms.openlocfilehash: a97fc3285dd610ce231091869464d4fbda165992
ms.sourcegitcommit: 2459abc72cd05f591f45d96f341721a310711185
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2020
ms.locfileid: "4495009"
---
# <a name="troubleshoot-common-issues-with-email-in-flows"></a>フロー内のメールに関する一般的な問題のトラブルシューティング


## <a name="known-limitations"></a>既知の制限

**メールを送る** アクションの既知の制限を [こちら](https://docs.microsoft.com/connectors/office365/#known-issues-and-limitations) で確認します。

## <a name="frequently-asked-questions"></a>よくあるご質問

**メールが届きませんでした。なぜですか?**

1.  メールサーバーにメールを送信できるように IT 部門がすべての Power Automate エンドポイントを承認したことを確認します。 これらのエンドポイントには、[IP アドレス](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config\#ip-addresses) と [ドメイン](https://support.microsoft.com/help/4557620/client-request-aborted-or-failed-to-fetch-error-in-power-automate) が含まれます。

1. メールを別のフォルダに移動する Outlook ルールがあるかどうかを再確認してください。

1. **集中** 受信トレイ機能を使用しているかどうかを確認しますか? メールが別のフォルダに届いたかどうかを確認します。

**メールを受信しておらず、メール送信アクションがフローでスタックしているように見えます。**

フローの一部として **メール** コネクタを使用している場合、24 時間ごとに 100 回の API 呼び出しの制限があります。 Office 365 Outlook コネクタでは、60 秒ごとに 300 API 呼び出しの制限があるため、制限に達する可能性は低くなりますのでお試しください。

**メールがフォルダに到着したときにトリガーされるフローがあります。メールをあるフォルダから別のフォルダに移動すると、フローがトリガーされますか?**

番号 新しいメールが到着した時のみ、フローをトリガーします。

**すべての承認者にメールを送信しようとしています。メール送信アクションの各アクションに適用され、個別のメールが発生します。私は全員にメールを送りたいのです。**

複数の承認者がいるため、それぞれに適用が追加されます。 文字列変数を作成し、セミコロンで区切って (配列ではなく) その中にメールアドレスを格納できます。

**一部の承認の添付ファイルを取得していません。**

承認アクションは、メールのサイズが 5MB に達するまで、通知メールにファイルを添付します。 添付ファイルが 5MB を超える場合、承認メールは承認者に Power Automate 承認センターで添付ファイルを確認するように指示します。

**Power Automate のメールの添付ファイルのサイズ制限はどのように増やせますか?**

 Common Data Service 管理者は、Common Data Service >  メール構成設定に移動し、添付ファイルのファイルサイズ制限を設定することで制限を変更できます。


**Power Automate が動作しなくなりました - Power Automate 共有メールボックスでアクションを使用する時の、"アイテム ID は現在のメールボックスに属していません" エラー。**

2020 年 5 月 6 日の時点で、オプションの共有メールボックス サポートがオプションの **メールボックス アドレス** パラメータで追加されました。これによりアクセスする操作に対して共有メールボックス アドレスを指定できます。 2020 年 5 月 6 日より前にこの操作を使用していた場合は、明示的に [操作を更新して、共有メールボックス アドレスを指定](https://docs.microsoft.com/connectors/office365/#shared-mailbox-support) する必要があります。

**エラー: "REST API はこのメールボックスではまだサポートされていません" が表示されます**

このエラーは、次の場合に専用 (オンプレミス) のメールサーバー上にあるアカウントで発生する可能性があります。

1. このメールボックスは専用の Microsoft Exchange Server 上にあるか、有効な Office 365 メールボックスではありません。

1. このメールボックスは、有効になっていない Outlook.com アカウントです。

1.  このメールボックスは、Power Automate を含む Office 365 計画の一部ではありません。

この [記事](https://support.microsoft.com/help/4462988/rest-api-is-not-yet-supported-for-this-mailbox-error) にあるガイダンスに従って、それを修正します。



## <a name="more-information"></a>詳細情報

- [フロー付きのメール](email-overview.md) の概要
- [メールを管理するフロー](create-email-flows.md) を作成する
- [フロー内のメールをカスタマイズする](email-customization.md)
- トップの [メールに関するシナリオ](email-top-scenarios.md)


