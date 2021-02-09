---
title: Microsoft Teams で承認に応答する | Microsoft Docs
description: Microsoft Teams でチャットまたはチャネルの承認に応答する方法を説明する
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
ms.openlocfilehash: bdc19a1f8b27fbcd720983d330a7e580009f5015
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711692"
---
# <a name="respond-to-an-approval-from-a-chat-or-channel"></a>チャットまたはチャネルからの承認に応答する

ユーザーがチャットまたはチャネル メッセージで、または承認アプリから承認を送信した場合、Teams チャットまたはチャネル内から、または承認アプリから、直接応答することができます。

承認アプリには、同じ環境のフローを使用して送信された承認も表示されます。 このように、Teams の承認アプリを使用して、すべての承認を管理することができます。

## <a name="approve-or-reject-an-request-in-teams"></a>Teams で要求を承認または拒否する

次のステップを実行し、Microsoft Teams のチャットまたはチャネルで承認に応答します。

1. [Microsoft Teams](https://teams.microsoft.com) にサインインします。

2. 承認が送信されたチャットまたはチャネルに移動します。

   承認されたカードが表示されます。

   ![チャットでの承認](../media/native-approvals-in-teams/approval-received.png)

   または、Teams で承認アプリを開いて、**受信済み** タブに移動します。

   ![チャットでの承認](../media/native-approvals-in-teams/approval-app-received.png)


3. カードで **詳細の表示** を選択するか、または承認を選択して承認フォームを開きます。
   
   ![フォームを承認または拒否する](../media/native-approvals-in-teams/approval-respond.png)

4. ここから、承認を承認または拒否することができます。 決定にコメントを含めることもできます。 承認されると、カードまたはアプリの状態が更新されます。

   ![承認完了](../media/native-approvals-in-teams/approval-complete.png)

   ![承認完了アプリ](../media/native-approvals-in-teams/approval-app-complete.png)

>[!TIP]
>承認者がカスタム応答で承認を送信することを選択した場合、下部のアクションは異なる場合があります。 たとえば、次のようなものです。

![カスタム応答](../media/native-approvals-in-teams/custom-responses-respond.png)


## <a name="known-issues"></a>既知の問題

現在、組織の既定の環境で送信された承認のみが Teams の承認アプリ内に一覧表示されます。
