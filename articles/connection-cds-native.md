---
title: Common Data Service （現在の環境）のコネクターを使用して自動フローを作成する| Microsoft Docs
description: Common Data Service の（現在の環境）コネクターと Power Automate を使用してワークフローを作成する
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/26/2020
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5b144f376640c1de3a1bbd165850555eeb444663
ms.sourcegitcommit: 1ac37360193f30d33c9a689ae6fe9ca7c7d991f2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "3789821"
---
# <a name="create-an-automated-flow-by-using-common-data-service-current-environment"></a>Common Data Service （現在の環境）を使用して自動化されたフローを作成する

>[!IMPORTANT]
>Common Data Service に接続できるコネクタは 3 つ存在します。 この記事では、Common Data Service への接続に対して推奨される [Common Data Service (現在の環境) コネクタ](./connection-cds.md)について説明します。 推奨するコネクタが使用できない場合は、[Common Data Service Connector](./connection-cds.md) と [Dynamics 365 コネクタ](https://docs.microsoft.com/connectors/dynamicscrmonline/) も使用することができます。


作成したフローは、Common Data Service レコードが作成、更新、削除されたタイミングでトリガーできます。

さらに、Common Data Service 内のレコードに対して、作成、更新、取得、削除のアクションを実行できます。

## <a name="initiate-a-flow-with-common-data-service-current-environment"></a>Common Data Service（現在の環境）でフローを開始する

**レコードの作成、更新、削除時** トリガーを使用してフローを開始します：

   ![トリガーの選択](./media/cds-connector-native/native-trigger.png)

トリガーの選択後は、次の設定を行う必要があります：

- トリガーに使用する条件を入力します。
- エンティティの名前です。
- トリガーのスコープ。

### <a name="trigger-condition"></a>トリガー条件

これらの条件のいずれかを追加して、フローがトリガーされるタイミングを正確に決定できます。

   ![トリガーの選択](./media/cds-connector-native/trigger-conditions.png)

### <a name="the-entity-name"></a>エンティティの名前

トリガーが動作するエンティティを示す目的で使用可能な多数のエンティティのいずれかを選択します。

   ![トリガーの選択](./media/cds-connector-native/entity-names.png)

### <a name="scope"></a>Scope

スコープを使用して、自分、部署の誰か、組織内の任意のユーザーがレコードを作成した際にフローが実行されるかどうかを判断します。

![スコープの選択](./media/cds-connector-native/scopes.png)

各スコープの詳細は次のとおりです。

|Scope|トリガーのタイミング|
| --- | --- |
|部署 |自分の部署が所有しているレコードに対して、アクションが実行されます|
|組織全体|組織内またはデータベース内の任意のユーザーによってアクションが実行されます|
|親 : 下位の部署|自分の部署または配下の部署が所有しているレコードに対して、アクションが実行されます|
|User|自分が所有しているレコードに対して、アクションが実行されます|


レコードが更新されたときに実行されるトリガーには、フィルター処理の属性を使用することもできます。 これにより、定義された属性のいずれかが更新されたときにのみフローが実行されるようになります。

> [!IMPORTANT]
> フィルター属性を使用することで、不要なフローの実行を防ぎます。

このフローは、フローのユーザが所有する連絡先の姓、または名が更新されるたびにトリガーされます。

![フィルター属性](./media/cds-connector-native/filtering-attributes.png)

## <a name="trigger-privileges"></a>トリガーの権限

レコードの作成、更新、削除に基づいてトリガーされるフローを作成するには、**コールバック登録** エンティティに対する作成、読み取り、書き込み、削除のユーザー レベル権限が必要となります。 さらに、定義されたスコープによっては、ユーザーは少なくとも同じエンティティの同等のレベルの読み取り権限が必要となる場合があります。  環境のセキュリティの詳細については、[こちらを参照してください](https://docs.microsoft.com/power-platform/admin/database-security)。

## <a name="write-data-into-common-data-service"></a>Common Data Service にデータを書き込む

Common Data Service にデータを書き込むには、次のいずれかのアクションを使用します：

![フィルター属性](./media/cds-connector-native/actions.png)

**対象範囲** 部署のいずれかのユーザーによって、**アカウント** が **作成される** たびに、名前と年間収益を含む通知を送信するフローの例です。

> ![フォローアップ タスク](./media/cds-connector-native/example-flow.png)

## <a name="advanced-concepts"></a>高度な概念

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>顧客、所有者、関連の各フィールドにデータを書き込む

顧客、所有者、関連の各フィールドにデータを書き込むには、2 つのフィールドを設定する必要があります。

| フィールドのカテゴリ | 設定の例 |
| --- | --- |
| 関連 | 関連とは、 レコードの ID (アカウント ID など) と一覧から選択した関連の種類です。 |
| 顧客 | レコードの ID と一覧から選択した顧客の種類を表します。 |
| 所有者  | システム ユーザーまたはチームの ID と、一覧から選択した顧客の種類を表します。 |

### <a name="enable-upsert-behavior"></a>upsert 動作を有効化する

**レコードを更新する** アクションを利用して upsert アクションを指定することができます。これにより、レコードが既に存在する場合はレコードを更新するか、新しいレコードを作成します。 upsert を呼び出すには、エンティティと GUID キーを指定します。 指定した種類とキーを持つレコードが存在する場合は、更新が行われます。 それ以外の場合は、指定したキーを持つレコードが作成されます。

### <a name="trigger-behavior"></a>トリガーの動作

レコードの更新に対してトリガーが登録されている場合は、指定されたレコードに対する*コミットされた*更新が行われる度にフローが実行されます。 サービスはフローを非同期的に呼び出し、呼び出しが発生した時点で取得されたペイロードを使用します。

> [!NOTE]
> 数秒以内に 2 つの更新が発生した場合には、最新バージョンのコンテンツフローが複数回トリガーされる可能性があります。

ご利用の環境内にシステム ジョブのバックログがある場合は、フローの実行が遅延する可能性があります。 この遅延が発生した場合、フローを開始するシステムジョブが実行された際にフローがトリガーされます。



