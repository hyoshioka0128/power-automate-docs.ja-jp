---
title: Microsoft Forms でフローを始める方法 | Microsoft Docs
description: Microsoft Teams 内のフローを使用するための上位の手順です。
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
ms.openlocfilehash: d43c47924bfa9fef14394e2c7842317bb7deae05
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711597"
---
# <a name="how-to"></a>方法

それらをアーカイブする例も含む Power Automate のフォームに関する質問方法の上位は、次の通りです。

- フォーム応答の日付と時刻の形式を変更します。
- グループ フォームを使用してフローを構成します。 
- 条件付きフォームの応答に基づいて電子メールを送信します。
- Microsoft Forms の添付ファイルを PDF に変換します。
- フォーム応答を Power BI データセットにアップロードして、応答を視覚化します。
- Microsoft Forms 応答からリードを作成します。

## <a name="change-the-date-and-time-format-of-the-forms-response"></a>フォーム応答の日付と時刻の形式を変更

既定では、フォームの送信時刻には UTC タイム ゾーンが表示されますが、ユーザーはそれをローカル タイム ゾーンに変更することをお勧めします。 

- タイムゾーンを変換する方法については以下を参照: [Microsoft でのタイム ゾーンの変換Power Automate](https://support.microsoft.com/help/4557244/converting-time-zone-in-microsoft-power-automate)
- フローの日付形式をカスタマイズする方法については以下を参照: [フロー内の日付と時刻の値をカスタマイズ/フォーマットする方法](https://support.microsoft.com/help/4534778/how-to-customize-format-date-and-time-values-in-a-flow)

## <a name="configure-a-flow-with-a-group-form"></a>グループ フォームを使用してフローを構成

フォームに移動します。 フォームの URL からフォーム ID をコピーし、カスタム値として追加します。 

## <a name="send-an-email-based-on-a-conditional-form-response"></a>条件付きフォームの応答に基づいて電子メールを送信

Microsoft Forms のトリガーとアクションを選択したら、特定の応答に基づいて[条件](/add-condition.md#add-a-condition) をフォームに追加できます。 条件には、テキスト値または数値と等しいことが含まれます。 条件が作成されると、アクションを追加できる「はいの場合」および「いいえの場合」ステートメントが表示されます。 たとえば、誰かがイベントに参加すると応答した場合、イベントの詳細を送信できます。 段階的な説明: [Microsoft Forms の自動ワークフローを作成する](https://support.microsoft.com/office/create-an-automated-workflow-for-microsoft-forms-dee28c00-503a-48b3-89df-91a5084e6e43)

## <a name="convert-an-attachment-in-microsoft-forms-to-pdf"></a>Microsoft Forms の添付ファイルを PDF に変換

フォームのトリガーとアクションを作成した後、[データを選択](/data-operations#use-the-select-action) 操作を追加、HTML テーブルの作成、OneDrive for Business の[ファイルを作成する](/connectors/onedrive/#create-file)、OneDrive for Business の[ファイルを変換する](/connectors/onedrive/#convert-file) を PDF または他のタイプのファイルへ実行します。 Lernen Tech から、[役立つチュートリアル](https://www.youtube.com/watch?v=6dJTkG-KE-E&feature=emb_logo) を確認ください。

## <a name="upload-forms-responses-to-a-power-bi-data-set-to-visualize-responses"></a>フォーム応答を Power BI データ セットにアップロードして、応答を視覚化する

Power BI で、フォーム内の質問に合わせたダッシュボードを作成できます。 段階的な説明を参照してください: [フローと Power BI を使用してフォーム調査を洞察に変える](https://flow.microsoft.com/blog/forms-and-flow-and-powerbi/) 

## <a name="create-a-lead-from-a-microsoft-forms-response"></a>Microsoft Forms 応答からリードを作成

レスポンダーのデータを Dynamics 365 にリードとしてプッシュできます。 詳細: [Microsoft Flow & Forms で Web フォームを Dynamics 365 リードに変換する](https://www.preact.co.uk/blog/converting-web-forms-to-dynamics-365-leads-with-microsoft-flow-forms)


### <a name="see-also"></a>関連項目

- [一般的な問題のトラブルシューティング](troubleshoot-issues.md)
- [Microsoft Forms - 既知の問題と制限](/connectors/microsoftforms/#known-issues-and-limitations)
