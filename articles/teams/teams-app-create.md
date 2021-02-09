---
title: Microsoft Teams でフローを作成する | Microsoft Docs
description: Microsoft Teams で Power Automate アプリを使用してフローを作成する方法について説明します
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
ms.date: 11/16/2020
ms.author: hamenon
ms.openlocfilehash: 03ac935810836f9f2feedfd05909f9ef17584af3
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709831"
---
# <a name="create-flows-in-microsoft-teams"></a>Microsoft Teams でフローを作成する

[Power Automate アプリ](./install-teams-app.md) を使用し、Microsoft Teams 内からフローを作成および管理できます。 すばやく開始するには、既存のテンプレートの 1 つを使用してフローを作成するか、カスタマイズされたフローを最初から作成することができます。 

## <a name="prerequisites"></a>前提条件

Power Automate アプリを使用するには、[Microsoft Teams](https://teams.microsoft.com) にアクセスできるアカウントが必要です。

## <a name="create-a-cloud-flow-from-a-template"></a>テンプレートからクラウド フローを作成する

>[!NOTE]
>既定では、Power Automate アプリは Microsoft Teams のために作成されたテンプレートを表示します。 右上のフィルターを切り替えて、必要に応じてすべての Power Automate テンプレートを表示できます。
 
![タブ フィルターを作成する](../media/power-automate-teams-app-create/create-filter.png)

次の手順に従って、Microsoft Teams テンプレートからクラウド フローを作成します。

1. [Microsoft Teams](Https://Teams.Microsoft.com) にサインインします。

   >[!TIP]
   >また、Microsoft Teams アプリを使用することもできます。

1. 画面の右側の **アプリ** を選択します。
1. **Power Automate** アプリを検索して選択します。

   ![Power Automate アプリの検索を示すスクリーンショット](../media/power-automate-teams-app-create/search-app.png)

1. **作成** タブを選択し、フローのベースにするテンプレートを選択します。

   ![タブの作成](../media/power-automate-teams-app-create/create-tab.png)

1. 選択したテンプレートが Microsoft Teams 用に最適化されている場合、フローの名前を変更し、フローに必要なアプリで認証できるダイアログが表示されます。
   ![接続を設定する](../media/power-automate-teams-app-create/template1.png)

   >[!NOTE]
   >フローを正常に実行するには、すべての接続にログインする必要があります。 緑のチェックは、認証済みであることを示します。

1. 必要に応じて接続を設定します。

1. **続行** を選択し、フローを正常に実行するために必要なパラメーターの一覧を取得します。 必要なパラメーターを提供します。
   
   ![セットアップ パラメーター](../media/power-automate-teams-app-create/template2.png)

   完全なフローを確認したい場合は、**詳細モードで編集** を選択します。
   
   ![詳細モード](../media/power-automate-teams-app-create/template-advanced.png)

1. 準備が完了しました。 フローが正常に作成されたことを示す確認画面が表示されます。 フローを作成したら、**ホーム** タブで見つけることができます。

   ![確認画面](../media/power-automate-teams-app-create/template3.png)

>[!IMPORTANT]
>Microsoft Teams の Power Automate アプリ内からフローを作成する場合、これらは常に組織の既定の環境で作成されます。 [Power Automate](https://flow.microsoft.com) からこれらのフローにアクセスすることもできます。

## <a name="create-a-cloud-flow-from-scratch"></a>ゼロからクラウド フローを作成する

作成するフローを完全に制御する場合は、テンプレートを使用する代わりに、画面の右上から **ブランクから作成** を選択します。

   ![一から作成](../media/power-automate-teams-app-create/create-blank.png)

これは Microsoft Teams 内のフル Power Automate デザイナー エクスペリエンスに表示され、[完全にカスタマイズされたフローを作成](https://docs.microsoft.com/power-automate/get-started-logic-flow) できます。

   ![一から作成](../media/power-automate-teams-app-create/full-editor.png)


## <a name="known-issues"></a>既知の問題

Power Automate アプリ内から作成するフローはすべて、組織の既定の環境内にあります。

## <a name="related-articles"></a>関連記事
- [Microsoft Teams でフローを管理する](./teams-app-home.md)。

- [Microsoft Teams コネクタのドキュメント](https://docs.microsoft.com/connectors/teams/) にアクセスしてください。

