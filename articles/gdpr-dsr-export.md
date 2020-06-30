---
title: Power Automate GDPRデータ対象者のエクスポート依頼 | Microsoft Docs
description: Power Automate を使用して GDPRデータ対象者のエクスポートの要求に対応する方法を説明します。
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: f9fee8a217cdec28f6a3b49dee6335c4f13a3d45
ms.sourcegitcommit: 2284143cf147beb7d6071fd8005a41298e51e493
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "3384941"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-power-automate"></a>Power Automate の GDPR データ対象者のエクスポート要求に対応する


一般データ保護規則 (GDPR) への道のりであなたのパートナーとなるという当社のコミットメントの一環として、準備に役立つドキュメントを開発しました。 このドキュメントでは、GDPR に対する Microsoft の対応について説明するだけでなく、Power Automate を使用するときに GDPR コンプライアンスがサポートされるようにするために実行できる手順の例を示します。

## <a name="manage-export-requests"></a>エクスポート要求の管理

*データ ポータビリティの権利* では、データ主体は別のデータ コントローラーに送信できる電子形式 (つまり、"構造化された、一般的に使用される、マシンが読み取り可能で相互運用可能な形式") で、個人データのコピーを要求できます。

Power Automate は、特定のユーザーの個人データを検索またはエクスポートする以下のエクスペリエンスがあります:

* **Web サイト アクセス:**  [Power Apps 管理センター](https://admin.powerapps.com/)、または [Power Automate 管理センター](https://admin.flow.microsoft.com/) にサインインします

* **PowerShell アクセス:**  [Power Apps 管理者 PowerShell コマンドレット](https://go.microsoft.com/fwlink/?linkid=871804)。

|**顧客データ**|**Web サイト アクセス**|**PowerShell アクセス**|
|-----------------|------------------|-------------------|
|システムによって生成されたログ|[Office 365 サービス トラスト ポータル](https://servicetrust.microsoft.com/)|
|実行履歴|Power Automate メーカー ポータル||
|フロー|Power Automate メーカー ポータル||
|フロー アクセス許可| Power Automate 作成者ポータルと Power Automate 管理センター||
|ユーザーの詳細||Power Apps コマンドレット|
|接続|Power Automate メーカー ポータル|Power Apps コマンドレット |
|接続のアクセス許可|Power Automate メーカー ポータル|Power Apps コマンドレット |
|カスタム コネクタ|Power Automate メーカー ポータル|Power Apps コマンドレット |
|カスタム コネクタのアクセス許可|Power Automate メーカー ポータル|Power Apps コマンドレット |
|ゲートウェイ|Power Automate メーカー ポータル|オンプレミス データ ゲートウェイ PowerShell コマンドレット|
|ゲートウェイのアクセス許可|Power Automate メーカー ポータル|オンプレミス データ ゲートウェイ PowerShell コマンドレット|

## <a name="export-a-flow"></a>フローをエクスポートする

エンド ユーザーまたは自分自身にフローへのアクセス権を付与した管理者は、次の手順に従ってフローをエクスポートできます:

1. [Power Automate](https://flow.microsoft.com/) にサインインする。

1. **マイ フロー** リンクを選択し、エクスポートするフローを選択します。

1. **… 詳細** を選択し、**エクスポート** を選択します。

    ![フローのエクスポート](./media/gdpr-dsr-export/export-flow.png)

1. **パッケージ (.zip)** を選択します。

フローが zip 形式のパッケージとして使用可能になります。 詳しくは、[フローをエクスポートおよびインポートする方法](https://flow.microsoft.com/blog/import-export-bap-packages/) に関するブログ記事をご覧ください。

## <a name="export-run-history"></a>実行履歴をエクスポートする

実行履歴には、フローで発生したすべての実行の一覧が含まれています。 このデータには、トリガーとアクションに対するフローの状態、期間、継続時間、および入出力データが含まれます。

エンド ユーザーまたは  Power Automate 管理センターでフローへのアクセス権を付与した管理者は、次の手順に従ってこのデータをエクスポートできます。

1. [Power Automate](https://flow.microsoft.com/) にサインインする。
1. **マイ フロー** リンクを選択し、実行履歴をエクスポートするフローを選択します。
1. **実行履歴** ウィンドウで、**すべて表示** を選択します。

    ![実行履歴](./media/gdpr-dsr-export/run-history.png)

1. **CSV のダウンロード** を選択します。

    ![CSV のダウンロード](./media/gdpr-dsr-export/download-csv.png)

Microsoft Excel またはテキスト エディターで開いて結果をさらに分析できるように、実行履歴が .csv ファイルとしてダウンロードされます。

## <a name="export-a-users-activity-feed"></a>ユーザーのアクティビティ フィードをエクスポートする

[Power Automate](https://flow.microsoft.com/) では、アクティビティ フィードはユーザーのアクティビティ、障害、通知の履歴を示します。 すべてのユーザーが、次の手順で自分のアクティビティ フィードを見ることができます。

1. [Power Automate](https://flow.microsoft.com/) にサインインし、右上隅のベル アイコンを選択して、**活動をすべて表示する** を選択します。

    ![アクティビティ フィードの表示](./media/gdpr-dsr-export/show-activity-feed.png)

1. **活動** の画面で、結果をコピーし、Microsoft Word などのドキュメント エディターに貼り付けます。

    ![アクティビティ フィードの表示](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>ユーザーの接続をエクスポートする

接続により、フローは API、SaaS アプリケーション、その他のサード パーティ システムに接続できます。 接続を表示するには次の手順のようにします:

1. [Power Automate](https://flow.microsoft.com/) にサイン インし、右上隅の歯車アイコンを選択して、**接続** を選択します。

    ![つながりの表示](./media/gdpr-dsr-export/show-connections.png)
1. 結果をコピーし、Microsoft Word などのドキュメント エディターに貼り付けます。

Power Apps 管理者 PowerShell cmdlets

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>ユーザーの接続アクセス許可の一覧をエクスポートする

ユーザーは、[Power Apps PowerShell コマンドレット](https://go.microsoft.com/fwlink/?linkid=871804) の Get-ConnectionRoleAssignment 関数を使用して、アクセスできるすべての接続に対する接続ロール割り当てをエクスポートできます。

```PowerShell
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt"
```
Power Apps 管理者 PowerShell cmdlets

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt" 
```

## <a name="export-a-users-custom-connectors"></a>ユーザーのカスタム コネクタをエクスポートする

カスタム コネクタは、既製のコネクタを補完し、他の API、SaaS、およびカスタム開発システムに接続できるようにします。 カスタム コネクタの所有権を譲渡したり、カスタム コネクタを削除したりできます。

カスタム コネクタのリストをエクスポートするには、次の手順のようにします:

1. [Power Automate](https://flow.microsoft.com)に移動します。
1. 設定の **歯車** アイコンを選択します。
1. **カスタム コネクタ** を選択します。
1. カスタム コネクタのリストをコピーし、Microsoft Word などのテキスト エディターに貼り付けます。

    ![カスタム コネクタのエクスポート](./media/gdpr-dsr-export/export-custom-connectors.png)

Power Automate で提供されるエクスペリエンスだけでなく、[Power Apps PowerShell コマンドレット](https://go.microsoft.com/fwlink/?linkid=871804) の Get-Connector 機能を使って、すべてのカスタム コネクタをエクスポートすることもできます。

~~~~
Add-PowerAppsAccount
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "CustomConnectors.txt"
~~~~

Power Apps 管理者 PowerShell cmdlets

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserCustomConnectors.txt"  
```

## <a name="export-a-users-custom-connector-permissions"></a>ユーザーのカスタム コネクタのアクセス許可をエクスポートする

ユーザーは、[Power Apps PowerShell コマンドレット](https://go.microsoft.com/fwlink/?linkid=871804) の Get-ConnectorRoleAssignment 関数を使って、作成したすべてのカスタム コネクタのアクセス許可をエクスポートできます。

```PowerShell
Add-PowerAppsAccount
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"
```

Power Apps 管理者 PowerShell cmdlets

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"   
```

## <a name="export-approval-history"></a>承認履歴をエクスポートする

Power Automate の承認履歴は、ユーザーが受信または送信した承認の履歴レコードをキャプチャします。 すべてのユーザーが、次のようにして、承認履歴を表示できます:

1. [Power Automate](https://flow.microsoft.com/) にサインインし、**承認** を選択して、**履歴** を選択します。

    ![承認履歴の表示](./media/gdpr-dsr-export/view-approval-history.png)

1. 一覧に、ユーザーが受け取った承認が表示されます。 ユーザーは、**受信** の隣の下向き矢印を選択してから、**送信済み** を選択することで、自分が送信した承認を表示できます。

    ![受信した承認の表示](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>ユーザーの詳細をエクスポートする
ユーザーの詳細では、ユーザーと特定のテナント間のリンクが提供されます。 管理者は、**Get-AdminFlowUserDetails** コマンドレットを呼び出し、ユーザーのオブジェクト ID で渡すことで、この情報をエクスポートすることができます。

Power Apps 管理者 PowerShell cmdlets

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>ゲートウェイ設定をエクスポートする
オンプレミス データ ゲートウェイのデータ主体エクスポート要求への応答に関しては、[こちら](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration) を参照してください。

