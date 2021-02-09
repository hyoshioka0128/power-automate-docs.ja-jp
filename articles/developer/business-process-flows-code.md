---
title: コードを使用してビジネス プロセス フローで作業をする | MicrosoftDocs
description: ビジネス プロセス フローをプログラム化して、より効率的で合理化されたビジネス プロセスを作成する方法について説明します。
ms.custom: ''
ms.date: 07/09/2018
ms.reviewer: ''
ms.service: flow
ms.topic: article
ms.assetid: 67d8cf80-9f77-4804-97a1-cf9f61417e83
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 84eef3c8f6590347759f66010da9c3b7ba3082c9
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709159"
---
# <a name="work-with-business-process-flows-using-code"></a>コードを使用してビジネス プロセス フローを操作する
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

*業務プロセス フロー* により、効率的で、より効率的な営業、サービス、および他の業務プロセスを作成できます。 それはエンティティ フォーム最上部に特別なコントロールを設定することで、ビジネス プロセスのビジュアル化を作成します。 ユーザーは完了に向け、営業、マーケティング、顧客サービス プロセスのさまざまなステージで導かれます。 各プロセスでは、複数のステージおよびステップをサポートします。 ステップを追加または削除したり、ステップの順序を変更したり、業務プロセス フローに新しいエンティティを追加できます。  
  
異なる業務プロセス フローのインスタンスが、同じエンティティ レコードに対して同時に実行できます。 ユーザーは同時のビジネス プロセス インスタンスを切り替えでき、プロセスの現在の段階での作業を再開できます。 

このトピックでは、業務プロセス フローをプログラムで使用する方法を説明します。

> [!NOTE]
> 業務プロセス フローを使用するためにコードを記述する必要はありません。 UI を使用したビジネス プロセス フローの作成と管理についての詳細は、[ビジネス プロセス フローの概要](../business-process-flows-overview.md) を参照してください  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>業務プロセス フローの前提条件 

UI フォームを更新したユーザー定義エンティティおよびエンティティによって、業務プロセス フローに参加できます。 更新された UI エンティティには `true`に設定された <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> プロパティがあります。 

業務プロセス フローのエンティティを有効にするには、`true`に <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> プロパティを設定します。

> [!IMPORTANT]
>  業務プロセス フローのエンティティを有効にするのは、一方向のプロセスです。 これを逆にはできません。

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>業務プロセス フローの定義
  
業務プロセス フローを定義するには、視覚的な業務プロセス フロー デザイナーを使用します。 詳細: [業務プロセス フローの作成](../create-business-process-flow.md)

既定では、業務プロセス フローのレコードは `Draft` 状態で作成されます。  

業務プロセス フローの定義は <xref:Microsoft.Dynamics.CRM.workflow> エンティティに格納され、業務プロセス フローのステージ情報は <xref:Microsoft.Dynamics.CRM.processstage> エンティティに保存されます。
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>業務プロセス フローのアクティブ化  
 プロセス フローを使用するには、その前に、それをアクティブ化する必要があります。 それをアクティブ化するには、`Workflow` エンティティの `prvActivateBusinessProcessFlow` の特権が必要です。 `Activated` に、`Workflow` エンティティ レコードの状態を設定するには <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> メッセージを使用します。 詳細については、[更新を使用して特化された操作を実行する](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update)を参照してください。 

 > [!NOTE]
 > 視覚的な業務プロセス フロー デザイナーを使用して、業務プロセス フローをアクティブ化することもできます。 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>業務プロセス フロー エンティティ 
 対応する `Workflow` エンティティ レコードの状態を変更したり、またはビジネス プロセス フロー デザイナーを使用して、ビジネス プロセス フローの定義をアクティブ化すると、以下の名前のユーザー定義エンティティが自動的に作成され、アクティブ化したビジネス プロセス フローの定義を保存します: "*\<activesolutionprefix>* _ *\<uniquename>*"、ここで uniquename は指定する名前から派生します。  
  
 たとえば、業務プロセス フローの定義の名前として「My Custom BPF」を指定して、アクティブ ソリューションの既定の発行元 (新規) を使用している場合、プロセス インスタンスの格納用に作成されたユーザー定義エンティティの名前は「new_mycustombpf」になります。  
  
 ビジネス プロセス フローの定義で `uniquename` の値が利用できない場合、たとえば、ビジネス プロセス フローが以前のバージョンからソリューションからインポートされた場合は、カスタム エンティティの既定の名前は `\<activesolutionprefix>_bpf_<GUID_BPF_Definition>` になります。  
  
> [!IMPORTANT]
>  サンプルのビジネス プロセス フローは、システム エンティティを使用して、対応するビジネス プロセス フロー インスタンス レコードを格納します。  
>   
>  ただし、作成する新しい業務プロセス フロー定義すべては、前に説明したように、ユーザー定義エンティティを使用してインスタンス レコードを保存します。 

次の方法のいずれかを使用して業務プロセス フロー エンティティの名前を取得できます。

- **UI を使用する**: 業務プロセス フロー エンティティを参照するためにカスタマイズ UI を使用します:

    ![UI を使用してビジネス プロセス フローエンティティを参照する](media/bpf-entity-name.png)
- **Web API を使用する**: 次の要求を使用します:

    **要求**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **回答**
    ```
    {  
    "@odata.context":"[Organization URI]/api/data/v9.0/$metadata#workflows(uniquename)",
    "value":[  
         {  
             "@odata.etag":"W/\"1084677\"",
             "uniquename":"new_mycustombpf",
             "workflowid":"2669927e-8ad6-4f95-8a9a-f1008af6956f"
         }
      ]
    }
    ```
- **組織サービスを使用する**: 次のコード サンプルを使用します :

    ```c#
    QueryExpression query = new QueryExpression
    {
        EntityName = "workflow",
        ColumnSet = new ColumnSet("uniquename"),
        Criteria = new FilterExpression
        {
            Conditions =
            {
                new ConditionExpression
                {
                    AttributeName = "name",
                    Operator = ConditionOperator.Equal,
                    Values = { "My Custom BPF" }
                }
            }
        }
    };
    Workflow Bpf = (Workflow)_serviceProxy.RetrieveMultiple(query).Entities[0]; 
    ```
> [!NOTE]
> <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity> プロパティは、ビジネス プロセス フローのエンティティに対しては `true` となります。 インスタンス内のビジネス プロセス フロー エンティティをすべて取得するには、次の Web API 要求を実行します :
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## <a name="manage-security-for-business-process-flows"></a>業務プロセス フローのセキュリティを管理する

業務プロセス フローをアクティブにすると自動的に作成され、業務プロセス フロー インスタンスを保存するカスタム エンティティは、 Common Data Service の他のカスタム エンティティと同様に、標準のセキュリティモデルに準拠します。 これは、それらのエンティティに付与される特権が、業務プロセス フローにおけるユーザー用のランタイム アクセス許可を定義することを意味します。

業務プロセス フローのユーザー定義エンティティは、組織のスコープがあります。 このエンティティに対する通常の作成、取得、更新、および削除の特権は、割り当てられた役割に基づいてユーザーが持つアクセス許可を定義します。 既定では、業務プロセス フローのユーザー定義エンティティが作成されると、**システム管理者** および **システム カスタマイザー** のセキュリティ ロールにのみアクセス許可が与えられ、他のセキュリティ ロールについては必要に応じて新しい業務プロセス フローのエンティティ (たとえば、**My Custom BPF**) に対してアクセス許可を明示的に付与する必要があります。

![セキュリティ ロールの管理](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## <a name="create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances"></a>ビジネス プロセス フローのエンティティ レコード (プロセス インスタンス) の作成、取得、更新、削除  
 業務プロセス フローの定義をアクティブ化する際に自動的に作成されるユーザー定義エンティティは、業務プロセス フローの定義のすべてのプロセス インスタンスを保存します。 カスタム エンティティは、Web API と CRM 2011 エンドポイントを使用したレコード (プロセス インスタンス) の標準的なプログラムによる作成と管理をサポートしています。

> [!IMPORTANT]
> エンティティ レコードの別のプロセス インスタンスへの切り替えは、UI (クライアント) を介して、またはこのセクションで利用可能な情報を使用してプログラムでのみサポートされています。 `SetProcess` メッセージ (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> または <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>) を使用して、対象のエンティティ レコードのプロセスをプログラム的に切り替える (別のビジネス プロセス フローをアクティブなプロセス インスタンスとして設定する) ことはできなくなります。 

 以下の例では、3 つのステージ (S1: アカウント、S2: アカウント、S3: コンタクト) を持つクロス エンティティのビジネス プロセス フロー 「カスタム BPF」 について考えてみます。 

 ![カスタム ビジネス プロセス フロー](media/sample-bpf.png)
 
### <a name="retrieve-all-the-records-instances-for-a-business-process-flow-entity"></a>ひとつつのビジネス プロセス フロー エンティティに対応するレコード (インスタンス) をすべて取得する
 ビジネス プロセス フローのエンティティ名が「new_mycustombpf」の場合、以下のクエリを使用して、ビジネス プロセス フロー エンティティのすべてのレコード (プロセス インスタンス) を取得します。  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

この時点で、何も存在しない場合は、応答でインスタンスを取得しない場合もあります。 このトピック後半の業務プロセス フローの定義のインスタンスを作成した後に、この要求を実行します。

> [!NOTE]
> 業務プロセス フロー エンティティの名前を取得する方法を確認するには、前のセクション、[業務プロセス フロー エンティティ](#business-process-flow-entity) を参照してください。
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>業務プロセス フロー エンティティ レコードの作成 (プロセス インスタンス) 

UI を使用しないでエンティティ レコードの別の業務プロセス フローに切り替えるには、業務プロセス フロー エンティティ レコード (プロセス インスタンス) をプログラムで作成します。 

業務プロセス フロー エンティティ レコードを作成するには、次の値を指定する必要があります: 
- `@odata.bind` コメントを使用して単一値ナビゲーション プロパティを設定することによって、主エンティティ レコードに、業務プロセス フロー エンティティ レコードを関連付けます。 業務プロセス フローの定義の主エンティティ レコードを指すナビゲーションプロバティ名を確認するには、[CSDL $metadata ドキュメント](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document) を使用します。 
- `@odata.bind` コメントを使用して単一値ナビゲーション プロパティを設定することによって、業務プロセス フローの定義で指定される有効なステージに業務プロセス フロー エンティティ レコードを関連付けます。 業務プロセス フローの定義のステージ レコードを指すナビゲーションプロバティ名 (通常 `activestageid`) を確認するには、[CSDL $metadata ドキュメント](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document) を使用します。

    また、ビジネス・プロセス・フロー定義のIDが 2669927e-8ad6-4f95-8a9a-f1008af6956fであると仮定して、次のWeb API要求を使用することでビジネス プロセス フロー定義のすべてのステージに関する情報を取得することができます:

    **要求**

    ```http
    GET [Organization URI]/api/data/v9.0/processstages?$select=stagename&$filter=processid/workflowid eq 2669927e-8ad6-4f95-8a9a-f1008af6956f HTTP/1.1
    ```

    **応答**

    ```http
    {
        "@odata.context": "[Organization URI]/api/data/v9.0/$metadata#processstages(stagename)",
        "value": [
            {
                "@odata.etag": "W/\"858240\"",
                "stagename": "S1",
                "processstageid": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b"
            },
            {
                "@odata.etag": "W/\"858239\"",
                "stagename": "S3",
                "processstageid": "a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a"
            },
            {
                "@odata.etag": "W/\"858238\"",
                "stagename": "S2",
                "processstageid": "19a11fc0-3398-4214-8522-cb2a97f66e4b"
            }
        ]
    }
    ```

次に、以下のリクエストを使用して、取引先企業レコード (ID=a176be9e-9a68-e711-80e7-00155d41e206) の業務プロセス フローの定義およびプロセス インスタンスの最初のステージとしてアクティブ ステージ セット、S1 (ID=9a9185f5-b75b-4bbb-9c2b-a6626683b99b) のインスタンスを作成します:

**要求**

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(a176be9e-9a68-e711-80e7-00155d41e206)",
    "activestageid@odata.bind": "/processstages(9a9185f5-b75b-4bbb-9c2b-a6626683b99b)"    
}
```

**応答**

```http
HTTP/1.1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.0/new_mycustombpfs(cc3f721b-026e-e811-80ff-00155d513100)
```

アクティブなステージを第 1 ステージ**_以外_* のステージとして設定したビジネス プロセス フロー定義のインスタンスを作成する場合は、リクエストに `traversedpath` を指定する必要があることに注意してください。 渡ったパスは業務プロセス フロー インスタンスのアクセス済みステージを表すプロセス ステージ ID のコンマ区切り文字列です。 次の要求は、取引先企業レコード(ID=679b2464-71b5-e711-80f5-00155d513100)のインスタンスを作成し、第二ステージS2 (ID=19a11fc0-3398-4214-8522-cb2a97f66e4b)としてアクティブ ステージ セットを作成します。

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(679b2464-71b5-e711-80f5-00155d513100)",
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"   
}
```

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>業務プロセス フロー エンティティ レコードの更新 (プロセス インスタンス)

次または前のステージへの移動、プロセス インスタンスの破棄、プロセス インスタンスを再アクティブ化、またはプロセス インスタンスの完了を行うためにプロセス インスタンスを更新できます。 

#### <a name="stage-navigation"></a>ステージ ナビゲーション

別のステージに移動するには、プロセス インスタンス レコードを更新して、アクティブ ステージ ID を変更し、それに応じて渡ったパスを更新する必要があります。 業務プロセス フロー インスタンスを更新する際、次または前のステージに移動するだけでなければならないことに注意してください。

ステージ ナビゲーションを行うには、更新する業務プロセス フロー インスタンスの ID が必要です。 業務プロセス フローのすべてのインスタンスを取得するには、[業務プロセス フロー エンティティのすべてのレコード (インスタンス) を取得する](#retrieve-all-the-records-instances-for-a-business-process-flow-entity) を先に参照してください。

更新するプロセス インスタンスの ID が dc2ab599-306d-e811-80ff-00155d513100 であると仮定して、次のリクエストを使用して、S1 から S2 にアクティブ ステージを更新します:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
Content-Type: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0

{
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"
}
```

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>プロセス インスタンスの状態の変更: 中止、再アクティブ化、または終了 

プロセス インスタンスには、*アクティブ*、**終了**、**中止** のうち 1 つを使用できます。 状態はプロセス インスタンス レコードの次の属性によって決まります:

- **statecode**: プロセス インスタンスの状態を表示します。

    |Value|ラベル|
    |-----|-----|
    |0    |Active|
    |1    |非アクティブ|

- **statuscode**: プロセス インスタンスの状態に関する情報を表示します。

    |Value|ラベル|
    |-----|-----|
    |1    |Active|
    |2    |終了|
    |3    |中止|

そのため、プロセスのインスタンスを **中止** するには、次の要求を使用して `statecode` と `statuscode` の値を適切に設定します:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{ 
    "statecode" : "1", 
    "statuscode": "3" 
}
```
 
> [!NOTE]
> 任意のステージでプロセス インスタンスを中止できます。

同様に、プロセス インスタンスを再アクティブ化するには、上記のコードの`statecode` と `statuscode` の値を **0** と **1** にそれぞれ置き換えます。

最後に、プロセス インスタンスの状態を、プロセス インスタンスの最終ステージでのみ有効な **終了** に設定するには、上記のコードの `statecode` と `statuscode` の値を **0** と **2** にそれぞれ置き換えます。

#### <a name="cross-entity-navigation"></a>複数のエンティティにまたがるナビゲーション

この例にて使用するエンティティ間のナビゲーションでは、プロセス インスタンスのアクティブ ステージを最終ステージS3(ID=a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a)に設定し、移動パスをそれに応じて更新し、ビジネス プロセス フロー定義に従って連絡先レコードをプライマリ エンティティー レコードとして設定する必要があります。

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{
    "activestageid@odata.bind": "/processstages(a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b,a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a",
    "bpf_contactid@odata.bind": "/contacts(0e3f10b0-da33-e811-80fc-00155d513100)"
}
``` 

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>業務プロセス フロー エンティティ レコードの削除 (プロセス インスタンス)

次の Web API 要求を使用します:

**要求**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**応答**

このレコードが存在する場合は、削除に成功したことを示す状態が 204 の通常応答を受け取ります。 エンティティが存在しなかった場合は、状態が 404 の応答を受け取ります。

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>RetrieveProcessInstances and RetrieveActivePath メッセージを使用する

`RetrieveProcessInstances` メッセージ (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> または <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) を使用して、すべての業務プロセス フローの定義でエンティティ レコードのすべての業務ビジネス フローのインスタンスを取得します。 エンティティに対して返される業務プロセス フロー インスタンスは、インスタンスの `modifiedon` 属性に基づいて順序付けられます。 たとえば、最後に変更された業務プロセス フロー インスタンスは、返されたコレクションの *最初* のレコードになります。 最後に変更された業務プロセス フロー インスタンスは、エンティティ レコードの UI でアクティブなインスタンスです。  
  
`RetrieveProcessInstances` メッセージを使用した結果としてエンティティ レコードに対して返された各業務プロセス フロー インスタンスのレコードは、アクティブ ステージの ID を `processstageid` 属性に格納します。この ID は、アクティブ ステージを検出して、前または次のステージに移動するために使用されます。 これを行うには、まず業務プロセス フロー インスタンスのアクティブ パスと、`RetrieveActivePath` メッセージ (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> または <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>) を使用してプロセス フロー インスタンスで使用できるステージを見つける必要があります。   
  
 アクティブ ステージと業務プロセス フロー インスタンスのアクティブ パス情報を取得したら、その情報を使用してアクティブ パスの前または次のステージに移動できます。 ステージの前方へのナビゲーションは、順番に実行する必要があります。つまり、アクティブなパスの次のステージに進むだけです。   
  
 [組織サービス](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata) を使用してコードがこれら 2 つのメソッドおよびステージ ナビゲーションを示す完全なサンプルについては、[サンプル: 業務プロセス フローの使用](sample-work-business-process-flows.md) を参照してください。 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>エンティティ レコードの作成時に業務プロセス フロー内を適用する

このセクションでは、Common Data Service で作成された新しいエンティティ レコードに業務プロセス フローを自動的に適用するための既定の動作と、それを上書きして任意の業務プロセス フローを新しいエンティティ レコードに適用する方法について説明します。

既定では、複数の業務プロセス フローが定義されているエンティティの場合、システムは次のマルチステップ ロジックを使用して新しいエンティティ レコードに業務プロセス フローを適用します。
1. 業務プロセス フロー定義レコードの **Workflow.PrimaryEntity** 属性に基づいて、新しいエンティティ レコードに適用可能なすべての業務プロセス フローを識別します。
2. 現在のユーザーがアクセスできる業務プロセス フロー定義を識別します。 業務プロセス フローへのアクセスがどのように決定され管理されるかについては、このトピックで前述した「[業務プロセス フローのセキュリティを管理する](#BPFSecurity)」を参照してください。<br/>  
3. システム内のすべての業務プロセス フローには、エンティティごとにグローバル順序が適用されます。 業務プロセス フローの順序は、**Workflow.ProcessOrder** 属性に格納されています。 エンティティの業務プロセス フローの定義は、この順序に基づいて並べ替えられ、順序の値が最も低いものが選択されます。
4. 最後に、エンティティ レコードがビジネス アプリ (アプリ モジュール) から作成された場合、新しいエンティティ レコードに自動的に適用される業務プロセス フローを選択するために、フィルタリングの追加のレベルが適用されます。 アプリで操作する場合、ユーザーはビジネス アプリに割り当てられたセキュリティ ロールゆえにアクセスできる該当するエンティティ、業務プロセス フロー、ビュー、およびフォームにしかアクセスできません。 
    - ビジネス アプリに業務プロセス フローが含まれない場合、手順 3 まで説明されたとおりに業務プロセス フローが適用されます。
    - ビジネス アプリに 1 つ以上の業務プロセス フローがある場合、アプリにある業務プロセス フローのみが適用されます。 この場合、ユーザーがビジネス アプリのコンテキスト内で作業しているなら、手順 3 の業務プロセス フローのリストはアプリ モジュール内にあるビジネス アプリの一部であるものにフィルタリングされ、プロセス順序に基づいて並べ替えられます。 
    - エンティティのビジネス アプリに業務プロセス フローがない場合、またはユーザーがアクセスできるものに業務プロセス フローがない場合、新しいエンティティ レコードに業務プロセス フローは適用されません。

新しいエンティティ レコードに自動的に適用される業務プロセス フローの既定のロジックは上書きできます。 上書きするには、新規エンティティ レコードを作成する際にエンティティの **ProcessId** 属性を次のいずれかの値に設定します。
- 新しいエンティティ レコードの業務プロセス フローの設定をスキップするには、**Guid.Empty** に設定します。 これは、エンティティ レコードを一括作成するものの業務プロセス フローを適用しない場合に行えます。
- 特定の業務プロセス フローのエンティティに設定します (エンティティ参照として)。 この場合、システムは既定ロジックの代わりに、選択した特定の業務プロセス フローを適用します。

新しいエンティティ レコードの作成時に **ProcessId** 属性の値を設定しない場合、システムは前述したように既定のロジックを適用します。

> [!NOTE]
> 新しいエンティティ レコードに自動的に適用される業務プロセス フローの既定のロジックを上書きすることは、プログラムでのみサポートされています。 UI を使用して行うことはできません。

## <a name="legacy-process-related-attributes-in-entities"></a>エンティティのレガシ プロセス関連属性

業務プロセス フローで有効なエンティティのレガシ プロセス関連属性 (**ProcessId**、**StageId**、**TraversedPath** など) は既に削除されています。 ターゲット エンティティ レコードのこれらレガシー プロセスの関連属性を操作することは、ビジネス プロセス フローの状態の一貫性を保証するものでなく、サポートされているシナリオでは *_ありません_*。 推奨されている方法は、セクション [業務プロセス フロー エンティティ レコードの作成、取得、更新、および削除 (プロセス インスタンス)](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances) の前半で説明されるように、業務プロセス フロー エンティティの属性を使用することです。

これの唯一の例外は、プログラムで _ *ProcessId** 属性を変更すると同時に、前のセクション: [エンティティ レコードの作成時にビジネス プロセス フローを適用する](#ApplyBPF) で説明されているように、ビジネス プロセス フローの既定のアプリケーションを新しいレコードで上書きすることです。

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>業務プロセス フローのクライアント側でのプログラムのサポート  
 フォーム スクリプトの中でビジネス プロセス フローと対話するために使用できるクライアント サイドのオブジェクトがあります。 業務プロセス フローは、プロセスがレコードに適用されたり、ステージが変更されたり、状態が `Active`、`Finished`、または `Aborted` に変更されたりするたびにクライアント側のイベントをトリガします。 詳細については、[ormContext.data.process (クライアント API 参照)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md) を参照してください。  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>プロセス、ステージおよび手順の最大数  
 エンティティごとの、アクティブ化された業務プロセス フローの最大数の既定値は 10 です。 `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity` 属性を使用して別の値を指定できます。 ただし、値が 10 より大きい場合、プロセスを切り替えるとき、または業務プロセス フローが割り当てられているレコードを開くときのシステム パフォーマンスが低下することがあります。 このことは、プロセスが複数のエンティティにまたがっている場合に特に顕著です。  
  
 次の設定はカスタマイズできません。  
  
-   プロセス内のエンティティ当たりの最大数が 30 です。  
  
-   各ステージのステップの最大数は 30 です。  
  
-   プロセス フローに参加できるエンティティの最大数は 5 です。  

