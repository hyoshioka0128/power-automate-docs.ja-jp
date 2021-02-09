---
title: デスクトップ フローの共有と管理 | Microsoft Docs
description: デスクトップ フローの共有と管理
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
ms.date: 12/09/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f1cc9bfe7e3a9561ac324f529b2a2a20c3918746
ms.sourcegitcommit: 43547f1d30185888fade31d205ad4684e8529b47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4713474"
---
# <a name="manage-desktop-flows"></a>デスクトップ フローを管理する

デスクトップ フローを作成した後は、それらの状態の表示、編集、確認が必要となる場合があります。 これを行うには、**デスクトップ フロー** タブに移動します。

## <a name="list-of-desktop-flows"></a>デスクトップ フロー一覧

1. Power Automate にサインインします。
1. **マイ フロー** > **デスクトップ フロー** を選択します。

   ![すべてのデスクトップ フローの表示](../media/manage-desktop-flows/view-all.png "すべてのデスクトップ フローの表示")

このセクションから、新しいデスクトップ フローの作成や、既存のデスクトップ フローの編集または削除ができます。

## <a name="details-page"></a>詳細ページ

デスクトップ フローごとに詳細を確認するには、デスクトップ フローの一覧からその名前を選択します。 次のような詳細が表示されます:

-   各実行の詳細を含む実行履歴。
-   デスクトップ フローで使用されているアプリケーション、または Web サイト。

デスクトップ フローの詳細を確認するには、次の手順に従います:

1. Power Automate にサインインします。
1. **マイ フロー** > **デスクトップ フロー** を選択します。
1. 任意のデスクトップ フローを選択します。

   ![詳細を表示します](../media/manage-desktop-flows/view-details.png "詳細を表示します")

## <a name="share-desktop-flows"></a>デスクトップ フローの共有

デスクトップフローを組織内の他のユーザーと共有し、そのユーザーにフローのアクセス権限を付与することができます。

次の手順に従って、デスクトップ フローを共有します。

1. [Power Automate](https://powerautomate.com) にサインインします。
1. 画面の左側から **マイ フロー** を選択します。
1. **デスクトップ フロー** を選択します。
1. 所有しているフローを選択します。

   ![共有するフローを選択する](../media/manage-desktop-flows/select-one.png)

1. **共有** を選択します。
1. **人を追加する** フィールドを選択し、フローを共有する組織内の人物の名前を入力します。
1. **アクセスを許可する** を選択し、フローの共有先として **ユーザー** または **共同所有者** を選択します。
1. **共有** ボタンを選択します。

   ![グラフィカル ユーザー インターフェース、アプリケーションの説明は自動的に生成されます](../media/manage-desktop-flows/sharing-ux.png)

デスクトップフローを共有する際に使用できる 2 つのアクセス許可レベルは次のとおりです: 

1. **共同所有者**: このアクセスレベルは、共同所有者にそのデスクトップ フローへの完全なアクセス許可を与えます。 フローの編集、共有、削除ができます。

1. **ユーザー** : クラウド フローでそのデスクトップ フローのみを使用する権限があります。 このアクセス権限では、編集、削除、共有のアクセス許可は使用できません。 または、「名前を付けて保存」を使用してデスクトップ フローのコピーを作成し、独立して作業することもできます。

デスクトップ フローが共有されると、所有者と共同所有者は、デスクトップ フローの詳細ページで **アクセスの管理** のリンクを選択することで、各ユーザーのアクセスを変更することができます。

**既知の問題と制限事項:**

- 現在、表示できるのは所有するフロー実行のみです。 将来的には、共有者が全ユーザーの実行を閲覧できるようになる予定です。

- 現在、共同所有者とユーザーフローの一覧は、Power Automate ポータルでのみ閲覧可能です。 まもなく、Power Automate Desktop からも閲覧できるようになります。

- デスクトップ フローの共有機能は、現在のところ、最近作成された環境でのみ利用可能です。


## <a name="more-information"></a>詳細情報

- [デスクトップ フロー](create-flow.md)の作成。
- [デスクトップ フローの実行](run-desktop-flow.md)。
- [Windows レコーダー (V1) のフロー](create-desktop.md)の作成。
- [SeleniumIDE フロー](create-web.md)の作成。

