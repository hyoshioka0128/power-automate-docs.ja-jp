---
title: Microsoft Teams の任意のメッセージからフローをトリガーする | Microsoftドキュメント
description: Microsoft Teams の任意のメッセージからインスタント フローをトリガーする方法
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
ms.date: 07/16/2020
ms.author: hamenon-ms
ms.openlocfilehash: 002ee947d89f4a1b4e826ac61948350f0c94c7ac
ms.sourcegitcommit: 3642d485c5f66141d990a0fd69cbd0b2b55fd2f5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "3610202"
---
# <a name="trigger-a-flow-from-any-message-in-microsoft-teams"></a>Microsoft Teams のメッセージからフローをトリガーする

メッセージを使用して Microsoft Teams のプロセスをトリガーできます。 ここでは例として、Teams のメッセージを起点として Azure DevOps で作業項目の作成や、Dynamicsで営業案件を作成する方法を説明します。 

Teams のコネクターの**選択したメッセージ**トリガーを使用して、Teams 内から直接フローをトリガーします。

## <a name="create-the-flow"></a>フローを作成する

1. **Power Automate** にサインインし、続いて**マイ フロー** > **新規** > **インスタント作成**を選択します。
1. フローに名前を付けます。
1. **選択したメッセージ** トリガーを選択します。

   ![選択したメッセージトリガー](media/trigger-flow-teams-message/trigger-for-a-selected-message.png)

1. **作成**を選びます。

>[!NOTE]
>Teams にログインしていない場合は、ログインする必要があります。

**選択したメッセージ**トリガーには、アダプティブ カード形式のオプションの入力があります。 アダプティブ カードを使用してフォームを作成し、フローのトリガーをするユーザーから情報を収集します。 たとえば、フローがタスクを作成する場合、アダプティブ カードを使用して、タスクのタイトルや説明などの情報を収集できます。

## <a name="collect-information-from-the-user"></a>ユーザーから情報を収集する

フォームを使用してユーザーから情報を収集するには、トリガー内の**アダプティブ カードを作成**ボタンを選択します。

![アダプティブ カード ボタン](media/trigger-flow-teams-message/create-adaptive-card.png)

これにより、カードの要素をドラッグ アンド ドロップして独自のフォームを作成することができる、インラインのアダプティブ カード エディターが表示されます。

![アダプティブ カード フォーム デザイナー](media/trigger-flow-teams-message/ac-card-designer.png)

アダプティブ カード フォーム内のそれぞれの入力には ID を持っています。フローの後半部分で動的トークンを介して ID を使用し、ユーザーがフローの実行の一環として入力した入力値を参照できます。

### <a name="use-the-message-details-within-the-flow"></a>フロー内でメッセージの詳細を使用する

フロー内で使用するトリガーの出力結果として利用可能なメッセージ要素がいくつかあります。 以下に、プロパティの概要を示します :

* メッセージ コンテンツ - Teams メッセージの完全な HTML コンテンツ。
* プレーン テキストメッセージ 出力 - Teams メッセージのプレーン テキスト版。
* メッセージへのリンク - メッセージの参照に使用するダイレクト URL。
* 送信者の表示名、送信者 ID - メッセージを送信したユーザーの詳細。
* 元のユーザー表示名、元のユーザー ID - フローを呼び出したユーザーの詳細。

   ![選択したメッセージの出力結果](media/trigger-flow-teams-message/dynamic-outputs.png)

トリガー出力の完全なリストについては、[こちらを参照してください](https://docs.microsoft.com/connectors/teams/)。

## <a name="trigger-the-flow"></a>フローのトリガー

**選択したメッセージ**トリガーを使用するフローは、フローの**その他のアクション**メニュー内の Teams メッセージのメッセージ アクションとして表示されます。 

![Microsoft Teams からトリガーする](media/trigger-flow-teams-message/more-actions-menu.png)

>[!IMPORTANT]
>フローの名前は Teams 内のフローの参照に使用されるため、フローにはわかりやすい名前を付けてください。

>[!IMPORTANT]
>これらのフローは、既定の環境内で作成し、Teams にて一覧表示されるよう設定する必要があります。

## <a name="best-practices"></a>ベスト プラクティス

完成したフローには、ユーザーへの確認フォームを必ず含めてください。 トリガーされたフローの完了時に Teams のユーザーに通知をするには、**フロー ボットとしてユーザーにメッセージを投稿する**または、**フロー ボットとしてチャンネルにメッセージを投稿する** を使用することを推奨します。

以下が Azure Devops で作業項目を作成し、発信元のユーザーに確認を投稿するフローの例です。

![タスク フローを作成する](media/trigger-flow-teams-message/complete-flow.png)

## <a name="known-issues-and-limitations"></a>既知の問題と制限

これらのフローは、既定の環境内で作成し、Teams にて一覧表示されるよう設定する必要があります。