---
title: フローに他の所有者を追加し、チーム フローを作成する | Microsoft Docs
description: Power Automate を使用すると、反復的なタスクを簡単に自動化できます。 ユーザーまたはグループを所有者として追加し、共同作業によりフローを設計、管理できます。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/05/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7ddcc0303fb2a1a8d3c5a89adb7a7b8d77c3d08b
ms.sourcegitcommit: a1d509e61196054c8272ed96aed9477485d3c71e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "3542749"
---
# <a name="share-a-flow"></a>フローを共有する 

組織内の他の人を所有者として加えることで、フローを共有します。 チーム フローのすべての所有者は、以下のアクションを実行することができます :

* フローの履歴 (それぞれの実行履歴) を表示する。
* フローのプロパティを管理する (たとえば、フローの開始または停止、所有者の追加、接続に使用する資格情報の更新)。
* フローの定義を編集する (たとえば、アクションまたは条件の追加や削除)。
* 他の所有者を追加および削除する (フローの作成者以外)。
* フローを削除します。

チーム フローの作成者または所有者は、[Power Automate](https://flow.microsoft.com) の**チーム フロー** タブでそのリストを見つけることができます。

![チーム フローのタブ](./media/create-team-flows/addowner5.png)

> [!NOTE]
> 共有された接続は、それらが作成されたフローの中で**のみ**使うことができます。
> 
> 

所有者は、フロー内のサービスを使うことはできますが、別の所有者が作成した接続の資格情報を変更することはできません。

## <a name="prerequisites"></a>前提条件
チーム フローを作成するには、[有料の Power Automate プラン](https://flow.microsoft.com/pricing/) が必要です。 また、チーム フローの所有者を追加/削除するには、作成者、あるいは所有者である必要があります。

## <a name="share-a-flow"></a>フローを共有する
チーム フローを作成するには、またはチーム フローに所有者を追加するには、次のステップに従ってください。

1. [Power Automate](https://flow.microsoft.com) にサインインし、**自分のフロー** を選びます。
2. 共有するフローに対して、**...** (その他のコマンド) を選択し、**共有** を選択します。
   
    ![チームのアイコン](./media/create-team-flows/addowner1.png)
3. 所有者として追加する個人またはグループの名前、メール アドレス、またはグループ名を入力してください。
   
    ![ユーザーの検索](./media/create-team-flows/addowner2.png)
4. 選択したユーザーまたはグループが、フローの所有者になります :
     
    ![新しい所有者](./media/create-team-flows/addowner4.png)
   
     以上で&mdash;チーム フローが作成されました。

## <a name="add-a-list-as-a-co-owner"></a>共同所有者として一覧を追加する

SharePoint のリストを共有者としてフローに追加することで、リストへの編集アクセス権を持っている全員が自動的にフローへの編集アクセス権を得ることができます。 フローが共有されると、フローへのリンクを簡単に配布することができます。

> [!TIP]
> フローが SharePoint に接続される場合はリストを使用し、それ以外の場合はグループを使用してください。
>

## <a name="remove-an-owner"></a>所有者の削除

> [!IMPORTANT]
> Power Automate サービスにアクセスするために使用される資格情報を持つ所有者を削除する場合は、フローが正常に実行され続けるように、それらの接続の資格情報を更新する必要があります。
> 
> 

1. 共有するフローに対して、**...** (その他のコマンド) を選択し、**共有** を選択します。
   
    ![ユーザー選択のアイコン](./media/create-team-flows/addowner1.png)
2. 削除する所有者の **削除** アイコンを選びます :
   
    ![削除の選択](./media/create-team-flows/removeowner2.png)
3. 確認ダイアログ ボックスで、**この所有者を削除する** を選びます :
   
    ![削除の確認](./media/create-team-flows/removeowner3.png)
4. 以上で&mdash; 削除したユーザーまたはグループはフローの所有者として一覧に表示されなくなります。


## <a name="update-connection-owner"></a>接続の所有者を更新する

既存の所有者を削除した場合は、フロー内で使用している接続の所有者を変更が必要となる場合があります。 次のステップに従って、フローの所有者を切り替えてください :

1. 左側パネルから **データ** を選択します。
1. **接続**を選択します。
1. 更新する接続を検索し、選択します。
1. 選択した接続で **...** (その他のコマンド) を選択し、**アカウントの切り替え** を選択します。
1. 接続に使用する異なるアカウントを使用するステップに従います。

## <a name="embedded-and-other-connections"></a>埋め込み接続とその他の接続

フローで使う接続は、次の 2 つのカテゴリに分類されます :

* **埋め込み** &mdash; これらの接続はフローで使用されます。
* **その他** &mdash; これらの接続はフローに対して定義されていますが、フロー内では使用されていません。

フロー内で使われなくなった接続は **その他** の接続一覧に表示され、所有者が接続を再びフロー内に含めるまではそのままになります。

[接続の所有者を更新する](./create-team-flows.md#update-connection-owner) のステップに従って、埋め込み接続を変更します。

接続の一覧は、フローのプロパティで所有者の一覧の下に表示されます :

![埋め込み接続](./media/create-team-flows/embeddedconnections.png)

