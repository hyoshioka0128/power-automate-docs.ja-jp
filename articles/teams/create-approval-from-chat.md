---
title: チャットまたはチャネルからの承認を作成する | Microsoft Docs
description: チャットまたはチャネルからの承認を作成する方法について説明します。
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
ms.date: 11/30/2020
ms.author: hamenon
ms.openlocfilehash: b29dde17e91c3323c8d77b215d0de9042908a3dc
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711694"
---
# <a name="create-an-approval-from-a-chat-or-channel"></a>チャットまたはチャネルからの承認を作成する

Teams の新しい承認機能を使用すると、作成ボックスから任意のチャットまたはチャネルから承認を作成できます。

## <a name="start-an-approval-in-a-chat-or-channel"></a>チャットまたはチャネルで承認を開始する

次のステップを実行し、Teams のチャットまたはチャネルで承認を作成します。

1. [Microsoft Teams](https://teams.microsoft.com) にサインインします。

2. 承認を送信するチャットまたはチャネルに移動します。

3. 作成ボックスの下にある承認アイコンを選択します。
   
   ![チャットで承認を開始する](../media/native-approvals-in-teams/approvals-compose-box.png)

4. アイコンを選択すると、承認の詳細を入力するためのモーダル ダイアログが表示されます。

   ![承認フォーム](../media/native-approvals-in-teams/approvals-dialog-box.png)

5. 送信する承認の詳細と、承認を必要とするユーザーを入力します。

>[!TIP]
>既定では、承認者の入力は、承認を送信するチームまたはチャットの名簿に制限されています。

6. **オプション**: 承認を得てファイルを含めることもできます。 これを行うには、承認フォームで *添付ファイルを追加* します。 アップロードしたファイルはすべて、Teams で共有されている他のファイルと同じように OneDrive/SharePoint フォルダーに自動的に保存されます。

   ![承認に添付ファイルを追加する](../media/native-approvals-in-teams/approval-attach.png)


7. **送信** を選択します。 

   カードが作成され、チャットまたはチャネルで送信されました。

   ![承認カード](../media/native-approvals-in-teams/approvals-card.png)

## <a name="custom-responses-for-approvals"></a>承認へのカスタム応答

承認へのアクションをカスタマイズする場合は、**カスタム応答** オプションを使用してアクションを任意に変更します。 これを行うには、前述の同じ手順に従ってから、承認フォームのカスタム応答オプションを切り替えます。

   ![カスタム応答](../media/native-approvals-in-teams/custom-responses.png)

>[!TIP]
>2 つ以上のカスタム応答を追加する場合は、クラウド フローを使用して承認を送信する必要があります。 [承認におけるカスタム応答の詳細](../create-approval-response-options.md)。


## <a name="known-issues"></a>既知の問題

現在、このネイティブ Teams エクスペリエンスを使用して作成されたすべての承認は、組織の既定の環境で作成されています。

