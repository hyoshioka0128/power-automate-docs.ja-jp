---
title: Dynamics 365 (online) でクラウド フローを作成する | Microsoft Docs
description: Dynamics 365 Connector の廃止。 Microsoft Dataverse (現在の環境) コネクタ、または Common Data Service コネクタを使用してください。
services: ''
suite: flow
documentationcenter: na
author: JimDaly
ms.reviewer: deonhe
ms.service: flow
ms.topic: article
ms.date: 05/31/2020
ms.author: jdaly
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c165b9c85eaeaf115d57c3b410deba136c80ba70
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4708751"
---
# <a name="create-a-cloud-flow-by-using-dynamics-365-online"></a>Dynamics 365 (online) を使用してクラウド フローを作成する

[!INCLUDE[cc-data-platform-banner](./includes/cc-data-platform-banner.md)]

> [!IMPORTANT]
> Dynamics 365 Sales、Dynamics 365 Customer Service、Dynamics 365 Field Service、Dynamics 365 Marketing、Dynamics 365 Project Service Automation などの Dynamics 365 アプリは、データ ソースとして [Microsoft Dataverse](/powerapps/maker/common-data-service/data-platform-intro) を使用します。
>
> [Dynamics 365 Connector](/connectors/dynamicscrmonline/)は廃止されますが、削除されるまでは機能し続けます。 詳細: [Dynamics 365 Connector が非推奨になりました](/power-platform/important-changes-coming#dynamics-365-connector-is-deprecated)。
> 
> 新しいフローには Dynamics 365 connector を使用しないでください。 可能な限り、[Dataverse (現在の環境) コネクタ](/connectors/commondataserviceforapps/)を使用してください。 Dataverse (現在の環境) コネクタで要件を満たせない場合は、[Common Data Service コネクタ](/connectors/commondataservice/) を使用してください。
>
> [Dataverse (現在の環境) コネクタ](/connectors/commondataserviceforapps/)は、最も多くの機能と最良のパフォーマンスを提供するため、まずはこれを選択してください。 ただし、現時点では、複数の環境に接続する機能などの Dynamics 365 と Common Data Service コネクタで提供されている機能には対応していません。 [Common Data Service コネクタ](/connectors/commondataservice/) は、Dynamics 365 connector と同様の機能を提供しますが、信頼性も大幅に向上します。


Dynamics 365 connector を使用すると、Dynamics 365 やその他のサービスでイベントが発生し、これにより Dynamics 365 やその他のサービスでアクションが実行された際に、開始されるフローを作成することができます。 

Power Automate では、お気に入りのアプリやサービス間で自動化されたワークフローを設定して、ファイルの同期、通知の取得、データの収集などを行うことができます。 詳細については、[Power Automateの使用を開始する](getting-started.md) を参照してください。

> [!IMPORTANT] 
> Power Automate トリガーを起動するには、フローと共にDataverse エンティティが使用する **変更の追跡** を有効にする必要があります。 詳細については、[変更の追跡を有効化してデータの同期をコントロールする](/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization)を参照してください。 

## <a name="create-a-cloud-flow-from-a-template"></a>テンプレートからクラウド フローを作成する

さまざまなテンプレートが用意されています。このいずれかを使用してクラウド フローを作成することができます。次に例を示します。

* オブジェクトが Dynamics 365 で作成されている場合は、SharePoint でリスト項目を作成します。
* Excel の表から Dynamics 365 の潜在顧客レコードを作成する。
* Dynamics 365 の取引先企業を Dynamics 365 for Operations の顧客にコピーします。

テンプレートからクラウド フローを作成するには、次の手順に従います。

1. [Power Automate Web サイト](https://flow.microsoft.com/)にサインインします。
2. **サービス** をクリックまたはタップし、**Dynamics 365** をクリックまたはタップします。
3. 複数のテンプレートが利用できます。 作業を開始するには、目的のテンプレートを選択します。

## <a name="create-a-task-from-a-lead"></a>潜在顧客からタスクを作成する

必要とする内容に対応するテンプレートが提供されていない場合は、一からクラウド フローを作成します。 このチュートリアルでは、Dynamics 365 で潜在顧客が作成されるたびに、 Dynamics 365 でタスクを作成する方法を説明します。

1. [Power Automate Web サイト](https://flow.microsoft.com/)にサインインします。
2. **自分のフロー** をクリックまたはタップし、**はじめから作成する** をクリックまたはタップします。
3. フロー トリガーの一覧で、**Dynamics 365 - レコードが作成されたとき** をクリックまたはタップします。
4. メッセージが表示されたら、Dynamics 365 にサインインします。
5. **組織名** 配下で、フローがリッスンする Dynamics 365 インスタンスを選択します。
6. **エンティティ名** 配下で、フローを開始するトリガーとして機能する、リッスンするエンティティを選択します。
   
     このチュートリアルでは、**潜在顧客** を選択します。
   
    ![フローの詳細](./media/connection-dynamics365/flow-details.png)
    > [重要] Dynamics 365 エンティティでフローをトリガーするには、エンティティの定義の **変更の追跡** が有効になっている必要があります。 詳細については、[変更の追跡を有効にしてデータ同期を制御する](/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization)を参照してください
    
7. **新しいステップ** をクリックまたはタップし、**アクションの追加** をクリックまたはタップします。
8. **Dynamics 365 – 新しいレコードの作成** をクリックまたはタップします。
9. **組織名** 配下で、フローによって作成されるレコードの Dynamics 365 インスタンスを選択します。 イベントがトリガーされるものと同じインスタンスである必要はないことに注意してください。
10. **エンティティ名** 配下で、イベントの発生時にレコードを作成するエンティティを選択します。
    
     このチュートリアルでは、**タスク** を選択します。
11. **サブジェクト** ボックスが表示されます。 このボックスをクリックまたはタップすると、動的コンテンツのウィンドウが表示され、このウィンドウでは以下のフィールドのいずれかを選択できます。
    
    * **姓**。 このフィールドを選択すると、タスクの作成時にタスクの **サブジェクト** フィールドに潜在顧客の姓が挿入されます。
    * **トピック**。 このフィールドを選択すると、タスクの作成時にタスクの **サブジェクト** フィールドに潜在顧客の **トピック** フィールドが挿入されます。
    
    このチュートリアルでは、**トピック** を選択します。
    
    ![フローのトピックの追加](./media/connection-dynamics365/flow-addtopic.png)
    
    > **ヒント :** 動的コンテンツのウィンドウで、**詳細を参照する** をクリックまたはタップすると、エンティティに関連付けられたその他のフィールドが表示されます。 たとえば、タスクの **サブジェクト** フィールドに、潜在顧客の **会社名**、**顧客**、**説明**、**電子メール** フィールドを取り込むことができます。
    > 
    > 
12. **フローの作成** をクリックまたはタップします。

## <a name="trigger-based-logic"></a>トリガーに基づくロジック

**レコードが作成されたとき**、**レコードが更新されたとき**、**レコードが削除されたとき** などのトリガーでは、イベントの発生から数分以内にフローが開始されます。  ごくまれに、フローがトリガーされるまでに最大で 2 時間ほど要する場合があります。

トリガーが発生すると、フローに通知が送信されますが、フローはアクションが実行された際に存在するデータに対して実行されます。  たとえば、新たなレコードが作成されたときにフローがトリガーされ、フローが実行される前にレコードを 2 回更新した場合、フローは最新のデータに対してのみ、 1 回だけ実行されます。

## <a name="specify-advanced-options"></a>詳細オプションの指定

クラウド フローにステップを追加する場合は、**詳細オプションの表示** をクリックまたはタップして、フロー内でのデータのフィルター処理の方法を制御するフィルターまたは並べ替えクエリを追加することができます。

たとえば、フィルター クエリを使用してアクティブな連絡先のみの取得や、姓で並べ替えることができます。 そのためには、OData フィルター クエリ **statuscode eq 1** を入力し、動的コンテンツのウィンドウから **姓** を選択します。 クエリによるフィルターと並べ替えの詳細については、[クエリ データ > 結果のフィルタリング](/powerapps/developer/common-data-service/webapi/query-data-web-api#filter-results) と [クエリ データ > 並び替え結果](/powerapps/developer/common-data-service/webapi/query-data-web-api#order-results)を参照してください。

  ![フローの並べ替えクエリ](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>詳細なオプションを使用する際のベスト プラクティス

フィールドに値を追加する際は、値を入力するか、動的コンテンツ ウィンドウに表示されるいずれかを選択するかにかかわらず、フィールドの種類を照合する必要があります。

| フィールドの種類 | 使用方法 | 参照先 | 名前 | データ型 |
| --- | --- | --- | --- | --- |
| テキスト フィールド |テキスト フィールドには、単一行のテキストやテキスト型フィールドである動的コンテンツが必要となります。 たとえば、**カテゴリ** フィールド、**サブカテゴリ** フィールドなどが含まれます。 |**設定** > **カスタマイズ** > **システムのカスタマイズ** > **エンティティ** > **タスク** > **フィールド** |**カテゴリ** |**1 行テキスト** |
| 整数フィールド |一部のフィールドには、整数や整数型フィールドの動的コンテンツが必要となります。 たとえば、**達成率**、**期間** などが含まれます。 |**設定** > **カスタマイズ** > **システムのカスタマイズ** > **エンティティ** > **タスク** > **フィールド** |**percentcomplete** |**整数** |
| 日付フィールド |一部のフィールドには、mm/dd/yyyy 形式で入力した日付、または日付型フィールドの動的コンテンツが必要となります。 たとえば、**作成日**、**開始日**、**実際の開始日**、**前回の保留時間**、**実際の終了日**、**期限** などが含まれます。 |**設定** > **カスタマイズ** > **システムのカスタマイズ** > **エンティティ** > **タスク** > **フィールド** |**createdon** |**日付と時間** |
| レコード ID と参照タイプの両方を必要とするフィールド |別のエンティティ レコードを参照するフィールドには、レコード ID と参照タイプの両方が必要となります。 |**設定** > **カスタマイズ** > **システムのカスタマイズ** > **エンティティ** > **アカウント** > **フィールド** |**accountid** |**主キー** |
|オプション セット|オプション セット フィールドでは、この種類のフィールドに既知の整数値を渡す必要があります。  Dynamics 365 のカスタマイズ領域では、オプション セットのバッキング整数フィールドを、それぞれのラベルと共に表示します。|設定 > カスタマイズ > システムのカスタマイズ > エンティティ > アカウント > フィールド | 優先する連絡方法| 整数|

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>レコード ID と参照タイプの両方を必要とするフィールドに関するその他の例

ここでは、以前の表を拡張して、動的コンテンツ リストから選択された値では動作しないフィールドの例を示します。 これらのフィールドには、Power Apps のフィールドに入力されているレコード ID と参照タイプの両方が必要です。

* **所有者** と **所有者の種類**。
  
  * **所有者** フィールドには、有効なユーザーまたはチーム レコード ID を入力する必要があります。
  * **所有者の種類** には、**システム ユーザー** または **チーム** を指定する必要があります。
* **顧客** と **顧客の種類**。
  
  * **顧客** フィールドには、有効なアカウント、または連絡先レコード ID を入力する必要があります。
  * **顧客の種類** には、**取引先企業** または **取引先担当者** を指定する必要があります。
* **関連** と **関連の種類**。
  
  * **関連** フィールドには、有効なレコード ID (アカウント レコード ID や連絡先レコード ID など) を入力する必要があります。
  * **関連の種類** には、レコードの参照タイプ (**取引先企業** や **取引先担当者** など) を指定する必要があります。

次の例では、タスクの **関連** フィールドにレコード ID を追加し、この ID に対応するアカウント レコードを追加します。

  ![フローのレコード ID とタイプ アカウント](./media/connection-dynamics365/flow-recordid-account.png)

この例では、ユーザーのレコード ID に基づいて特定のユーザーにタスクを割り当てます。

  ![フローのレコード ID とタイプ ユーザー](./media/connection-dynamics365/flow-recordid-user.png)

レコード ID の検索方法については、このトピック後半の [レコード ID の検索](#find-the-records-id) を参照してください。

> **重要 :** フィールドの説明が "内部利用専用" となっている場合、フィールドに値は含まれません。 これらのフィールドには、**渡されたパス**、**追加パラメーター**、**タイム ゾーン規則のバージョン番号** が含まれます。
> 
> 

## <a name="find-the-records-id"></a>レコード ID の検索

1. Dynamics 365 の Web アプリケーションで、アカウント レコードなどのレコードを開きます。
2. 操作ツール バーの **ポップ アウト**
   ![ポップアウト レコード](./media/connection-dynamics365/popout.png) をクリックまたはタップします (または、**リンクを電子メールで送信する** をクリックまたはタップして完全な URL を既定の電子メール プログラムにコピーします)。
   
    Web ブラウザーのアドレス バーで、URL のエンコード文字 %7b と  %7d の間にレコード ID が表示されます。
   
   ![recordId を表示するスクリーンショット](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>関連トピック

[クラウド フローのトラブルシューティング](fix-flow-failures.md)

[組織における Flow の Q & A](organization-q-and-a.md)

[よくあるご質問](frequently-asked-questions.md)

