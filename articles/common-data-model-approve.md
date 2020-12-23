---
title: Microsoft Dataverse で承認ループを構築する | Microsoft Docs
description: Dropbox に追加されたファイルをレビュー担当者が承認または却下できるように連携するエンティティ、クラウド フロー、アプリを作成します。
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
ms.date: 04/07/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: efb1cc378bd8a6045a8a1453fd07cba03952cf11
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4708871"
---
# <a name="build-an-approval-loop-by-using-power-automate-and-common-data-service"></a>Power Automate と Common Data Service を使用して承認ループを構築する

[!INCLUDE[cc-data-platform-banner](./includes/cc-data-platform-banner.md)]

Dataverse を使用すると、クラウド フローから独立してデータベースに情報が格納されているフローを構築することができます。 この最も良い例が承認です。 承認の状態をエンティティに格納すると、フローはそれを元にして動作できます。

この例では、ユーザーが Dropbox にファイルを追加したときに開始される承認プロセスを作成します。 ファイルが追加されると関連する情報がアプリに表示され、その変更をレビュー担当者が承認または拒否できます。 レビュー担当者が変更を承認または却下すると通知メールを送信し、却下されたファイルは Dropbox から削除されます。

このセクションの手順に従い、以下を構築します。

* Dropbox に追加された各ファイルに関する情報と、そのファイルの状態 (承認、拒否、保留中) を含む **カスタム エンティティ**。
* ファイルが Dropbox に追加されるとカスタム エンティティに情報を追加し、ファイルが承認や拒否された際にメールを送信し、拒否されたファイルを削除する **フロー**。 これらの手順は、このようなクラウド フローを一から作成する方法を示していますが、同様のフローをテンプレートから作成することもできます。
* レビュー担当者が Dropbox に追加されたファイルを承認や拒否できる **アプリ**。 Power Apps を使用すると、カスタム エンティティのフィールドに基づいて自動的にこのアプリが生成されます。

**前提条件**

* [Power Automate](sign-up-sign-in.md) と [Power Apps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) に登録します。
* [接続を管理する](https://powerapps.microsoft.com/tutorials/add-manage-connections/) に記載の説明に従って Dropbox および Office 365 Outlook への接続を作成します。

## <a name="build-the-entity"></a>エンティティを構築する
1. [powerapps.com](https://make.powerapps.com) へのサインイン。
2. 既定で左側のナビゲーション バーが表示されない場合は、左上隅にある 3 本の横線のアイコンをクリックまたはタップします。
   
    ![左側のナビゲーション バーを開く](./media/common-data-model-approve/hamburger-icon.png)
3. 左側のナビゲーション バーで、**管理**、**エンティティ** の順にクリックまたはタップします。
   
    ![エンティティの管理](./media/common-data-model-approve/manage-entities.png)
4. プロンプトが表示されたら **自分のデータベースを作成する** をクリックまたはタップします。
   
    ![データベースの作成](./media/common-data-model-approve/create-database.png)
5. 画面右上隅付近から **新しいエンティティ** をクリックまたはタップします。
   
    ![エンティティを作成する](./media/common-data-model-approve/new-entity.png)
   
    ブラウザー ウィンドウが最大化されていない場合は、このボタンが別の場所に表示されることがあります。
6. **エンティティ名** に、スペースを含まずデータベース内の他のエンティティと重複しない名前を指定します。
   
    この例に正確に従う場合は **ReviewDropboxFiles** を指定します。
   
    ![エンティティ名を指定する](./media/common-data-model-approve/entity-name.png)
7. **表示名** にフレンドリ名を指定します。
   
    ![表示名を指定する](./media/common-data-model-approve/display-name.png)
8. **次へ** をクリックまたはタップします。
   
    ![[次へ] ボタン](./media/common-data-model-approve/next-button.png)

## <a name="add-fields-to-the-entity"></a>エンティティにフィールドを追加する
1. 画面右上隅付近で **フィールドの追加** をクリックまたはタップします。
   
    ![フィールドの追加](./media/common-data-model-approve/add-field.png)
2. フィールド一覧の下部に表示される空白行に **承認者** フィールドのプロパティを設定します。 (これらのプロパティを設定すると Tab キーの押下で次の列に移動できます。)
   
   * **表示名** 列に **承認者** と入力します。
   * **名前** 列に **ApproverEmail** と入力します。
   * **種類** 列で **電子メール** オプションをクリックまたはタップします。
   * **必須** 列のチェック ボックスを選択します。
     
     ![承認者フィールド](./media/common-data-model-approve/approver-field.png)
3. 次の行で **状態** フィールドのプロパティを設定します:
   
   * **表示名** 列に **状態** と入力します。
   * **名前** 列に **状態** と入力します。
   * **種類** 列で **テキスト** オプションをクリックまたはタップします。
   * **プロパティ** 列は既定値のままにします。
   * **必須** 列のチェック ボックスを選択します。
     
     ![状態フィールド](./media/common-data-model-approve/status-field.png)
4. 次の行で **FileID** フィールドのプロパティを設定します:
   
   * **表示名** 列に **ファイル識別子** と入力します。
   * **名前** 列に **FileID** と入力します。
   * **種類** 列で **テキスト** オプションをクリックまたはタップします。
   * **プロパティ** 列は既定値のままにします。
   * **一意** 列でチェックボックスを選択します。
   * **必須** 列のチェック ボックスを選択します。
     
     ![FileID フィールド](./media/common-data-model-approve/fileid-field.png)
5. 画面右端付近で **FileID** フィールドの省略記号 (...) をクリックまたはタップして、**タイトル フィールドに設定する** をクリックまたはタップします。
   
    ![タイトル フィールドを設定する](./media/common-data-model-approve/set-title-field.png)
6. 画面左下隅付近で **作成** をクリックまたはタップします。
   
    ![エンティティの作成](./media/common-data-model-approve/create-button.png)
7. (オプション) エンティティの一覧が再表示されたら、ブラウザー ウィンドウをまだ最大化していない場合は最大化し、**種類** 列ヘッダーをクリックまたはタップします。 リストはここで作成したようなカスタム エンティティでソートされ、上部に表示されます。

## <a name="sign-in-and-create-a-cloud-flow"></a>サインインしてクラウド フローを作成する
1. [Power Automate ポータル](https://flow.microsoft.com) を開きます。
2. ブラウザー ウィンドウをまだ最大化していない場合は最大化し、画面右上隅付近で **サインイン** をクリックまたはタップします。
   
    ![Power Automate のサイン イン ボタン](./media/common-data-model-approve/signin-flow.png)
3. 右上のメニューから、powerapps.com でデータベースを作成した環境を選択します。
   
    **メモ**: 同じ環境を選択しない場合はエンティティが表示されません。
4. 左上隅付近で **マイ フロー** をクリックまたはタップします。
   
    ![[マイ フロー] ボタン](./media/common-data-model-approve/myflows-button.png)
5. 右上隅付近で **新しいフローを作成する** をクリックまたはタップします。
   
    ![[新しいフローを作成する] ボタン](./media/common-data-model-approve/create-flow.png)

## <a name="start-when-a-file-is-added"></a>ファイルの追加時に開始します
1. **他のトリガーを検索する** を含むボックスで、**Dropbox** と入力または貼り付けてから **Dropbox - ファイルの作成時** をクリックまたはタップします。
   
    ![トリガーを作成する](./media/common-data-model-approve/create-trigger.png)
2. **フォルダー** からフォルダー アイコンをクリックまたはタップし、ファイルを追加するフォルダーを参照します。
   
    ![フォルダーを選択する](./media/common-data-model-approve/folder-icon.png)

## <a name="add-data-to-the-entity"></a>エンティティにデータを追加する
1. **新しいステップ** をクリックまたはタップし、**アクションの追加** をクリックまたはタップします。
   
    ![アクションを追加します](./media/common-data-model-approve/add-action.png)
2. **その他のアクションを検索する** と表示されているボックスで **Common Data Service** と入力し、**Common Data Service - オブジェクトを作成する** をクリックまたはタップします。
   
    ![Common Data Service でオブジェクトを作成する](./media/common-data-model-approve/cdm-create-object.png)
3. **エンティティ** に **レビュー** と入力または貼り付けてから **Dropbox ファイルをレビューする** をクリックまたはタップします。
   
    ![エンティティを選択する](./media/common-data-model-approve/choose-entity-flow.png)
4. **タイトル** 配下でボックス内をクリックまたはタップして、パラメーター トークンの一覧で **ファイル名** をクリックまたはタップし、そのトークンをフィールドに追加します。
   
    ![ファイル名トークンを追加する](./media/common-data-model-approve/add-filename-token.png)
5. **承認者** 配下に、ファイルのレビュー担当者のメール アドレスを入力または貼り付けます。
   
    **メモ**: フローのテストを簡単にするために自分のアドレスを指定します。 後でフローを実際に使用する準備ができた時に変更できます。
   
    ![承認者を追加する](./media/common-data-model-approve/add-approver.png)
6. **状態** に **保留中** と入力するか貼り付けます。
   
    ![既定状態を追加する](./media/common-data-model-approve/add-default-status.png)
7. **ファイル識別子** 配下でボックスをクリックまたはタップして、パラメーター トークンの一覧で **ファイル識別子** をクリックまたはタップし、そのトークンをフィールドに追加します。
   
    ![ファイル識別子トークンを追加する](./media/common-data-model-approve/add-file-identifier.png)

## <a name="check-whether-the-file-has-been-reviewed"></a>ファイルがレビューされたかどうかを確認する
1. **オブジェクトの作成** アクションで **新しいステップ** をクリックまたはタップし、**その他** をクリックまたはタップしてから **Do Until の追加** をクリックまたはタップします。
   
    ![Do Until を追加する](./media/common-data-model-approve/add-do-until.png)
2. **Do until** アクションの左上隅から **値の選択** と表示されたボックスをクリックまたはタップします。
   
    ![値の選択](./media/common-data-model-approve/choose-value.png)
   
    **メモ**: ブラウザー ウィンドウが最大化されていない場合は **値の選択** と表示された上部のボックスをクリックまたはタップします。
3. **オブジェクト作成の出力** 配下から **状態** をクリックまたはタップして、そのパラメーター トークンをフィールドに追加します。
   
    ![状態トークンを追加する](./media/common-data-model-approve/add-status.png)
4. **Do until** アクションの中央付近にあるリストを開き、**等しくない** をクリックまたはタップします。
   
    ![[等しくない] を指定する](./media/common-data-model-approve/is-not-equal.png)
5. **Do until** アクションの右上隅で **値の選択** と表示されたボックスに **保留中** を入力または貼り付けます。
   
    ![監視する状態を指定する](./media/common-data-model-approve/do-until-not-pending.png)
   
    **メモ**: ブラウザー ウィンドウが最大化されていない場合は **値の選択** と表示された下部のボックスをクリックまたはタップします。
6. **Do until** アクションの下部から **アクションの追加** をクリックまたはタップします。
   
    ![Do until にアクションを追加する](./media/common-data-model-approve/add-action-in-dountil.png)
7. **その他のアクションを検索する** と表示されているボックスで **Common** と入力し、**Common Data Service - オブジェクトを取得する** をクリックまたはタップします。
   
    ![オブジェクトを取得する](./media/common-data-model-approve/get-object.png)
8. **名前空間** 配下のデータベースをクリックまたはタップします。
9. **エンティティ** に **レビュー** と入力または貼り付けてから **Dropbox ファイルをレビューする** をクリックまたはタップします。
   
    ![エンティティの選択](./media/common-data-model-approve/choose-entity-flow.png)
10. **オブジェクト ID** 配下のボックスをクリックまたはタップし、**ファイル識別子** パラメーター トークンをクリックまたはタップしてフィールドに追加します。
    
     ![オブジェクト識別子を追加する](./media/common-data-model-approve/add-object-id.png)

## <a name="check-whether-the-item-has-been-approved"></a>項目が承認されたかどうかを確認する
1. **Do Until** アクションから **新しいステップ**、**条件の追加** を順にクリックまたはタップします。
   
    ![条件の追加](./media/common-data-model-approve/add-condition.png)
2. 条件の左上隅で **値の選択** と表示されたボックスをクリックまたはタップします。
   
    ![条件の左上隅](./media/common-data-model-approve/condition-upper-left.png)
   
    **メモ**: ブラウザー ウィンドウが最大化されていない場合は **値の選択** と表示された上部のボックスをクリックまたはタップします。
3. **オブジェクト取得の出力** 配下で **状態** パラメーター トークンをクリックまたはタップしてフィールドに追加します。
   
    ![条件に状態を追加する](./media/common-data-model-approve/add-status-to-condition.png)
4. 条件の右上隅で **値の選択** と表示されたボックスに **承認済** と入力または貼り付けます。
   
    ![状態が承認済みに設定されたかどうかを確認する](./media/common-data-model-approve/status-equals-approved.png)
   
    **メモ**: ブラウザー ウィンドウを最大化していない場合は、**値の選択** と表示された下のボックスに **承認済** と入力または貼り付けます。

## <a name="send-notification-mail"></a>通知メールを送信する
1. **はいの場合は何もしない** 配下で **アクションの追加** をクリックまたはタップします。
   
    ![[はい] の場合、アクションを追加する](./media/common-data-model-approve/if-yes-action.png)
2. **その他のアクションを検索する** と表示されているボックスで、**メールの送信** と入力し、 **Office 365 Outlook - メールの送信** をクリックまたはタップします。
   
    ![[はい] の場合、メールを送信する](./media/common-data-model-approve/if-yes-send-mail.png)
3. **宛先** 配下に、項目が承認された際に通知するユーザーのメール アドレスを入力または貼り付けます。
   
    **メモ**: フローのテストを簡単にするために自分のアドレスを指定します。 フローを実際に使用する準備ができた時に変更できます。
   
    ![承認の受信者](./media/common-data-model-approve/approval-recipient.png)
4. **件名** 配下のボックスをクリックまたはタップしてから、**ファイル名** パラメーター トークンをクリックまたはタップしてフィールドに追加します。
   
    ![電子メールの件名にファイル名を指定する](./media/common-data-model-approve/subject-is-file-name.png)
5. **本文** に **項目が承認されました** と入力または貼り付けます。
   
    ![承認メールの本文](./media/common-data-model-approve/approval-body.png)
6. **いいえの場合は何もしない** で、電子メール メッセージの本文に **項目が拒否されました** を指定することを除き、この手順の 1〜5 を繰り返します。
   
    ![拒否メールの本文](./media/common-data-model-approve/rejection-body.png)

## <a name="delete-rejected-files"></a>拒否されたファイルを削除する
1. 拒否メールのフィールドで **アクションの追加** をクリックまたはタップします。
   
    ![削除アクションを追加する](./media/common-data-model-approve/add-delete-action.png)
2. **他のアクションを検索する** と表示されたボックスに **Dropbox** と入力または貼り付けてから、**Dropbox - ファイルの削除** をクリックまたはタップします。
   
    ![Dropbox からファイルを削除する](./media/common-data-model-approve/dropbox-delete-file.png)
3. **ファイル** 配下でボックスをクリックまたはタップしてから、**ファイル識別子** トークン パラメーターをクリックまたはタップしてフィールドに追加します。
   
    ![削除するファイルを特定する](./media/common-data-model-approve/identify-file-delete.png)

## <a name="save-the-flow"></a>フローを保存する
1. 画面上部に作成するフロー名を入力または貼り付けてから **フローの作成** をクリックまたはタップします。
   
    ![フローを保存する](./media/common-data-model-approve/save-flow.png)
2. **閉じる** と **完了** を順にクリックまたはタップします。
3. 少なくとも 2 つのファイルを Dropbox の指定したフォルダーに追加します。1 つで承認をテストし、もう 1 つで拒否をテストします。

## <a name="build-the-app"></a>アプリを構築
1. [powerapps.com](https://make.powerapps.com) にサインインして、左側のナビゲーション バー下部付近にある **新しいアプリ** をクリックまたはタップします。
   
    ![ブラウザーでアプリを作成する](./media/common-data-model-approve/new-app-button.png)
2. 表示されるダイアログ ボックスで、Windows 用の Power Apps Studio  と Web 用の Power Apps Studio のいずれかを開くオプションをクリックまたはタップします。
3. Windows 用の Power Apps Studio を開いた場合は、左側のナビゲーション バーの **新規** をクリックまたはタップします。
4. **アプリをデータから作成する** 配下の、**Common Data Service** タイルにて **Phone レイアウト** をクリックまたはタップします。
   
    ![アプリの作成](./media/common-data-model-approve/afd-cdm.png)
5. **検索** ボックスに **レビュー** と入力するか貼り付けます。
   
    ![エンティティの検索](./media/common-data-model-approve/search-entities.png)
6. **エンティティの選択** 配下の **Dropbox ファイルのレビュー** をクリックまたはタップします。
   
    ![エンティティの選択](./media/common-data-model-approve/choose-entity.png)
7. 画面右下隅付近の **接続** をクリックまたはタップします。
   
    ![接続ボタン](./media/common-data-model-approve/connect-button.png)
8. 紹介ツアーの開始画面が表示されたら、ツアーを実行して Power Apps の概要を理解します (または、**スキップ** をクリックまたはタップします)。
   
    ![概要ツアー](./media/common-data-model-approve/quick-tour.png)
   
    画面左上隅の疑問符アイコンをクリックまたはタップして、**概要ツアーを見る** をクリックまたはタップすると、後でいつでもツアーに参加できます。
9. (オプション) 画面下部付近のスライダーをドラッグして、ズーム拡大するとアプリが見やすくなります。
   
    ![ズーム コントロール](./media/common-data-model-approve/zoom-control.png)

## <a name="customize-the-app"></a>アプリをカスタマイズする
1. 右側のナビゲーション バーで、ヘッダーと説明が表示されたレイアウトをクリックまたはタップします。
   
    ![接続ボタン](./media/common-data-model-approve/choose-layout.png)
2. **BrowseScreen** で検索バーのすぐ下をクリックまたはタップし、大きいテキストボックス コントロールを選択します。
   
    ![ヘッダーを選択する](./media/common-data-model-approve/select-header.png)
3. 右側のウィンドウ下部で、下向き矢印をクリックまたはタップして一覧を開きます。
   
    ![ドロップダウンを開く](./media/common-data-model-approve/open-dropdown.png)
4. 下側の一覧で **タイトル** をクリックまたはタップして、追加されたファイルのファイル名を表示します。
   
    ![ヘッダー データを設定する](./media/common-data-model-approve/set-heading.png)
5. 右側のウィンドウで上部の一覧を開き、**状態** をクリックまたはタップして各ファイルの状態を表示します。
   
    ![本文データを設定する](./media/common-data-model-approve/set-body.png)

## <a name="test-the-overall-solution"></a>ソリューション全体をテストする
1. Power Apps で左上隅の再生ボタンをクリックまたはタップし、プレビュー モードを開きます。
   
    ![プレビュー モードを開く](./media/common-data-model-approve/open-preview.png)
2. リストの最初のファイルで矢印をクリックまたはタップして、そのファイルの詳細を表示します。
   
    ![詳細画面を開く](./media/common-data-model-approve/open-details.png)
3. 右上隅の鉛筆アイコンをクリックまたはタップし、ファイルの詳細を変更します。
   
    ![編集画面を開く](./media/common-data-model-approve/edit-record.png)
4. **状態** ボックスに **承認済** と入力するか貼り付けます。
   
    ![ファイルを承認する](./media/common-data-model-approve/change-status.png)
5. 画面右上隅のチェックマーク アイコンをクリックまたはタップして変更を保存し、詳細画面に戻ります。
   
    ![変更の保存](./media/common-data-model-approve/save-record.png)
   
    数分後に、ファイルが承認されたことを示すメールを受信します。
6. 画面右上隅の戻るボタンをクリックまたはタップして、参照画面に戻ります。
   
    ![参照画面に戻る](./media/common-data-model-approve/back-arrow.png)
7. 一覧のもう 1 つのファイルの矢印をクリックまたはタップし、そのファイルの詳細を表示します。
   
    ![詳細画面を開く](./media/common-data-model-approve/open-details.png)
8. 右上隅の鉛筆アイコンをクリックまたはタップし、ファイルの詳細を変更します。
   
    ![編集画面を開く](./media/common-data-model-approve/edit-record.png)
9. **状態** ボックスに **拒否** と入力または貼り付けます (または **Aproved** や **Approoved** を含む **Approved** 以外のもの)。
   
    ![ファイルを拒否する](./media/common-data-model-approve/reject-file.png)
10. 画面右上隅のチェックマーク アイコンをクリックまたはタップして変更を保存し、詳細画面に戻ります。
    
     ![変更の保存](./media/common-data-model-approve/save-record.png)
    
     数分後にファイルが拒否されたことを示すメールを受信し、Dropbox からファイルが削除されます。

