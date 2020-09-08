---
title: フローを他のユーザーと共有する方法についての説明 | Microsoft Docs
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
ms.date: 08/05/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5b4d97d47b7cd11c4dc42bcdb8b3861ee3c49398
ms.sourcegitcommit: 5c82214daf6aa602732b381c5f411c6a97ac52e9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "3705941"
---
# <a name="share-a-flow"></a>フローを共有する 

組織内の他のユーザーとフローを共有して、作成した自動化の恩恵を受けることができるようにします。 Power Automate でフローを共有する主な方法は 3 つあります:

1. フローに所有者を追加します。
2. 実行のみの権限でフローを共有します。
3. フローのコピーを共有します。

## <a name="prerequisites"></a>前提条件

- フローを共有するには [Power Automate の有料ライセンス](https://flow.microsoft.com/pricing/) が必要です。 
- フローの所有者を追加/削除するには、作成者または所有者である必要があります。

## <a name="add-an-owner-to-a-flow"></a>フローへの所有者の追加

フローへの所有者の追加は、フローを共有する最も一般的な方法です。 フローの所有者は、次の操作を実行できます:

* 実行履歴を表示します。
* フローのプロパティを管理する (たとえば、フローの開始または停止、所有者の追加、接続に使用する資格情報の更新)。
* フローの定義を編集する (たとえば、アクションまたは条件の追加や削除)。
* 他の所有者を追加または削除します (ただし、フローの作成者ではありません)。
* フローを削除します。

フローの作成者または所有者は、[Power Automate](https://flow.microsoft.com) の **チームのフロー** タブにリストされています。

![チーム フローのタブ](./media/create-team-flows/addowner5.png)

>[!NOTE]
>共有された接続は、それらが作成されたフローの中で**のみ**使うことができます。

所有者は、フロー内のサービスを使うことはできますが、別の所有者が作成した接続の資格情報を変更することはできません。


### <a name="steps-to-add-an-owner-to-a-flow"></a>フローに所有者を追加する手順

フローに所有者を追加する手順は、次のとおりです。

1. [Power Automate](https://flow.microsoft.com) にサインインし、**自分のフロー** を選びます。
1. **...** (その他のコマンド) を選択し、共有するフローに対して **共有** を選択します。
   
    ![チームのアイコン](./media/create-team-flows/addowner1.png)

   >[!NOTE]
   >フローの詳細ページの共有オプションを使用してフローを共有することもできます。 

1. 所有者として追加する個人またはグループの名前、メール アドレス、またはグループ名を入力してください。
   
    ![ユーザーの検索](./media/create-team-flows/addowner2.png)
1. 選択したユーザーまたはグループが、フローの所有者になります :
     
    ![新しい所有者](./media/create-team-flows/addowner4.png)
   
     おめでとうございます&mdash;チーム フローが作成されました!

## <a name="remove-an-owner"></a>所有者の削除

> [!IMPORTANT]
> Power Automate サービスにアクセスするために使用される資格情報を持つ所有者を削除する場合は、フローが正常に実行され続けるように、それらの接続の資格情報を更新する必要があります。

1. フローの詳細ページで、所有者セクションの ![所有者の編集](./media/create-team-flows/editowners.png) で編集リンクを選択します

   >[!NOTE]
   >前述のフローの詳細ページにある [共有] ボタンを使用して、フローの所有者を編集することもできます

1. 削除する所有者の **削除** アイコンを選びます :
   
    ![削除の選択](./media/create-team-flows/removeowner2.png)
1. 確認ダイアログ ボックスで、**この所有者を削除する** を選びます :
   
    ![削除の確認](./media/create-team-flows/removeowner3.png)
1. 以上で&mdash; 削除したユーザーまたはグループはフローの所有者として一覧に表示されなくなります。


### <a name="update-connections"></a>接続の更新

既存の所有者を削除したり、別のアカウントを使用してアクション/トリガーにサインインしたりする場合は、フローの接続の所有者を変更する必要がある場合があります。 共有フローのトリガーまたはアクションの接続を編集する手順は、次のとおりです:

1. 変更するフローへの移動
2. [編集] をクリックして、フローを編集します ![フローの編集](./media/create-team-flows/Edit-flow-details.png)
3. 編集するトリガーまたはアクションの接続を編集する手順のオーバーフロー メニューをクリックします
4. 接続がすでにある場合は、それを選択するだけですが、そうでない場合は、"新しい接続の追加" をクリックして新しい接続を作成します ![新しい接続の追加](./media/create-team-flows/edit-connection.png)
5. サインインをクリックして新しい接続を作成し、準備が完了しました!
![サインイン](./media/create-team-flows/sign-in.png)

### <a name="embedded-and-other-connections"></a>埋め込み接続とその他の接続

フローで使う接続は、次の 2 つのカテゴリに分類されます :

* **埋め込み** &mdash; これらの接続はフローで使用されます。
* **その他** &mdash; これらの接続はフローに対して定義されていますが、フロー内では使用されていません。

フロー内で使われなくなった接続は **その他** の接続一覧に表示され、所有者が接続を再びフロー内に含めるまではそのままになります。

[接続を更新する](./create-team-flows.md#update-connections) 手順に従って、埋め込み接続を変更します。

接続の一覧は、フローのプロパティで所有者の一覧の下に表示されます :

![埋め込み接続](./media/create-team-flows/embeddedconnections.png)

## <a name="add-a-list-as-a-co-owner"></a>共同所有者として一覧を追加する

SharePoint のリストを共有者としてフローに追加することで、リストへの編集アクセス権を持っている全員が自動的にフローへの編集アクセス権を得ることができます。 フローが共有されると、フローへのリンクを簡単に配布することができます。

> [!TIP]
> フローが SharePoint に接続される場合はリストを使用し、それ以外の場合はグループを使用してください。
>

## <a name="share-a-flow-with-run-only-permissions"></a>実行のみのアクセス許可でフローを共有する

インスタント フロー (ボタン、選択したアイテムなどの手動トリガーを使用するフロー) は、実行のみのアクセス許可を使用して共有できます。 実行のみのユーザーとして追加されたユーザーには、フローを編集または変更するためのアクセス権はありません。 フローをトリガーするアクセス許可しかありません。 

### <a name="add-a-run-only-user"></a>実行のみのユーザーを追加する

1. フローの詳細ページで、[実行のみのユーザー] セクションの横にある "編集" リンクを選択します。 
![実行のみの共有](./media/create-team-flows/run-only-share.png)
2. [実行のみのアクセス許可を管理] ポップアップで、実行のみのアクセス許可を付与するユーザー、グループを指定します ![実行のみのユーザーを追加](./media/create-team-flows/run-only-share2.png)
3. 所有者として、実行のみのユーザーがフローを共有するときに独自の接続を用意する必要があるか、フローで既に定義されている接続を使用する必要があるかを選択できます ![接続の管理](./media/create-team-flows/manage-run-only-connections.png)
4. おめでとうございます &mdash; ユーザーまたはグループにフローを実行するためのアクセス権が付与されます。

### <a name="remove-a-run-only-user"></a>実行のみのユーザーを削除する

1. フローの詳細ページで、[実行のみのユーザー] セクションの横にある "編集" リンクを選択します。 
![実行のみの共有](./media/create-team-flows/run-only-share.png)
2. [実行のみのアクセス許可の管理] ポップアップで、実行のみのアクセス許可を削除するユーザーの横にある削除アイコンをクリックし、ページの下部にある保存をクリックします ![実行のみのユーザーの削除](./media/create-team-flows/remove-run-only-user.png)
3. おめでとうございます &mdash; ユーザーまたはグループはこのフローを実行するためのアクセス権を失います。

## <a name="share-a-copy-of-a-flow"></a>フローのコピーを共有する

コピーを共有すると、フローの定義を別のユーザーとテンプレートとして共有できます。 これは、接続を共有せずにフローの一般的な構造を共有するための優れた方法を提供とする同時に、受信者がフローに関係なくフローを変更できるため、ニーズに合わせることができます。

> [!NOTE]
> コピーを共有すると、受信者のフローの独立したインスタンスが作成されます。 共有されたフローへのアクセスを取り消す方法はありません。

### <a name="send-a-copy-of-a-flow"></a>フローのコピーを送信する

1. フローの詳細ページで、上部のコマンドバーの "コピーを送信" オプションを選択します![コピーを送信](./media/create-team-flows/send-a-copy.png)

   >[!NOTE]
   >フロー オーバーフロー メニューから [コピーを送信] を選択することもできます

   ![別のコピーを送信する](./media/create-team-flows/send-a-copy2.png)

1. ポップアップ メニューで、共有するフローの名前と説明を編集し、フローを共有するユーザーを指定できます。
![コピーの詳細を送信](./media/create-team-flows/send-a-copy3.png)
1. 受信者は、フロー テンプレートをあなたと共有し、そのフローの独自のインスタンスを作成することを許可することを示すメールを受信します

   ![コピーを受信する](./media/create-team-flows/send-a-copy5.png)
   
   >[!NOTE]
   >受信者は、テンプレートの下の [共有アイテム] セクションからフローにアクセスすることもできます

   ![共有アイテム](./media/create-team-flows/send-a-copy6.png)

## <a name="faq"></a>よくあるご質問

### <a name="what-happens-if-the-user-who-created-a-shared-flow-leaves-the-organization"></a>共有フローを作成したユーザーが組織を離れるとどうなりますか?
共有フローにアクティブな所有者がいる限り、フローは引き続き実行されます。 

>[!NOTE]
>フローが、組織を去ったユーザーに属するアクティブ接続または組み込み接続を使用する場合、これらの特定のアクションは失敗する可能性があります。 これを修正するには、[接続を更新する](./create-team-flows.md#update-connections) セクションに記載されている手順に従って、トリガーまたはアクションの接続を変更します。

