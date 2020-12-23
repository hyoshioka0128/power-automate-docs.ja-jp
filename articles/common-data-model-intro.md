---
title: Microsoft Dataverse | Microsoft Docs
description: Microsoft Dataverse を使用するテンプレートからクラウド フローを作成します。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/17/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f50ed06682bf934763eed1b3d9ab1ba0ccbc5ea1
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4708439"
---
# <a name="create-a-cloud-flow-that-uses-microsoft-dataverse"></a>Microsoft Dataverse を使用するクラウド フローを作成する

[!INCLUDE[cc-data-platform-banner](./includes/cc-data-platform-banner.md)]

[Dataverse](https://powerapps.microsoft.com/tutorials/data-platform-intro/) を使用するフローを作成することにより、ビジネス データの統合ビューで運用効率を向上させます。 


たとえば、Power Automate 内では、主に以下の方法で Dataverse を使用できます。

* データのインポート、データのエクスポート、データ変更時のアクションの実行 (通知の送信など) を行うクラウド フローを作成します。 詳細な手順については、このトピックの後半にある手順を参照してください。
* [電子メールを介した承認ループを作成する](wait-for-approvals.md)代わりに、承認状態をエンティティに格納するクラウド フローを作成し、ユーザーが項目を承認または却下できるカスタム アプリをビルドします。 詳細な手順については、[Dataverse を使用した承認ループの作成](common-data-model-approve.md) を参照してください。

この記事では、*適格な潜在顧客に関するプロセス* が Dataverse で新しい *営業案件* を作成したときに電子メール通知を送信するクラウド フローを作成します。 通知には *潜在顧客* からの *メモ* が含まれています。

## <a name="prerequisites"></a>前提条件

* [Power Automate](https://flow.microsoft.com) と [Power Apps](https://make.powerapps.com) に登録します。
  
    問題が発生した場合は、所有するアカウントの種類が [Power Automate](sign-up-sign-in.md)  と [Power Apps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) で対応しているかどうか、および組織が登録をブロックしていないことを確認してください。
* 今まで Dataverse を使用したことがない場合は、Power Platform 管理センターのデータベースを使って [Dataverse 環境を作成](https://docs.microsoft.com/power-platform/admin/create-environment#create-an-environment-with-a-database)します。

## <a name="sign-in-to-your-environment"></a>環境にサインイン

1. [Power Automate](https://flow.microsoft.com) を参照し、右上隅の **サインイン** を選択します。
   
    ![サインイン](./media/common-data-model-intro/signin-flow.png)
1. 右上のメニューで、powerapps.com でデータベースを作成した環境を選択します。
   
    >[!IMPORTANT]
    >同じ環境を選択しないと、エンティティが表示されません。
   
    ![環境の選択](./media/common-data-model-intro/select-environment.png)

## <a name="use-a-template"></a>テンプレートの使用

1. 画面上部にある **アプリ、タスク、または業界のテンプレートを検索する** ボックスに、**一般** と入力し、**Enter** キーを押します。

   Common Data Model を使用するテンプレートを含め、名前に「一般」という単語が含まれるテンプレートのリストが表示されます。
   
    ![テンプレートの検索](./media/common-data-model-intro/template-search.png)

1. テンプレートのリストで、実行するタスクを実行するテンプレートを選択します。
   
    たとえば、次の手順に示すように、Dataverse で潜在顧客から営業案件にメモをコピーするテンプレートを選択します。
   
    ![テンプレートを選択する](./media/common-data-model-intro/select-template.png)
   
1. 接続をまだ作成していない場合は、**サインイン** を選択し、必要に応じて資格情報を入力します。
   
1. **続行** を選択します。

   テンプレートとその接続が表示されます。 次の手順では、このテンプレートをカスタマイズします。

## <a name="customize-your-flow-template"></a>フロー テンプレートのカスタマイズ

1. **営業案件が作成されたとき** カードで、使用する **環境**、**エンティティ名**、**範囲** を選択します。
   
    ![エンティティの詳細を指定する](./media/common-data-model-intro/specify-instance.png)

1. 要件に応じて、**営業案件レコードの取得** カードに入力します。
   
    ![営業案件レコードの取得](./media/common-data-model-intro/get-opportunity-record.png)

1. **潜在顧客から** カードを構成します。 
   
    ![潜在顧客から](./media/common-data-model-intro/originate-from-lead.png)

1. 決定分岐の **該当する場合** 側にある **リードの取得** と **リードのメモのリスト** のカードを完成させてください。 

   ![完全な決定分ブランチ](./media/common-data-model-intro/get-lead-list-notes.png)

1. **Apply to each** カードを展開し、**潜在顧客メモを新しいメモにコピー** カードを削除します。

1. **アクションを追加** を選択して **通知** を検索し、**メール通知を受け取る** を選択します。

   ![電子メール通知](./media/common-data-model-intro/apply-to-each.png)

1. 潜在顧客のメモの詳細が記載された電子メール通知を送信するように通知カードを構成します。

   ![通知カード](./media/common-data-model-intro/notification-card.png)


>[!TIP]
>必要なテンプレートが見つからない場合は、Dataverse 上で動作する[クラウド フローをゼロから構築する](get-started-logic-flow.md) ことができます。

