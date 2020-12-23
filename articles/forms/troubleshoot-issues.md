---
title: Microsoft Forms でフローを使用して既知の問題のトラブルシューティングを行う | Microsoft Docs
description: Microsoft Forms でフローを使用して既知の問題のトラブルシューティングに役立つ情報を提供します
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
ms.openlocfilehash: 1cc8d07fba104eb97c9c7f6f6c62cb1d04264236
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711675"
---
# <a name="troubleshoot-issues"></a>問題をトラブルシューティングします

## <a name="limitations"></a>制限

フォームの制限については、以下を参照してください。[Microsoft Forms - 既知の問題と制限](/connectors/microsoftforms/#known-issues-and-limitations)

## <a name="known-issues"></a>既知の問題

### <a name="my-flow-doesnt-work-or-has-stopped-working"></a>フローが機能しないか、機能しなくなりました。

参照されているフォームが削除されていないこと、またはフォームの名前が変更されていないことを確認してください。

コネクタまたは製品の制限に達している可能性があります。 Microsoft Forms コネクタの場合、接続ごとの API 呼び出しの制限は、60 秒以内の接続ごとの 300 API 呼び出しと、86400 秒ごとに 1 回のトリガー ポーリングの頻度です。 さらに、Microsoft Forms については、[応答制限](https://support.microsoft.com/office/form-question-response-and-character-limits-in-microsoft-forms-ec15323d-92a4-4c33-bf88-3fdb9e5b5fea) をご覧ください。

### <a name="i-am-experiencing-an-invalid-connection-error"></a>無効な接続エラーが発生しています。

フロー内のすべてのコネクタの調整制限を確認してください。

Power Automate が使用する Cookie をブロックしている可能性があるため、Chrome プラグインの Privacy Badger などのプラグインを無効にします。

### <a name="when-the-email-sends-form-responses-the-files-are-corrupt"></a>メールがフォームの応答を送信すると、ファイルが破損します。

ファイルが破損する可能性があるため、Base64() 関数を使用していないことを確認してください。

### <a name="flow-with-form-only-works-sometimes"></a>フォーム付きのフローはたまにしか機能しません。

これが発生する理由の 1 つは、一部のユーザーがフォームの 1 行のテキスト フィールドに 255 文字を超える文字を入力する可能性があることです。 テキスト フィールドで長い回答を有効にします。  

### <a name="form-created-by-another-team-doesnt-isnt-listed-as-an-option-in-form-id"></a>別のチームによって作成されたフォームは、フォーム ID のオプションとしてリストされていません。

フォームが Microsoft Forms の「共有アイテム」タブに表示されていることを再確認します。特にチームのメンバーが会社を辞める場合に、[フォームの所有権を譲渡](https://support.microsoft.com/office/transfer-ownership-of-a-form-921a6361-a4e5-44ea-bce9-c4ed63aa54b4) する場合もあるかもしれません。

### <a name="the-forms-id-field-lists-duplicate-form-names"></a>フォーム ID フィールドには、重複するフォーム名が一覧表示されます。

フォームがごみ箱から削除されるまで、リストはすべてのフォームを伝達します。 したがって、Microsoft Forms に戻り、不要になったフォームが削除されていることを確認してください。

### <a name="unable-to-find-the-correct-form-id"></a>正しいフォーム ID が見つかりません。

フォームに移動します。 フォームの URL からフォーム ID をコピーし、カスタム値として追加します。

### <a name="i-dont-get-an-attachment-for-some-of-my-approvals"></a>一部の承認の添付ファイルを取得していません。

承認アクションにより、サイズが 5 MB になるまで通知メールにファイルが添付されます。 それを超えると、Power Automate の承認アクションでは、通知メールにファイルを添付できなくなります。 Microsoft Flow ポータルの添付ファイルをチェックするためにユーザー/承認者をリダイレクトします。

### <a name="send-email-action-looks-stuck-in-my-flow"></a>メール送信アクションがフローで停止しているようです。

フローの一部としてメール コネクタを使用している場合、24 時間ごとに 100 回の API 呼び出しの制限があります。 Office 365 Outlook コネクタを試してください。60 秒ごとに 300 API 呼び出しの制限があるため、制限に達する可能性は低くなります。
