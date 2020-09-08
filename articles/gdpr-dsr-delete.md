---
title: Power Automate GDPRデータ対象者削除依頼 | Microsoft Docs
description: Power Automate を使用して GDPRデータ対象者削除依頼に対応する方法を説明します。
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
ms.date: 08/14/2020
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 07c0f662eae3cebe49009de0730a65494fdbffa2
ms.sourcegitcommit: 39d7912519ff03dae924023c1a1c320a30efaa81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "3691154"
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-power-automate"></a>Power Automate の GDPR データ対象者削除依頼に対応する


組織の顧客データから個人データを削除することによる "忘れられる権利" は、GDPR での重要な保護です。 個人データの削除では、監査ログ情報を除くすべての個人データとシステム生成ログが削除されます。

Power Automate では、組織の日常業務の重要な一部であるオートメーション ワークフローを構築できます。 ユーザーが組織を離れるとき、管理者は、手作業で確認し、ユーザーが作成した特定のデータとリソースを削除するかどうかを判断する必要があります。 その他の個人データは、Azure Active Directory からユーザーのアカウントが削除されるときは常に自動的に削除されます。

次の表では、自動的に削除される個人データと、管理者が手動で確認して削除する必要があるデータを示します:

|手動での確認および削除が必要|ユーザーが Azure Active Directory から削除すると自動的に削除される|
|------|------|
|環境*|システムによって生成されたログ|
|環境アクセス許可**|実行履歴|
|フロー|アクティビティ フィード|
|フロー アクセス許可|ゲートウェイ |
|ユーザーの詳細|ゲートウェイのアクセス許可|
|接続*||
|接続のアクセス許可||
|カスタム コネクタ*||
|カスタム コネクタのアクセス許可||

*これらの各リソースには、個人データを含む "作成者" および "変更者" のレコードが含まれます。 セキュリティ上の理由から、これらのレコードはリソースが削除されるまで保持されます。

** Common Data Service  データベースが含まれる環境では、環境のアクセス許可 (たとえば、環境作成者および環境管理者のロールが割り当てられているユーザー) が、Common Data Service にレコードとして格納されます。 Common Data Service を使用するユーザーのDSRへの応答方法に関するガイダンスについては、[Common Data Service 顧客データに対する DSR の実行](https://go.microsoft.com/fwlink/?linkid=872251)を参照してください。

手動での確認が必要なデータとリソースのため、Power Automate  では特定のユーザーの個人データの検索または変更を行う以下のエクスペリエンスが提供されています。

* **Web サイト アクセス:** [Power Apps 管理センター](https://admin.powerapps.com/)、または [Power Platform 管理センター](https://admin.powerplatform.microsoft.com/) にサインインします

* **PowerShell アクセス:**  [Power Apps 管理者 PowerShell コマンドレット](https://go.microsoft.com/fwlink/?linkid=871804) 

次に示すのは、リソースの種類ごとに各個人データの種類を削除するために管理者が使用できるエクスペリエンスの詳細です:

|個人データを含むリソース|Web サイト アクセス|PowerShell アクセス|自動削除|
|-----|----|----|----|
|システムによって生成されたログ|[Office 365 サービス トラスト ポータル](https://servicetrust.microsoft.com/)|||
|環境|Power Automate 管理センター|Power Apps コマンドレット||
|環境アクセス許可*|Power Automate 管理センター|Power Apps コマンドレット||
|実行履歴||| 28 日間の保持ポリシーにより削除|
|アクティビティ フィード |||28 日間の保持ポリシーにより削除|
|ユーザーのジョブ|| ||
|フロー|Power Automate メーカー ポータル**|||
|フロー アクセス許可|Power Automate メーカー ポータル|||
|ユーザーの詳細||Power Apps コマンドレット||
|接続|Power Automate メーカー ポータル| ||
|接続のアクセス許可|Power Automate メーカー ポータル| ||
|カスタム コネクタ|Power Automate メーカー ポータル| ||
|カスタム コネクタのアクセス許可|Power Automate メーカー ポータル| ||
|承認履歴|Microsoft Power Apps メーカー ポータル*|||

* Common Data Service の導入により、環境内にデータベースが作成された場合、環境のアクセス許可とモデル駆動型アプリのアクセス許可が、Common Data Service 内のレコードとして格納されます。 Common Data Service を使用するユーザーのDSRへの応答方法に関するガイダンスについては、[Common Data Service 顧客データに対する DSR の実行](https://go.microsoft.com/fwlink/?linkid=872251)を参照してください。

\*\* 管理者は、Power Automate フロー管理センターからアクセス権を割り当てられている場合、Power Automate 作成者ポータルからのみ、これらのリソースにアクセスできます。

## <a name="manage-delete-requests"></a>削除要求を管理する

以下の手順では、存在する管理機能を使用して GDPR の削除要求に対応する方法を説明します。 これらの手順は、以下の順序で実行する必要があります。

> [!IMPORTANT]
> データの破損を避けるため、以下の手順の順序に従ってください。
>
>

## <a name="list-and-re-assign-flows"></a>フローを一覧表示して再割り当てを行う

これらの手順では、いなくなるユーザーの既存のフローをコピーします。 コピーに新しい所有者を割り当てた場合、これらのフローは既存のビジネス プロセスを引き続きサポートできます。 これらのフローをコピーすることは、いなくなるユーザーへの個人識別子リンクを削除するのに重要であり、フローが他の API および SaaS アプリケーションと接続するように新しい接続を確立する必要があります。

1. [Power Platform 管理センター](https://admin.powerplatform.microsoft.com/)にサインインし、削除されたユーザーが所有するフローを含む環境を選択します。

    ![環境を表示する](./media/gdpr-dsr-delete/view-environments.png)

1. **リソース** > **フロー** の順に選択し、再割り当てするフローのタイトルを選択します。

    ![フローを表示する](./media/gdpr-dsr-delete/admin-view-flows.png)

1. **共有の管理** を選択します。

    ![共有を管理する](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. 右端近くに表示される **共有** パネルで、自分自身を所有者として追加し、**保存** を選択します。

    ![フローを共有する](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. [Power Automate](https://flow.microsoft.com/) にサインインし、 **マイ フロー** を選択し、**チーム フロー** を選択します：

1. コピーするフローの省略記号 **(… )** を選択して、**名前を付けて保存** を選択します。

    ![フローの名前を付けて保存](./media/gdpr-dsr-delete/flow-save-as.png)

1. 必要に応じて接続を構成し、**続行** を選択します。

1. 新しい名前を指定し、**保存** を選択します。

    ![フローのコピーを作成する](./media/gdpr-dsr-delete/create-copy-flow.png)

1. この新しいバージョンのフローが **マイ フロー** に表示され、必要に応じて他のユーザーと共有できます。

    ![チームのフロー](./media/gdpr-dsr-delete/team-flows.png)

1. 元のフローを削除するには、削除するフローの省略記号 **(…)** を選び、**削除** を選んでから、メッセージが表示されたら再び **削除** を選びます。 この手順では、ユーザーと Power Automate の間のシステムの依存関係に含まれる、基になっている個人識別子も削除されます。

    ![フローの削除の確認](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. **マイ フロー** を開き、切り替えコントロールを **オン** にして、コピーしたフローを有効にします。

    ![フローの有効化](./media/gdpr-dsr-delete/toggle-on.png)

1. コピーが、元のバージョンと同じワークフロー ロジックを実行するようになります。

## <a name="delete-approval-history-from-power-automate"></a>Power Automate から承認履歴を削除する

 Power Automate の承認データは、現在または以前のバージョンの Common Data Service に格納されています。 承認には、承認の割り当ておよび承認応答に含まれるコメントの形式で、個人情報が存在します。 管理者は、次の手順でそのデータにアクセスできます:

1. [PowerApps](https://make.powerapps.com/) にサインインする。

1. **データ** を選んでから、**エンティティ** を選びます。

1. **Flow 承認**  エンティティの省略記号 **(…)** を選んでから、Microsoft Excel でデータを開きます。

1. Microsoft Excel で、必要に応じて承認データを検索し、フィルター処理して、削除します。

Common Data Service を使用するユーザーのDSRへの応答方法に関する詳細なガイダンスについては、[Common Data Service 顧客データに対する DSR の実行](https://go.microsoft.com/fwlink/?linkid=872251)を参照してください。


## <a name="delete-connections-created-by-a-user"></a>ユーザーによって作成された接続を削除する

接続は、他の API や SaaS システムとの接続を確立するために、コネクタと組み合わせて使われます。  接続には、それらを作成したユーザーへの参照が含まれているため、ユーザーへの参照を削除するために削除できます。

Power Apps Maker PowerShell コマンドレット

ユーザーは、[Power Apps 作成者 PowerShell コマンドレット](https://go.microsoft.com/fwlink/?linkid=871448) の Remove-Connection 機能を使って、すべての接続を削除できます。

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-AdminPowerAppConnection | Remove-Connection
```

Power Apps 管理者 PowerShell cmdlets

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all connections for the DSR user and deletes them 
Get-AdminPowerAppConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection 

```

## <a name="delete-the-users-permissions-to-shared-connections"></a>共有接続に対するユーザーのアクセス許可を削除する

Power Apps Maker PowerShell コマンドレット

ユーザーは、[Power Apps 作成者 PowerShell コマンドレット](https://go.microsoft.com/fwlink/?linkid=871448) の Remove-ConnectionRoleAssignment 機能を使って、共有接続に対するすべての接続ロールの割り当てを削除できます。

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

Power Apps 管理者 PowerShell cmdlets

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all shared connections for the DSR user and deletes their permissions 
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment  

```
> [!NOTE]
> 接続リソースを削除しないと、所有者のロール割り当てを削除することはできません。
>
>

## <a name="delete-custom-connectors-created-by-the-user"></a>ユーザーによって作成されたカスタム コネクタを削除する

カスタム コネクタは、既存の標準コネクタを補完し、他の API、SaaS、およびカスタム開発システムへの接続を可能にします。 カスタム コネクタにはそれを作成したユーザーへの参照が含まれ、結果として、ユーザーへの参照を除去するために削除できます。

Power Apps Maker PowerShell コマンドレット

ユーザーは、[Power Apps 作成者 PowerShell コマンドレット](https://go.microsoft.com/fwlink/?linkid=871448) の Remove-Connector 機能を使って、すべてのカスタム コネクタを削除できます。

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

Power Apps 管理者 PowerShell cmdlets
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connectors created by the DSR user and deletes them 
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector  

```

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>共有カスタム コネクタに対するユーザーのアクセス許可を削除する

Power Apps Maker PowerShell コマンドレット

ユーザーは、[Power Apps 作成者 PowerShell コマンドレット](https://go.microsoft.com/fwlink/?linkid=871448) の Remove-ConnectorRoleAssignment 機能を使って、共有接続に対するすべての接続ロールの割り当てを削除できます。

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

Power Apps 管理者 PowerShell cmdlets
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connector role assignments for the DSR user and deletes them 
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment  

```

> [!NOTE]
> 接続リソースを削除しないと、所有者のロール割り当てを削除することはできません。
>
>


## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>ユーザーによって作成されたすべての環境を削除または再割り当てする

管理者は、ユーザーが作成した各環境に対するユーザーの DSR 削除要求を処理するときに、2 つのことを決定します:

1. 環境が組織内のどのユーザーによっても使われていないことを確認した場合は、環境を削除できます
1. 環境がまだ必要であると判断した場合は、環境を削除せず、自分自身 (または、組織内の別のユーザー) を環境管理者として追加できます。
> [!IMPORTANT]
> 環境を削除すると、すべてのアプリ、フロー、接続など、環境内のすべてのリソースが完全に削除されるため、削除する前に環境の内容を確認してください。
>
>

## <a name="give-access-to-a-users-environments-from-the-power-automate-admin-center"></a>Power Automate 管理センター からユーザー環境へのアクセスを許可する

管理者は、[Power Platform 管理センター](https://admin.powerplatform.microsoft.com/) から、特定のユーザーによって作成された環境への管理アクセス権を付与できます。 環境の管理について詳しくは、 [Power Automate 内の環境を使用する](https://docs.microsoft.com/flow/environments-overview-admin)をご覧ください。

## <a name="delete-the-users-permissions-to-all-other-environments"></a>他のすべての環境に対するユーザーのアクセス許可を削除する

ユーザーには環境内のアクセス許可 (環境管理者、環境作成者など) を割り当てることができ、アクセス許可は "ロールの割り当て" として Power Automate サービスに格納されます。

Common Data Service の導入により、環境内にデータベースが作成された場合、これら役割の割り当てが、Common Data Service 内のレコードとして格納されます。

環境でのユーザーのアクセス許可の削除についての詳細は、[Power Automate 内の環境を使用する](https://docs.microsoft.com/flow/environments-overview-admin)をご覧ください。

## <a name="delete-gateway-settings"></a>ゲートウェイ設定を削除する

オンプレミス データ ゲートウェイのデータ対象者削除依頼への応答に関しては、[こちら](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration) を参照してください。

## <a name="delete-user-details"></a>ユーザーの詳細を削除する

ユーザーの詳細では、ユーザーと特定のテナント間のリンクが提供されます。 このコマンドを実行する前に、このユーザーのすべてのフローを再割り当てまたは削除していることを確認します。 完了したら、管理者は **Remove-AdminFlowUserDetails** コマンドレットを呼び出し、ユーザーのオブジェクト ID を渡すことで、ユーザーの詳細を削除できます。

Power Apps 管理者 PowerShell cmdlets
```PowerShell
Add-PowerAppsAccount
Remove-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

> [!IMPORTANT]
> ユーザーがまだ個別またはチーム フローを所有している場合、このコマンドではエラーが返されます。 これを解決するには、このユーザーの残りのフローやチーム フローをすべて削除し、もう一度コマンドを実行します。
>
>

## <a name="delete-the-user-from-azure-active-directory"></a>Azure Active Directoryからユーザーを削除する

上記の手順が完了後は、最後に [Office 365 サービス トラスト ポータル](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) で参照できる Azure データ主体の要求の GDPR ドキュメントの手順に従って、Azure Active Directory 用のユーザーのアカウントを削除してください。

## <a name="delete-the-user-from-unmanaged-tenant"></a>アンマネージド テナントからユーザーを削除する

アンマネージド テナントのメンバーの場合は、[職場または学校のプライバシー ポータル](https://go.microsoft.com/fwlink/?linkid=873123) から **アカウント閉鎖** アクションを実行する必要があります。

マネージドまたはアンマネージド テナントのユーザーかどうかを確認するには、次のアクションを実行します。

1. ブラウザで次の URL を開き、URL で電子メール アドレスを必ず置き換えてください: [https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1](https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1)
1. **アンマネージド テナント** のメンバーである場合、応答に `"IsViral": true` が表示されます。

    {

     "ログイン"："foobar@unmanagedcontoso.com"

    "DomainName": "unmanagedcontoso.com",

    "IsViral": **true**,
    
    }

1. それ以外の場合、マネージド テナントに属します。
