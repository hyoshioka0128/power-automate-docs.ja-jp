---
title: SharePoint 項目のリマインダー フローを作成する | Microsoft Docs
description: SharePoint 項目の期限が迫っていることを通知するフローを作成します。
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
ms.date: 04/06/2020
ms.author: deonhe
ms.openlocfilehash: 5ddb783eba69f9f4926778390175d6eac672a730
ms.sourcegitcommit: dd1d04d6e899174c474291ae415e6272ad4c381a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "4068738"
---
# <a name="create-sharepoint-reminder-flows"></a>SharePoint リマインダー フローを作成する


SharePoint のリストとライブラリを使用すると、カスタム メタデータ列を定義して日付を追跡できます。 Power Automate と SharePoint の統合により、SharePoint の DateTime 列に基づいたリマインダー フローを簡単に作成できます。 リマインダー フローを使用すると、SharePoint のドキュメントまたはアイテムの日付より事前に指定した日数だけ前に、個人用のメール アラートを受け取ります。

## <a name="prerequisites"></a>前提条件

- SharePoint Online へのアクセス。
- DateTime 列が含まれる SharePoint リストまたはライブラリ。
- Power Automate へのアクセス。

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]

## <a name="create-a-reminder-flow"></a>リマインダー フローを作成する

 1. 現在のビューに少なくとも 1 つの DateTime 列を含む [SharePoint リスト](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) を作成してください。 
 1. **自動化** > **リマインダーを設定する** > **非アクティブ化された日付** (これは、リマインダー対象の DateTime を含む列です) を選択します。

     ![リマインダー フローを選択する](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. 場合によっては、この Power Automate テンプレートで使用されるサービスにサインインする必要があります。
     
1. **続行** を選択します。

1. **リマインダーを設定する** カードでリマインダー アラートを受信する場合は、**フロー名** と DateTime 列のエントリの前の日数を指定します。

    ![リマインダー フローの詳細を設定する](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. **リマインダーを設定する** カードで、**作成** を選択します。

1. フローが作成されたことを示す次のメッセージが表示されます:

    ![作成されたリマインダー フロー](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>受信したリマインダーの確認

前に作成した **リマインダーを設定する** のフローで指定した **何日も前にあらかじめこれを通知する** に基づいて、電子メールでリマインダーを受け取ります。 

## <a name="edit-your-flow"></a>フローを編集する

リマインダー フローは他のフローと同じように、[Power Automate](https://flow.microsoft.com) からアクセスして編集することができます。

## <a name="learn-more"></a>詳細はこちら

- [Power Automate](https://flow.microsoft.com) を使用する。
- SharePoint で [リマインダー フロー](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) を設定する。


