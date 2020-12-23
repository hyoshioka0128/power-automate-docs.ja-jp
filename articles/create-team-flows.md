---
title: クラウド フローを他のユーザーと共有する方法 | Microsoft Docs
description: Power Automate を使用すると、反復的なタスクを簡単に自動化できます。 ユーザーまたはグループを所有者として追加し、共同作業によりフローを設計、管理できます。
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
ms.date: 08/25/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3629e57cd3156713376a700e71766248ba6a52a7
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709111"
---
# <a name="share-a-cloud-flow"></a>クラウド フローを共有する

クラウド フローを組織内の他の人と共有して、作成した自動化の益を得ることができるようにします。 Power Automate でクラウド フローを共有する主な方法は 3 つあります。

- クラウド フローに所有者を追加する。
- 実行専用の特権でクラウド フローを共有する。
- クラウド フローのコピーを共有する。

## <a name="prerequisites"></a>前提条件

- クラウド フローを共有するには、[Power Automate の有料ライセンス](https://flow.microsoft.com/pricing/) が必要です。
- クラウド フローの所有者を追加または削除するには、作成者または所有者である必要があります。

### <a name="about-embedded-and-other-connections"></a>埋め込み接続とその他の接続について

クラウド フローで使う接続は、2 つのカテゴリに分類されます。

- **埋め込み**: これらの接続はフローで使用されます。
- **その他**: これらの接続はクラウド フローに対して定義されていますが、使用されません。

クラウド フロー内で使われなくなった接続は **その他の接続** の一覧に表示され、所有者が接続を再びフローに含めるまでそのままになります。 埋め込み接続に変更を加える場合は、この記事で後述する [接続を更新する](#modify-a-connection) の手順に従います。<!--What is the significance of this? Embedded versus other?  DH: Its described in this section-->

次の図に示すように、接続の一覧は、クラウド フローのプロパティの所有者のリストの下に表示されます。

![埋め込み接続](./media/create-team-flows/embeddedconnections.png "埋め込み接続")

## <a name="add-an-owner-to-a-cloud-flow"></a>クラウド フローに所有者を追加する

所有者をクラウド フローに追加することは、クラウド フローを共有するための最も一般的な方法です。 クラウド フローのすべての所有者は、次の操作を実行できます。

- 実行履歴を表示します。
- フローのプロパティを管理する (たとえば、フローの開始または停止、所有者の追加、接続に使用する資格情報の更新)。
- フローの定義を編集する (たとえば、アクションまたは条件の追加や削除)。
- 他の所有者を追加または削除します (ただし、フローの作成者ではありません)。
- フローを削除します。

クラウド フローの作成者または所有者は、Power Automate の **チーム フロー** タブでそのリストを見つけることができます。

![チーム フローのタブ](./media/create-team-flows/addowner5.png "チーム フローのタブ")

>[!NOTE]
>共有された接続は、それらが作成されたフローの中で *のみ* 使うことができます。

所有者は、クラウド フローのサービスを使うことはできますが、別の所有者が作成した接続の資格情報を変更することはできません。<!--I'm confused by this. In line 42, you say that "any owner of a cloud flow can...update credentials for a connection." It seems that there's a difference between being added as an owner of a cloud flow and owning a connection within a cloud flow - will this be obvious to the reader? -->

<!--markdownlint-disable MD036-->
**クラウド フローにさらに所有者を追加するには**

1. [Power Automate](https://flow.microsoft.com) にサインインして **マイ フロー** を選択します。
1. 共有するフローを選択し、**その他のコマンド** ![その他のコマンド](./media/create-team-flows/more-commands.png) を選択してから **共有** を選択します。
  
    ![[その他のコマンド] から [共有] を選択する](./media/create-team-flows/addowner1.png "[その他のコマンド] から [共有] を選択する")

1. 所有者として追加する個人またはグループの名前、メール アドレス、グループ名を入力してください。

    ![ユーザーまたはグループを検索する](./media/create-team-flows/addowner2.png "ユーザーまたはグループを検索する")

    選択したユーザーまたはグループが、フローの所有者になります。

    ![新しい所有者](./media/create-team-flows/addowner4.png "新しい所有者")

おめでとうございます&mdash;チーム フローが作成されました!

## <a name="add-a-list-as-a-co-owner"></a>共同所有者として一覧を追加する

SharePoint の一覧をクラウド フローの共有者として追加すると、リストに対する編集アクセス権を持つすべてのユーザーが自動的にそのフローに対する編集アクセス権を取得できます。 フローを共有した後で、フローへのリンクを簡単に配布できます。 詳細情報: [トレーニング: SharePoint リストの作成と設定](https://support.microsoft.com/office/training-create-and-set-up-a-list-1ddc1f5a-a908-478b-bb6d-608f34b71f94)

> [!TIP]
> フローが SharePoint に接続される場合は一覧を使用し、それ以外すべての場合はグループを使用します。

>[!IMPORTANT]
>SharePoint でフローを実行する場合、SharePoint ユーザーは **編集** 権限を持っているか、**メンバー** や **所有者** グループのメンバーである必要があります。

## <a name="remove-an-owner"></a>所有者の削除

> [!IMPORTANT]
> Power Automate サービスの利用に資格情報を使用している所有者を削除する場合は、フローを引き続き正しく実行するために、それらの接続の資格情報を更新する必要があります。 詳細情報: [接続を変更する](#modify-a-connection)

1. フローの詳細ページの **所有者** セクションで、**編集** を選択します。

   ![所有者を編集する](./media/create-team-flows/editowners.png "所有者を編集する")

1. 削除する所有者に対応する **削除** ![削除ボタン](./media/create-team-flows/delete.png) を選択します。

    ![所有者の削除](./media/create-team-flows/removeowner2.png "所有者の削除")

1. 確認ダイアログ ボックスで **削除** を選択します。

これで削除したユーザーやグループがフローの所有者として一覧に表示しなくなります。

## <a name="modify-a-connection"></a>接続を変更する

既存の所有者を削除する場合や、アクションまたはトリガーにサインインするために別のアカウントを使用する場合は、クラウド フローで接続の所有者を変更する必要があります。

1. 変更するフローへの移動します。

1. **編集** を選択します。

   ![クラウド フローの編集](./media/create-team-flows/Edit-flow-details.png "クラウド フローの編集")

1. 接続を編集するステップで **その他のコマンド** (...) を選択します。

1. 接続済みの場合は、それを選択します。そうでない場合は **新しい接続を追加する** を選択して新しい接続を作成し、**サインイン** を選択して新しい接続を作成します。

   ![新しい接続を追加する](./media/create-team-flows/edit-connection.png "新しい接続を追加する")

## <a name="share-a-cloud-flow-with-run-only-permissions"></a>実行専用のアクセス許可でクラウド フローを共有する

(ボタンや選択したアイテムなどの手動トリガーを使用するフローである) インスタント フローは、実行専用のアクセス許可を使用して共有できます。 実行専用ユーザーとして追加されたユーザーは、フローを編集や変更するアクセス許可を持たず、フローをトリガーする権限のみを持ちます。

**実行専用ユーザーを追加する**

1. フローの詳細ページの **実行専用ユーザー** セクションで、**編集** を選択します。 

   ![実行専用ユーザー セクションを編集する](./media/create-team-flows/run-only-share.png "実行専用ユーザー セクションを編集する")

1. **実行専用アクセス許可を管理する** パネルで、実行専用アクセスを提供するユーザーとグループを指定します。

   ![実行専用ユーザーの追加](./media/create-team-flows/run-only-share2.png "実行専用ユーザーの追加")

1. 所有者は、実行専用ユーザーが独自の接続を提供する必要があるかを指定するか、またはフローで定義済みの接続を使用するかを選択できます。

   ![接続の管理](./media/create-team-flows/manage-run-only-connections.png "接続の管理")

これでユーザーやグループがフローを実行するアクセス許可を持ちます。

**実行専用ユーザーを削除する**

1. フローの詳細ページの **実行専用ユーザー** セクションで、**編集** を選択します。 
1. **実行専用アクセス許可を管理する** パネルで、アクセス許可を削除するユーザーの横にある **削除** ![削除ボタン](./media/create-team-flows/delete.png) を選択し、次に **保存** を選択します。

    ![実行専用ユーザーを削除する](./media/create-team-flows/remove-run-only-user.png "実行専用ユーザーを削除する")

これでユーザーやグループは、このフローを実行するアクセス許可を失います。

## <a name="share-a-copy-of-a-cloud-flow"></a>クラウド フローのコピーを共有する

クラウド フローのコピーを別のユーザと共有し、そのユーザがフローの定義をテンプレートとして使用できます。 これは、接続を共有せずにクラウド フローの一般的な構造を共有するための優れた方法を提供すると同時に、受信者が自分のニーズに合うように自分のフローを独自に変更できるようにします。

> [!NOTE]
> コピーを共有すると、受信者用に独立したフローのインスタンスが作成されます。 フローを共有した後は、フローのアクセス許可を取り消せません。

**クラウド フローのコピーを送信するには**

1. フローの詳細ページのコマンド バーで **コピーを送る** を選択します。

   ![コマンド バーでコピーを送信する](./media/create-team-flows/send-a-copy.png "コマンド バーでコピーを送信する")

1. **コピーを送る** パネルで共有するフローの名前と説明を編集し、フローを共有するユーザーを指定します。

   ![コピーの詳細を送信する](./media/create-team-flows/send-a-copy3.png "コピーの詳細を送信する")

1. 受信者には、クラウド フロー テンプレートが共有されたことを示すメールが届きます。その後、受信者はそのフローの独自のインスタンスを作成できます。

   ![コピーを受信する](./media/create-team-flows/send-a-copy5.png "コピーを受信する")

   >[!NOTE]
   >受信者は左側のウィンドウから **テンプレート** を選択し、**自分と共有済み** タブを選択してフローにアクセスすることもできます。

   ![自分と共有](./media/create-team-flows/send-a-copy6.png "自分と共有")

## <a name="faq"></a>よくあるご質問

### <a name="what-happens-if-the-user-who-created-a-shared-flow-leaves-the-organization"></a>共有フローを作成したユーザーが組織を離れるとどうなりますか?

共有フローにアクティブな所有者がいる場合、フローは引き続き実行されます。 

>[!NOTE]
>フローが、組織を去ったユーザーに属するアクティブ接続または組み込み接続を使用する場合、これらの特定のアクションは失敗する可能性があります。 これを修正する場合は、この記事の前半にある [接続を変更する](#modify-a-connection) の手順に従い資格情報を更新します。
<!--markdownlint-enable MD036-->
