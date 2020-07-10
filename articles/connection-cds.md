---
title: Common Data Serviceで自動フローを作成する | Microsoft Docs
description: Common Data Service の接続と Power Automate を使用してワークフローを作成する
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
ms.openlocfilehash: ea1c52933af3c42397004ae62d15e0475e051f14
ms.sourcegitcommit: aec3a74472b4e6eb70ed4554d14b57a7324d123d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "3498584"
---
# <a name="create-an-automated-flow-by-using-common-data-service"></a>Common Data Service を使用して自動化されたフローを作成する

>[!IMPORTANT]
>Common Data Service に接続できるコネクタは 3 つ存在します。 推奨される [Common Data Service（現在の環境）コネクタ](./connection-cds-native.md) を使用してください。 この記事に記載している **Common Data Serviceコネクタ**、[Dynamics 365 Connector](https://docs.microsoft.com/connectors/dynamicscrmonline/) は、推奨コネクタが使用できない場合にご利用いただけます。


Common Data Service コネクタを使用すると、Common Data Service 内で作成、更新されるイベントによって開始するフローを作成できます。 さらに、Common Data Service 内のレコードに対して、作成、更新、取得、削除のアクションを実行できます。

## <a name="initiate-a-flow-from-common-data-service"></a>Common Data Service からフローを開始する

次のいずれかのトリガーを使用してフローを開始できます。

- レコードが選択された場合
- レコードが作成されたとき
- レコードが削除されたとき
- レコードが更新されたとき


> [!div class="mx-imgBorder"]
> ![トリガーの選択](./media/cds-connector/Triggers.png)

選択したトリガーが環境の選択をする必要がある場合は、 `(Current)` を選択できます。これにより、Power Automate を実行する環境内のデータベースが常に使用されます。 フローが特定の環境におけるイベントに基づいて常にトリガーされるようにする場合は、その環境を選択します。

> [!div class="mx-imgBorder"]
> ![環境の選択](./media/cds-connector/Environments.png)

スコープを使用して、フローが実行されるのが、自分が新しいレコードを作成したときか、部署内のユーザーによって新しいレコードが作成されたときか、または組織内の任意のユーザーによって新しいレコードが作成されたときかを決定できます。

> [!div class="mx-imgBorder"]
> ![スコープの選択](./media/cds-connector/Scopes.png)

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

> [!div class="mx-imgBorder"]
> ![フィルター属性](./media/cds-connector/FilterAttributes.png)

## <a name="trigger-privileges"></a>トリガーの権限

レコードの作成、更新、削除に基づいてトリガーされるフローを作成するには、コールバック登録 エンティティに対する作成、読み取り、書き込み、削除のユーザー レベル権限が必要となります。 さらに、定義されたスコープによっては、ユーザーは少なくとも同じエンティティの同等のレベルの読み取り権限が必要となる場合があります。  環境のセキュリティの詳細については、[こちらを参照してください](https://docs.microsoft.com/power-platform/admin/database-security)。

## <a name="write-data-into-common-data-service"></a>Common Data Service にデータを書き込む

Common Data Service にデータを書き込むには、次のいずれかのアクションを使用します：

- 新しいレコードを作成します
- レコードの更新

特定のユーザーが新しいアカウント レコードを作成したときのフォロー アップ タスクを作成する例を次に示します。  

> [!div class="mx-imgBorder"]
> ![フォローアップ タスク](./media/cds-connector/Regarding.png)

## <a name="advanced-concepts"></a>高度な概念

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>顧客、所有者、関連の各フィールドにデータを書き込む

顧客、所有者、関連の各フィールドにデータを書き込むには、2 つのフィールドを設定する必要があります。

| フィールドのカテゴリ | 設定の例 |
| --- | --- |
| 関連 | 関連とは、 レコードの ID (アカウント ID など) と一覧から選択した関連の種類です。 |
| 顧客 | レコードの ID と一覧から選択した顧客の種類を表します。 |
| 所有者  | システム ユーザーまたはチームの ID と、一覧から選択した顧客の種類を表します。 |

### <a name="enable-upsert-behavior"></a>upsert 動作を有効化する

**レコードを更新する**コマンドを利用して upsert アクションを指定することができます。これにより、レコードが既に存在する場合はレコードを更新するか、新しいレコードを作成します。 upsert を呼び出すには、エンティティと GUID キーを指定します。 指定した種類とキーを持つレコードが存在する場合は、更新が行われます。 それ以外の場合は、指定したキーを持つレコードが作成されます。

### <a name="trigger-behavior"></a>トリガーの動作

レコードの更新に対してトリガーが登録されている場合は、指定されたレコードに対する*コミットされた*更新が行われる度にフローが実行されます。 サービスはフローを非同期的に呼び出し、呼び出しが発生した時点で取得されたペイロードを使用します。

ご利用の環境内にシステム ジョブのバックログがある場合は、フローの実行が遅延する可能性があります。  この遅延が発生した場合、フローは、フローを呼び出すシステム ジョブが実行されたときにトリガーされます。

