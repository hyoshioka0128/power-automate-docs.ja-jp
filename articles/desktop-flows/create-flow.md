---
title: Power Automate Desktop フローの作成 | Microsoft Docs
description: Power Automate デザイナーを使用してデスクトップ フローを作成します。
author: olegmelnykov
ms.service: flow
ms.topic: article
ms.date: 12/09/2020
ms.author: olmelnyk
ms.reviewer: olmelnyk
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: bb488cef1ed8b173bfde7e9a68479f7c9b8233c6
ms.sourcegitcommit: 25e860afc49c5cc38de74f56da4c2aa1bc36dac5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4712984"
---
# <a name="create-a-power-automate-desktop-flow"></a>Power Automate Desktop フローを作成する

デスクトップ フローは、Web やデスクトップのタスクの自動化に使用します。 [Power Automate Desktop](introduction.md)を使用すると、デスクトップ上だけでなく Web 上のタスクも自動化することができます。 あるいは、デスクトップ フローを作成する 2 つのレガシーな方法 ([Windows レコーダー (V1) と Selenium ID](overview.md)) を使用することもできます。


## <a name="trigger-the-console-from-the-portal"></a>ポータルからコンソールをトリガーする


1. Power Automate Desktop でデスクトップ フローを作成するには、アプリを開き、**新規フロー** を選択します。

   ![新しいフロー ボタン](\media\create-flow-console\console.png)

1. デスクトップ フローの名称を入力し、**OK** をクリックします。

   ![フロー ダイアログ ボックスのビルド](\media\create-flow-console\build-flow-dialog.png)

1. **フロー デザイナー** でフローを作成し、**Ctrl+S** を押下してフローを保存します。 フロー デザイナーを閉じると、コンソールにフローが表示されます。

   ![コンソールのフロー](\media\create-flow-console\console-flow.png)


## <a name="design-a-flow-in-power-automate-and-power-automate-desktop"></a>Power Automate と Power Automate Desktop でフローを設計する

1. デスクトップで新規フォルダーを作成し、**Countries** と名前を付けます。

1. **flow.microsoft.com** にアクセスし、**自分のフロー** を選択し、**+新規フロー** と **インスタント クラウド フロー** を選択します。

   ![自分のフロー インスタント ブランク](\media\design-flow\my-flows-instant-blank.png)

1. ダイアログ ボックスで、クラウド フローの名前を入力し、**フローを手動でトリガーする** を選択して **作成** を選択します。

   ![手動でフローをトリガーする](\media\design-flow\manually-trigger-flow.png)

1. **+ 新しいステップ** を選択します。

   ![新しいステップ](\media\design-flow\new-step.png)

    <!--todo: Needs new screenshot and verify if action names are being updated-->
1. **power automate desktop** を検索し、**Power Automate Desktop でビルドしたフローを実行する** アクションを選択します。

   ![アクションの検索](\media\design-flow\action-search.png)

1. アクションの実行モードで、**有人 - サインイン時に実行** を選択し、デスクトップ フロー配下で **新しいデスクトップ フローを作成** を選択します。

   ![Windows レコーダー (V1) のフローのプロパティを実行する](\media\design-flow\run-desktop-flow-v2-action-properties.png)

1. デスクトップ フロー名を入力するか、または生成されたものを入力して、**アプリの起動** を選択します。

   ![ダイアログ ボックス](\media\design-flow\build-desktop-flow-dialog.png)

1. ブラウザから、flow.microsoft.com でアプリケーションを開くことを許可するかどうかを尋ねるメッセージが表示される場合があります。 このアクションが Power Automate  Desktop で継続することを許可します。

   ![ブラウザーでのアプリケーションの起動](\media\design-flow\browser-open-application.png)

1. Power Automate Desktop で、変数ペインを開き、**+** を選択し、**入力** を選択して新しい入力変数を追加します。

   ![新しい入力変数を追加する](\media\design-flow\add-new-input-variable.png)

1. 変数を次のように構成します:
   * 変数のタイプ: **入力**
   * 変数の名前: **CountryName**
   * データ型: **テキスト**
   * 既定値: **フランス**
   * 外部名称: **CountryName**
   * 説明: **国名の入力変数です。**

   ![変数入力の編集](\media\design-flow\edit-variable-input.png)

1. **現在時刻の取得** アクションを追加し、**取得** を **現在の日付のみ** に設定します。 **保存** を選択した後、Power Automate Desktop ワークスペースにアクションを追加します。 このアクションは現在の日付のみを取得し、変数に格納します。

   ![現在の日時のアクション プロパティを取得する](\media\design-flow\get-current-date-and-time-action-properties.png)

1. **datetimeをテキストに変換** アクションを追加します。 **Datetime の変換** で、**変数** アイコンを選択し、ポップアップの **%CurrentDateTime%** をダブルクリックしてフィールドに変数を追加します。 使用するフォーマットに **カスタム** を設定し、**カスタムフォーマット** に **MM-dd-yyyy** を入力します。 このアクションは datetime 変数をテキスト変数に変換し、同時に日付を指定されたフォーマットに変換します。

   ![datetime 出来ストを変換する](\media\design-flow\convert-datetime-text.png)

1. **特殊フォルダーの取得** アクションを追加します。 **特殊フォルダーの名前** の既定の名称は、**デスクトップ** です。 このアクションは、現在のユーザーのデスクトップの場所を変数に保存します。

   ![特殊フォルダ アクション プロパティの取得](\media\design-flow\get-special-folder-action-properties.png)

1. **フォルダーの作成** アクションを追加し、**新規フォルダの作成場所** を **%SpecialFolderPath%\Countries** に設定し、**新規フォルダー名** を **%CountryName%** に設定します。 このアクションは、指定された場所に指定された名前の新しいフォルダを作成します。

   ![フォルダ アクションプ ロパティの作成](\media\design-flow\create-folder-action-properties.png)

1. **テキストをファイルに書き込む** アクションを追加し、変数のポップアップを使用して **ファイル パス** を **%SpecialFolderPath%\Countries\\%CountryName%\\%FormattedDateTime%.txt** に設定します。 

1. **書き込むテキスト** を **Power Automate Desktop が書き込むテキスト** に設定します。 このアクションは、指定されたテキストを現在のユーザーのデスクトップ上のテキストファイルに書き込み、ファイル名を現在の日付に設定します。

   指定したテキストをテキスト ファイルに書き込みます。

   ![テキスト ファイル書き込みアクションプロパティ](\media\design-flow\write-text-file-action-properties.png)

1. **フォルダー内のファイルを取得** アクションを追加し、**フォルダー** を **%SpecialFolderPath%\Countries\\%CountryName%** に設定します。 このアクションは、指定したフォルダ内のファイルのリストを取得します。

   ![フォルダ ファイル アクション プロパティの取得](\media\design-flow\get-files-folder-action-properties.png)

1. **変数** ペインで、次のように 2 つの出力変数を作成します:
   * 変数のタイプ: **出力**
   * 変数の名前: **FileCount**
   * 外部名称: **FileCount**
   * 説明: **ファイルカウントの出力変数です。**

   して

   * 変数のタイプ: **出力**
   * 変数の名前: **FilePath**
   * 外部名称: **FilePath**
   * 説明: **出力変数のファイル パスです。**

   ![新規出力変数](\media\design-flow\new-output-variable.png)

   ![新規出力変数 2](\media\design-flow\new-output-variable-2.png)

1. **変数の設定** アクションを 2 つ追加し、次のように構成します :
   
   * 変数の設定: **FilePath**
   * 設定: **%SpecialFolderPath%\Countries\\%CountryName%\\%FormattedDateTime%.txt**
   
   して
   
   * 変数の設定: **FileCount**
   * 設定: **%Files.count%**

   ![変数アクション プロパティの設定](\media\design-flow\set-variable-action-properties.png)

   ![変数アクション プロパティの設定 2](\media\design-flow\set-variable-action-properties-2.png)

1. **保存** を選択してフローを保存し、フロー デザイナーを閉じます。

   ![完了したフローを保存する](\media\design-flow\save-complete-flow.png)

1. Power Automate に戻り、ダイアログ ボックスで **作業の継続** を選択します。

   ![パッド ポータル ダイアログ ボックスに戻り、作業を継続する](\media\design-flow\pad-portal-dialog-keep-working.png)

1. アクションで新しいデスクトップ フローを選択し、**CountryName** に **Greece** を入力します。

   ![デスクトップ フロー アクション プロパティの実行 2](\media\design-flow\run-desktop-flow-v2-action-properties-2.png)

1. **保存** を選択してフローを保存し、**テスト** を選択します。

   ![テスト フローの保存](\media\design-flow\save-test-flow.png)

1. **トリガー アクションを実行する** を選択します。 **テスト** を実行します。

   ![テスト フロー](\media\design-flow\test-flow.png)

1. Power Automate が Power Automate Desktop に接続する際は、**続ける** を選択し、**フローの実行**、**完了** を選択します。

   ![フローの実行ポップアップ 3](\media\design-flow\run-flow-pop-out-3.png)

1. フローの実行が終了すると、すべてのアクションに緑色のチェックマーク アイコンが表示され、フローが正常に実行されたことを確認する通知が表示されます。

   ![フロー実行の成功](\media\design-flow\successful-flow-run.png)

   <!--todo: Needs new screenshot and verify if action names are being updated-->
  
1. **Power Automate Desktop でビルドしたフローの実行** アクションを選択し、入力内容と出力内容を開きます。 **FileCount** と **FilePath** の 2 つの変数の値が Power Automate Desktop から返されます。 同様に、出力変数はフロー内の他の場所で使用することができます。

   ![変数の値](\media\design-flow\variables-values.png)

1. デスクトップの **Countries** フォルダーを確認します。 **Greece** という名前のフォルダーが追加され、今日の日付のテキスト ファイルが含まれていルことが確認できます。
