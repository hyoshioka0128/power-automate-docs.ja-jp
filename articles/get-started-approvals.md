---
title: Power Automate の承認を開始します。  | Microsoft Docs
description: Power Automate 承認に関するアクセス許可と一般的な詳細を確認します。
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
ms.date: 08/29/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c94ca32053c3326c56e4f50137065efe9b303fbb
ms.sourcegitcommit: df7fb20065cfafc153b4bc4019dff2c94f4ef567
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "4553124"
---
# <a name="get-started-with-approvals"></a>承認を開始する

承認フローは承認要求を自動化して、人間による意思決定とバックグラウンドの自動化を組み合わせ、ビジネス ユーザーが重要なタスクに集中できるようにします。

## <a name="prerequisites"></a>前提条件

承認の開始に必要なものを以下に示します。

- Microsoft Dataverse データベースを作成するアクセス許可。
- フローを作成するライセンス。


## <a name="permissions-to-create-a-dataverse-database"></a>Dataverse データベースを作成するためのアクセス許可

作成した承認フローは、Dataverse に保存されます。 最初に既定ではない環境に存在するフローで承認コネクタを使用すると、システムは自動的にデータベースをプロビジョニングします。 正常に実行するためには、最初の承認フローを実行するユーザーがその環境の管理者ロールを持っている必要があります。

データベースのプロビジョニングが完了するまでに数分かかる場合があり、フローを初めて実行する際はこの遅延は明らかです。 承認フローを作成する他のユーザーに対して、環境の昇格したアクセス許可は必要ありません。

>[!NOTE]
>既定の環境を使用している場合は、Dataverse データベースをプロビジョニングする必要はありません。 

## <a name="license-to-create-flows"></a>フローを作成するライセンス

承認コネクタは標準のコネクタなので、承認フローを作成する際は Power Automate へのアクセスと標準コネクタの使用を許可するライセンスで十分です。

これは、Power Automate、Office 365、または Power Automate 機能を搭載する Dynamics 365 のライセンスである可能性があります。 これらの Office 365 と Dynamics 365 ライセンスの一覧は [Microsoft Power Apps と Power Automate のライセンス ガイド](https://go.microsoft.com/fwlink/?linkid=2085130) でご確認ください。


## <a name="assign-approvals-to-any-user-in-your-tenant"></a>テナントで任意のユーザーに承認を割り当てる

現在の Dataverse 環境または Azure Active Directory (Azure AD) テナントのユーザー (ゲスト ユーザーも含む) に承認を割り当てることができます。 

現在の環境に存在しないユーザーに承認を割り当てる場合は、自動的に追加されるため応答を処理して承認履歴で保持できます。 

これは以下のテナント構成で許可されていません:

- Azure Active Directory (Azure AD) の AllowAdHocSubscriptions 設定が無効の場合。 この場合、テナント管理者に有効化を依頼できます。 この詳細はセルフサービス サインアップでご確認ください。
- セキュリティ グループを使用して、Dataverse 環境にアクセスできるユーザーを制御している場合。
- Power Automate [米国政府機関プラン](https://docs.microsoft.com/power-automate/us-govt)。


承認要求をユーザーに割り当てると、Power Automate、Office 365、または Power Automate 機能を搭載する Dynamics 365 ライセンスを持つ場合に、Outlook の電子メール、Teams のアダプティブ カード、Power Automate アクション センターから直接応答できます。 これらの Office 365 と Dynamics 365 のライセンス一覧は Microsoft Power Apps と Power Automate のライセンス ガイドでご確認ください。

## <a name="next-steps"></a>次の手順

- [承認フロー](modern-approvals.md) を作成する






 
