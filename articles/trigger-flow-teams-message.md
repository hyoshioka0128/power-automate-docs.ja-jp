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
ms.author: hamenon
ms.openlocfilehash: 0e6e1ede6491e376c19397aa0d35f17ff270e016
ms.sourcegitcommit: 2971e852bdb76efbe012b9de8df8e7f492063184
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "3900482"
---
# <a name="trigger-a-flow-from-any-message-in-microsoft-teams"></a>Microsoft Teams のメッセージからフローをトリガーする

メッセージを使用して Teams のプロセスをトリガーできます。 ここでは例として、Teams のメッセージを起点として Azure DevOps で作業項目の作成や、Dynamics 365 で営業案件を作成する方法を説明します。 

Teams のコネクターの**選択したメッセージ**トリガーを使用して、Teams 内から直接フローをトリガーします。

## <a name="create-the-flow"></a>フローを作成する

1. Power Automate にサインインして **マイ フロー** > **新規** > **インスタント - 最初から作成** を選択します。
1. フローの名前を入力します。
1. **選択したメッセージ** トリガーを選択します。

   ![選択したメッセージトリガー](media/trigger-flow-teams-message/trigger-for-a-selected-message.png)

1. **作成**を選びます。

>[!NOTE]
>まだサインインしていない場合は Teams にサインインする必要があります。

**選択したメッセージ**トリガーには、アダプティブ カード形式のオプションの入力があります。 アダプティブ カードを使用してフォームを作成し、フローのトリガーをするユーザーから情報を収集します。 たとえば、フローがタスクを作成する場合、アダプティブ カードを使用してタスクのタイトルや説明などの情報を収集できます。

## <a name="collect-information-from-the-user"></a>ユーザーから情報を収集する

フォームを使用してユーザーから情報を収集する場合に、ユーザーがトリガーで **アダプティブ カードを作成する** を選択できます。

![アダプティブ カードを作成する](media/trigger-flow-teams-message/create-adaptive-card.png)

これでインライン アダプティブ カード エディタが表示され、カード要素をドラッグして独自のフォームを作成できます。

![アダプティブ カード フォーム デザイナー](media/trigger-flow-teams-message/ac-card-designer.png)

アダプティブ カード フォームの各入力には ID があります。 ダイナミック トークンを介したフローの後半で ID を使用して、フロー実行の一部としてユーザーが入力した可能性のある入力を参照できます。

### <a name="use-the-message-details-within-the-flow"></a>フロー内でメッセージの詳細を使用する

いくつかのメッセージ要素はフローで使用するトリガー出力に使用できます。 いくつかのプロパティの概要を以下に示します:

* **メッセージ コンテンツ**: Teams メッセージの完全な HTML コンテンツ。
* **プレーン テキスト メッセージ出力**: Teams メッセージのプレーン テキスト版。
* **メッセージへのリンク**: メッセージを参照する直接 URL。
* **送信者の表示名と送信者 ID**: メッセージを送信したユーザーに関する詳細。
* **元のユーザーの表示名と元のユーザー ID**: フローを呼び出したユーザーに関する詳細。

![選択したメッセージの出力結果](media/trigger-flow-teams-message/dynamic-outputs.png)

詳細は [トリガー出力の完全なリスト](https://docs.microsoft.com/connectors/teams/) を参照してください。

## <a name="trigger-the-flow"></a>フローのトリガー

>[!IMPORTANT]
>これらのフローを Teams に表示する場合は、*既定* の環境にこれらのフローを作成する必要があります。

>[!IMPORTANT]
>**Teams で選択したメッセージの場合** トリガーで作成したフローが表示されない場合は、Teams 管理センター https://admin.teams.microsoft.com/policies/manage-apps で Power Automate アクション アプリが有効かどうか確認するよう管理者に依頼してください。 

**選択したメッセージ**トリガーを使用するフローは、フローの**その他のアクション**メニュー内の Teams メッセージのメッセージ アクションとして表示されます。<!--note from editor: I assume Joni Sherman, Isaiah Langer, and Megan Bowen are names from sample data?-->

![Teams からトリガーする](media/trigger-flow-teams-message/more-actions-menu.png)

>[!IMPORTANT]
>フロー名は Teams でフローの参照に使用するため、内容を表す名前を指定します。

## <a name="best-practices"></a>ベスト プラクティス

フローの完了後には必ずユーザーに対する確認フォームを含めてください。 トリガーしたフローの完了時に **ユーザーにフロー ボットとしてメッセージを投稿する** または **チャネルにフロー ボットとしてメッセージを投稿する** を使用して Teams のユーザーに通知することを推奨します。

これは Azure DevOps で作業項目を作成して元のユーザーに確認を投稿するフローの例です。<!--note from editor: This image needs more detailed alt text to describe what's going on. It probably will take more than 150 characters, so this might be a good place to use the new image extension.-->

![タスク フローを作成する](media/trigger-flow-teams-message/complete-flow.png)

## <a name="known-issues-and-limitations"></a>既知の問題と制限

これらのフローは、既定の環境内で作成し、Teams にて一覧表示されるよう設定する必要があります。
