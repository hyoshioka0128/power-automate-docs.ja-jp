---
title: SharePoint でのフロー使用の概要 | Microsoft Docs
description: SharePoint リストおよびファイルでフローを使用できる多くの方法の概要を説明します。
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
ms.date: 06/08/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 11043a7a5dc21731f2e3207f033c61a4c3da3f91
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709902"
---
# <a name="use-sharepoint-and-power-automate-to-build-workflows"></a>SharePoint と Power Automate を使用してワークフローを構築する

Power Automate は SharePoint と深く統合されています。 [100 を超える SharePoint テンプレート](https://flow.microsoft.com/templates/)で始めるか、または SharePoint と統合する独自のフローを最初から作成できます。

## <a name="top-sharepoint-workflow-scenarios"></a>トップ SharePoint ワークフロー シナリオ

Power Automate を SharePoint で使用できる主なシナリオのいくつかを次に示します:

- 承認フローを管理する
- ファイルとリストを操作する
- ワークフローから Power Automate に移行する

### <a name="manage-approval-flows"></a>承認フローを管理する

- [SharePoint ページの承認](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/customize-page-approvals)をニーズに合わせてカスタマイズします。
- Power Automate を使用して、SharePoint で[ドキュメントの承認](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/require-doc-approval)を要求します。
- 完成したドキュメントを[承認のためのチーム](./customize-sharepoint-page-approvals.md)にルーティングします。

### <a name="work-with-files-and-lists"></a>ファイルとリストを操作する

- [リスト アイテムとファイルのアクセス許可](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/manage-list-item-file-permissions)を管理します。
- SharePoint で承認された後で、[ファイルを別のフォルダーに移動](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/migrate-from-classic-workflows-to-power-automate-flows)します。
- 新しい注文が Salesforce に追加されたら、[SharePoint でアイテムを作成](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/migrate-from-classic-workflows-to-power-automate-flows)します。
- [リストからアイテムを取得するか、ライブラリからファイルを取得](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/working-with-get-items-and-get-files)します。
- [SharePoint または OneDrive でのリストまたはライブラリのフロー](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01)を作成します。
- [クラウド フローの編集](https://support.microsoft.com/office/edit-a-flow-for-a-list-in-sharepoint-b6678daa-2c82-44eb-be3f-2a9cb56301e8)。

### <a name="other-top-scenarios"></a>その他の上位シナリオ

- [HTTP リクエスト](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/working-with-send-sp-http-request)を使用して、リストとライブラリを管理します。
- [SharePoint のリマインダー フロー](create-sharepoint-reminder-flows.md)を作成します。

## <a name="sharepoint-triggers-and-actions"></a>SharePoint トリガーとアクション

SharePoint トリガーを使用して、SharePoint リストまたはライブラリに加えられた変更を監視するフローを開始できます。 完全なリストについては、[SharePoint トリガー](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/sharepoint-connector-actions-triggers#sharepoint-triggers)に移動してください。

![「アイテムが作成されたとき」などの SharePoint トリガーを示すスクリーンショット](./media/overview-sharepoint/sharepoint-triggers.png)

フローが開始されるとすぐに、[40 *アクション*](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/sharepoint-connector-actions-triggers#sharepoint-actions)を超えるアクションのいずれかを使用して、SharePoint リストを操作できます。

![「添付ファイルの追加」や「ファイルのチェックイン」などの SharePoint アクションを示すスクリーンショット](./media/overview-sharepoint/sharepoint-actions.png)

## <a name="migrate-from-workflows-to-power-automate"></a>ワークフローから Power Automate に移行する

-  SharePoint で、[クラシック ワークフローから Power Automate フローへ](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/migrate-from-classic-workflows-to-power-automate-flows)移行します。

## <a name="next-steps"></a>次の手順

- [Power Automate および SharePoint](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/get-started/create-your-first-flow) の使用を開始します。 
- [承認](https://docs.microsoft.com/power-automate/get-started-approvals)を開始します。
- 詳細モードの条件で、新しい[承認フロー](use-expressions-in-conditions.md)を作成します。
