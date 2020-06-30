---
title: 管理者に関する環境の概要 | Microsoft Docs
description: Power Automate で環境の使用、作成、管理をする
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/07/2020
ms.author: sunayv
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: e1c2a93fb011b6f20ecaf79fb0bf95212a2506d4
ms.sourcegitcommit: 2c9cffb59ef2382648a80966ebbf0fe8eafebe64
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2020
ms.locfileid: "3354439"
---
# <a name="using-environments-within-power-automate"></a>Power Automate 内の環境を使用する


## <a name="benefits"></a>給付金

環境には次の利点があります:

* **データのローカリティ**: 環境はさまざまなリージョンで作成され、その地理的な場所にバインドされます。 環境内にフローを作成すると、そのフローはその地理的な場所のすべてのデータセンターにルーティングされます。 これには、パフォーマンス上の利点もあります。

    ユーザーがヨーロッパにいる場合は、ヨーロッパ リージョンで環境を作成して使用します。 米国にユーザーがいる場合は、米国のユーザー環境を作成し使用します。 

    > [!IMPORTANT]
    > 環境を削除した場合、その環境内のすべてのフローも削除されます。 これは、接続、ゲートウェイ、Power Apps など、その環境で作成するすべての項目に適用されます。
* **データ損失の防止**: 管理者としては、内部の場所 (給与情報を含む *OneDrive for Business*や SharePoint リストなど) からデータを取得し、そのデータを公開の場所 (*Twitter* など) に投稿するようなフローは望ましくありません。 Power Automate の展開内のデータを共有できるサービスを制御するには、データ損失防止を使います。

    たとえば、*SharePoint* と *OneDrive for Business* サービスを、ビジネス データのみのポリシーに追加することができます。 この環境に作成されるすべてのフローは、 *SharePoint*サービスと *OneDrive for Business*  サービスを使うことができます。 しかし、ビジネス データのみのポリシーに含まれていない他のサービスとデータを共有することはできません。

  > [!NOTE]
  > データ損失防止は、P2 ライセンスなど、いくつかのライセンス SKU で使用できます。

* **すべてのリソースの分離境界**: どのフロー、ゲートウェイ、接続、カスタム コネクタなども、固有の環境に存在します。 他の環境には存在しません。
* **Common Data Service**: サービスにデータを挿入するフローを作成する場合は、このサービスを使います。

  * Excel ファイルにデータを挿入し、OneDrive などのクラウド ストレージ アカウントに Excel ファイルを格納します。
  * SQL Database を作成してから、そこにデータを格納します。
  * Common Data Service を使ってデータを格納する。

    すべての環境は、Common Data Service のフロー用に最大で 1 個のデータベースを持つことができます。 Common Data Service へのアクセスは、購入したライセンスによって異なります。Common Data Service は、無料ライセンスには含まれていません。

## <a name="limitations"></a>制限

環境には多くの利点がありますが、新たな制限も生じます。 環境が分離境界であるという事実は、*異なる* 環境のリソースを参照するリソースは持てないことを意味します。 たとえば、ある環境でカスタム コネクタを作成し、そのカスタム コネクタを使うフローを別の環境に作成することはできません。

## <a name="use-the-default-environment"></a>既定の環境を使用する

**既定** の環境はすべてのユーザーによって共有され、すべてのユーザーは **既定** の環境内にフローを作成できます。

> [!TIP]
> プレビュー ユーザーの場合、既存のフローはすべて既定の環境にあります。 *プレビュー ユーザー* とは、一般提供 (GA) リリース前に Power Automate を使用していたユーザーのことです。

## <a name="the-admin-center"></a>管理センター

管理者は、管理センターを使用して環境を作成および管理します。 管理センターを開くには 2 つの方法があります:

### <a name="option-1-select-settings"></a>オプション 1: 設定を選択する

1. [flow.microsoft.com](https://flow.microsoft.com) にサインインする。
1. 設定の歯車アイコンを選択し、一覧から **管理センター** を選択します。

   ![設定と管理者ポータル](./media/environments-overview-admin/settings.png)
1. 管理センターが開きます。

### <a name="option-2-open-adminflowmicrosoftcom"></a>オプション 2: admin.flow.microsoft.com を開く

[admin.flow.microsoft.com](https://admin.flow.microsoft.com) に移動し、職場アカウントでサインインします。

## <a name="create-an-environment"></a>環境を作成する

1. [Power Automate 管理センター](https://admin.flow.microsoft.com) で、**環境** を選択します。 既存の環境がすべて表示されます: ![環境](./media/environments-overview-admin/environments-list.png)
2. **新しい環境** を選択し、必要な情報を指定します:


   |     プロパティ     |                                                 内容                                                 |
   |------------------|-------------------------------------------------------------------------------------------------------------|
   | 環境名 |              `Human Resources` や `Europe flows` など、環境の名前を入力します。              |
   |      地域      | 環境をホストする場所を選択します。 最高のパフォーマンスを得るには、ユーザーに最も近いリージョンを使用します。 |
   | 環境の種類 |                  ライセンスに基づいて、環境の種類を選択します: 運用または試用版。                   |

     ![環境の設定](./media/environments-overview-admin/new-environment-dialog.png)
3. **環境の作成** をクリックします。
4. **データベースの作成** や **スキップ** のオプションがあります。
5. **データベースの作成** を選択すると、データベースの **通貨** と **言語** の入力を求められます。 さらに、サンプル アプリとデータを展開することもできます。

   ![データベース構成の設定](./media/environments-overview-admin/create-database-dialog2.png)


次に、ユーザーを環境に追加できます。

## <a name="manage-your-existing-environments"></a>既存の環境を管理する

1. [Power Automate 管理センター](https://admin.flow.microsoft.com) で、**環境** を選択します。

   ![環境のメニュー項目](./media/environments-overview-admin/select-environments.png)
1. 環境を選択してプロパティを開きます。
1. 環境の作成者、地理的な場所など、環境に関する追加情報を表示するには、**詳細** タブを使用します。

   ![詳細タブ](./media/environments-overview-admin/open-environment.png)
1. **セキュリティ**を選択します。

    前のステップで **データベースの作成** を選択しなかった場合、**環境ロール** には **環境管理者** と **環境作成者** の 2 つのオプションがあります:

    ![管理者ロール](./media/environments-overview-admin/environment-roles.png)

    **作成者** は、環境にフロー、データ接続、ゲートウェイなどの新しいリソースを作成できます。

   > [!NOTE]
   > ユーザーは環境内のリソースを *編集* するために **作成者** である必要はありません。 各作成者は、環境作成者ではないユーザーにアクセス許可を付与することにより、リソースを編集できるユーザーを決定します。
   > 
   > 

    **管理者** は、データ損失防止ポリシーを作成し、環境の作成、環境へのユーザーの追加、管理者/作成者の権限の割り当てなど、他の管理タスクを実行できます。

   1. **環境作成者** ロールを選択して、**ユーザー**: ![作成者ロール](./media/environments-overview-admin/add-environment-maker.png) を選択します
   1. **作成者** ロールを付与する名前、メール アドレス、またはユーザー グループを入力します。
   1. **保存**を選択します。

1. **セキュリティ** で **ユーザー ロール** を選択します:

    ![ユーザー ロール](./media/environments-overview-admin/security-user-roles.png)

    ロールを編集または削除するオプションを含め、既存のロールが一覧表示されます。

    **新しいロール** を選択して、新しいロールを作成します。
1. **セキュリティ** で **アクセス許可セット** を選択します:

    ![アクセス許可の設定](./media/environments-overview-admin/security-permission-set.png)

    ロールを編集または削除するための既存のアクセス許可セットとオプションがすべて表示されます。

    **新しいアクセス許可セット** を選択し、新しいアクセス許可セットを作成します。
1. データを保存するために **データベースの作成** を選択した場合、このデータベースは Common Data Service の一部になります。 **セキュリティ** タブをクリックすると、ロール ベースのセキュリティを適用できる **Dynamics 365 インスタンス管理センター** に移動するように求められます。
![Dynamics のセキュリティ設定](./media/environments-overview-admin/Security-Link-D365.png)

1. 環境 / インスタンス内のユーザーの一覧からユーザーを選択します。
  ![Dynamics のセキュリティ設定](./media/environments-overview-admin/D365-Select-User.png)

1. ロールをユーザーに割り当てます。

   ![ユーザーへのロールの割り当て](./media/environments-overview-admin/D365-Assign-Role.png)

> [!NOTE]
> これら環境ロールに割り当てられたユーザーまたはグループに、環境のデータベース (存在する場合) へのアクセス権が自動的に付与されることはなく、アクセス権はデータベース所有者により個別に付与される必要があります。 
>
>

### <a name="database-security"></a>データベース セキュリティ
データベース スキーマを作成および変更し、環境でプロビジョニングされたデータベース内に保存されているデータに接続する機能は、データベースのユーザー ロールとアクセス許可によってコントロールされます。 環境のデータベースのユーザー ロールとアクセス許可セットは、**セキュリティ** タブの **ユーザー ロール** および **アクセス許可セット** セクションから管理できます。 

   ![ユーザーへのロールの割り当て](./media/environments-overview-admin/D365-Assign-Role.png)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="can-i-move-a-flow-between-environments"></a>環境間でフローを移動できますか?

はい、ある環境からフローをエクスポートして、別の環境にインポートできます。

### <a name="which-license-includes-common-data-service"></a>Common Data Service はどのライセンスに含まれますか?

Common Data Service には、Power Automate [ライセンス](https://flow.microsoft.com/pricing) でアクセスできます。

請求に関するよく寄せられる質問への回答については、[請求に関する質問](billing-questions.md) ドキュメントを参照してください。

### <a name="can-common-data-service-be-used-outside-of-an-environment"></a>Common Data Service を環境外で使用できますか？

番号 Common Data Service には環境が必要となります。 その [詳細](common-data-model-intro.md) を参照してください。

### <a name="what-regions-include-power-automate"></a>Power Automate に含まれる地域はどこですか？

Power Automate は、 Office 365 でサポートされているほとんどのリージョンをサポートしています。詳しくは、[リージョンの概要](regions-overview.md) に関するページをご覧ください。

### <a name="whats-needed-to-create-my-own-custom-environment"></a>独自のカスタム環境を作成するには何が必要ですか?

Power Automate プラン 2 のライセンスを持つすべてのユーザーは、独自の環境を作成できます。 Power Automate のすべてのユーザーは、プラン 2 の管理者によって作成された環境を使用できますが、独自の環境を作成することはできません。
