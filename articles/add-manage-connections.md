---
title: 接続およびオンプレミス データ ゲートウェイを使用したデータへの接続について | Microsoft Docs
description: SharePoint、SQL Server、OneDrive for Business、Salesforce、Office 365、OneDrive、Dropbox、Twitter、Google Drive などへの接続を追加または管理する
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/23/2020
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0edd05a5c08b71c534a6b6b4a58bf96dcb33a6cf
ms.sourcegitcommit: 3732af8b39dcbc028de934694b54afc919e7eeef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "3893758"
---
# <a name="manage-connections-in-power-automate"></a>Power Automate での接続の管理

Power Automate が *接続* を使用するとフローの構築中にデータを簡単に利用できます。 Power Automate には、SharePoint、SQL Server、Office 365、OneDrive for Business、Salesforce、Excel、Dropbox、Twitter など、よく使用される接続が含まれています。 接続は Power Apps と共有されるため、一方のサービスで接続を作成すると、その接続は他方のサービスにも表示されます。

接続を使用して次のタスクを実行できます:

- SharePoint リストを更新します。
- OneDrive for Business や Dropbox のアカウントにある Microsoft Excel ファイルからデータを取得します。
- Office 365 で電子メールを送信する。
- ツイートを送信します。

以下を含む複数のシナリオで接続を作成できます:

-  [テンプレートからフロー](./get-started-logic-template.md) を作成する

-  [最初からフロー](./get-started-logic-flow.md) を作成するか、既存のフローを更新する

- [Power Automate](https://flow.microsoft.com/) に接続を作成しています。

>[!TIP]
> Power Automate での SharePoint の使用について詳しくは、 [SharePoint のドキュメント](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/sharepoint-connector-actions-triggers)を参照してください。

## <a name="add-a-connection"></a>接続の追加

1. [Power Automate](https://flow.microsoft.com/) に仕事用や組織のアカウントでサインインします。

1. 左側のナビゲーション バーから **データ** > **接続** を選択します。

   ![接続オプションを表示する画像](media/add-manage-connections/data-connections-link.png)

1. ページの上部から **新しい接続** を選択します。

1. 使用可能な接続リストから **+** アイコンを選択して、設定する (SharePoint などの) 接続を選択します。

   ![構成可能な接続リスト](media/add-manage-connections/new-connections-list.png)

1. 手順に従って資格情報を入力して接続を構成します。

   > [!TIP]
   > **データ** > **接続** で作成したすべての接続を確認できます。

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>オンプレミス データ ゲートウェイを介してデータに接続する

SharePoint コネクタなど一部のコネクタは、オンプレミス データ ゲートウェイをサポートします。 ゲートウェイを使用する接続を作成するには:

1. このトピックの前述の手順に従って [接続を追加します](#add-a-connection)。

1. 使用可能な接続の一覧で **SharePoint** を選択します。

1. **オンプレミス データ ゲートウェイを使用して接続する** オプションを選択します。

   ![オンプレミス オプションを選択する](media/add-manage-connections/select-on-prem-option.png)

1. 接続の資格情報を指定し、使用するゲートウェイを選択します。

   >[!TIP]
   > 詳細については [ゲートウェイの管理](./gateway-manage.md) と [ゲートウェイの概要](./gateway-reference.md) を参照してください。

   > [!NOTE]
   > 接続を構成すると **接続** に表示されます。

**接続の削除**

1. **データ** > **接続** に移動して削除する接続を選択します。

1. **…** を選択します その他のコマンドを表示してから **削除** を選択します。

   ![レコードを削除する際は [削除] を選択する](media/add-manage-connections/delete-connection.png)

1.  **削除** を選択して接続の削除を確認します。

   ![接続を削除する確認](media/add-manage-connections/delete-connection-confirmation.png)

接続を削除すると、Power Apps と Power Automate の両方から削除されます。

## <a name="update-a-connection"></a>接続を更新する

アカウントの詳細またはパスワードが変更されたために機能していない接続を更新できます。

1. **データ** > **接続** に移動して、更新する接続の **接続を修正する** リンクを選択します。

   ![リンクを選択して接続を修正する](media/add-manage-connections/fix-connection-link.png)

1. メッセージが表示されたら、新しい資格情報で接続を更新します。

接続を更新すると、Power Apps と Power Automate の両方で更新されます。

## <a name="troubleshoot-a-connection"></a>接続のトラブルシューティングを行う

組織のポリシーによっては、 Power Automate にサインインする場合と、SharePoint、Office 365、または OneDrive  for Business への接続を作成する場合に同じアカウントを使用する必要がある可能性があります。

たとえば、*yourname@outlook.com* を使用して Power Automate にサインインしているにも関わらず、*yourname@contoso.com* を使用して SharePoint に接続できない場合があります。 *yourname@contoso.com* を使用して Power Automate にサインインすると、SharePoint に接続できるようになります。
