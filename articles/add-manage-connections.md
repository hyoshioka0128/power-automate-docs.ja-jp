---
title: 接続およびオンプレミス データ ゲートウェイを使用したデータへの接続について | Microsoft Docs
description: SharePoint、SQL Server、OneDrive for Business、Salesforce、Office 365、OneDrive、Dropbox、Twitter、Google Drive などへの接続を追加または管理する
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 881a0a99e6570e20d748ea65c2fd003133cace06
ms.sourcegitcommit: a09a957460f7495c0b103e1d832f65963025fbac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2020
ms.locfileid: "3697127"
---
# <a name="manage-connections-in-power-automate"></a>Power Automate での接続の管理

Power Automate で接続を作成する場合は、フローを作成しながら、データに簡単にアクセスできます。 Power Automate には、SharePoint、SQL Server、Office 365、OneDrive for Business、Salesforce、Excel、Dropbox、Twitter など、よく使用される接続が含まれています。 接続は Power Apps と共有されるため、一方の製品で接続を作成すると、その接続は他方の製品にも表示されます。

たとえば、接続を使用すると、次のタスクを実行できます:

* SharePoint リストを更新します。
* OneDrive for Business または Dropbox アカウントで使用している Excel ファイルからデータを取得する。
* Office 365 で電子メールを送信する。
* ツイートを送信します。

次のような複数のシナリオで、接続を作成できます。

* [テンプレートからフロー](get-started-logic-template.md) を作成する
* [ゼロからフロー](get-started-logic-flow.md) を作成するか、既存のフローを更新する
* サービスでのレポートの直接作成[Power Automate の Web サイト][1] で直接接続を作成する

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]

## <a name="add-a-connection"></a>接続の追加
1. [Power Automate の Web サイト][1] で、ご自身の職場または組織のアカウントを使用してサインインします。
2. 右上隅近くにある歯車アイコンを選択し、**接続** を選択します。
   
    ![接続を選択する](./media/add-manage-connections/connections-menu.png)
3. **接続の作成** を選択します。
4. **利用可能な接続** の一覧で、SharePoint などの、設定する接続を選択します。
5. **接続の作成** ボタンを選択し、接続をセットアップするための資格情報を入力します。

接続がセットアップされると、**自分の接続** の一覧に表示されます。

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>オンプレミス データ ゲートウェイを介してデータに接続する
この記事の執筆時点では、SQL Server と SharePoint  Server はオンプレミス データ ゲートウェイに対応しています。 ゲートウェイを使用する接続を作成するには:

1. このトピックの前述の手順に従って、接続を追加します。
2. **利用可能な接続** の一覧で **SQL Server** を選択し、**オンプレミスのデータ ゲートウェイ経由で接続** チェック ボックスを選択します。
   
    ![ゲートウェイの選択](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > Microsoft SharePoint データ ゲートウェイは、HTTP トラフィックに対応していますが、HTTPS トラフィックには対応していません。
   > 
   > 
3. 接続の資格情報を指定し、使用するゲートウェイを選択します。
   
    詳細については、[ゲートウェイの管理](gateway-manage.md) と [ゲートウェイについて](gateway-reference.md) を参照してください。
   
    接続がセットアップされると、**自分の接続** の一覧に表示されます。

## <a name="delete-a-connection"></a>つながりの削除
1. **自分の接続** ページに移動し、削除する接続に対してごみ箱アイコンを選択します。
   
    ![接続の削除](./media/add-manage-connections/delete-connection.png)
2. **OK** を選択して、接続を削除することを確認します。
   
    ![削除の確認](./media/add-manage-connections/delete-confirmation.png)

接続を削除すると、Power Apps と Power Automate の両方から削除されます。

## <a name="update-a-connection"></a>接続を更新する
アカウントの詳細またはパスワードが変更されたために機能していない接続を更新できます。

1. **自分の接続** ページで、更新する接続の **パスワードの確認** リンクを選択します。
   
    ![パスワードの確認](./media/add-manage-connections/verify-password.png)
2. メッセージが表示されたら、新しい資格情報で接続を更新します。

接続を更新すると、Power Apps と Power Automate の両方で更新されます。

## <a name="troubleshoot-a-connection"></a>接続のトラブルシューティングを行う
組織のポリシーによっては、 Power Automate にサインインする場合と、SharePoint、Office 365、または OneDrive  for Business への接続を作成する場合に同じアカウントを使用する必要がある可能性があります。

たとえば、*yourname@outlook.com* を使用して Power Automate にサインインしているにも関わらず、*yourname@contoso.com* を使用して SharePoint に接続できない場合があります。 *yourname@contoso.com* を使用して Power Automate にサインインすると、SharePoint に接続できるようになります。

<!--Reference links in article-->
[1]: https://flow.microsoft.com
