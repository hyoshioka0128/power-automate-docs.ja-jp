---
title: ユーザー入力を取得するボタン フローで反復タスクを自動化する方法 | Microsoft Docs
description: Power Automate を使用すると、反復的なタスクを簡単に自動化できます。 フローでは、反復的なタスクを実行するときにユーザー入力を取得することもできます。
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
ms.date: 02/15/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5a2fa063b5379999a5dcbe37a56271fccf435cae
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79192372"
---
# <a name="introducing-button-flows-with-user-input"></a>ユーザー入力のあるボタン フローの概要

ボタン フローを作成すると、ボタンをタップするだけで日常的なタスクを実行することができます。 フローの実行時に使用される特定の詳細をユーザーが指定できるようにすることで、フローをカスタマイズできます。 このトピックでは、ユーザーからの入力を受け取るボタン フローを作成する手順、さらにボタン フローを実行して、ユーザー入力を指定する方法を明らかにする手順を説明します。

Power Automate の Web サイトや Power Automate のモバイル アプリでボタン フローを作成できます。 このトピックでは、Web サイトを使用します。

### <a name="prerequisites"></a>前提条件
* Power Automate Web サイトのアカウント。

## <a name="open-the-template"></a>テンプレートを開く
1. [Power Automate Web サイト](https://flow.microsoft.com)にサインインし、検索ボックスに「**Visual Studio**」と入力し、検索アイコンをクリックまたはタップして、Visual Studio に関連するすべてのテンプレートを検索します。
   
    ![](./media/button-flow-with-user-input-tokens/1.png)  
2. **[Open a Priority 2 Bug in Visual Studio]** \(Visual Studio で優先順位 2 のバグを開く) テンプレートを選択します。
   
    ![](./media/button-flow-with-user-input-tokens/2.png)  
3. **[このテンプレートを使用]** ボタンを選択します。
   
    ![](./media/button-flow-with-user-input-tokens/3.png)  
   
    このテンプレートでは、Visual Studio Team Services (VSTS) と、プッシュ通知サービスを使用します。 これらのいずれのサービスにも接続していない場合は、サービスにサインインする必要があります。 **[サインイン]** ボタンは、サービスへのサインインが必要な場合にのみ表示されます。
4. 必要なすべてのサービスにサインインした後で、 **[続行]** ボタンを選択します。
   
    ![](./media/button-flow-with-user-input-tokens/4.png)  
5. (省略可能) ポータルの上部にあるボックスに目的の名前を入力することにより、フローの名前を変更します。
   
    ![](./media/button-flow-with-user-input-tokens/5.png)

## <a name="customize-the-user-input"></a>ユーザー入力をカスタマイズする
1. トリガー カードで、 **[編集]** を選択します。
   
    ![](./media/button-flow-with-user-input-tokens/6.png)  
2. カスタム入力フィールドを追加できるように、 **+** アイコンを選択してページを展開します。
   
    ![](./media/button-flow-with-user-input-tokens/7.png)
3. ユーザーがフローを実行する場合に利用可能にするカスタム フィールドごとに、**入力のタイトル**と**入力の説明**を入力します。  
   
    この例では、このフローを使用する任意のユーザーがバグの再現ステップを入力し、バグの重大度を評価できるように、2 つのカスタム入力フィールド **[Bug repro steps]** \(バグの再現ステップ) と **[Bug severity]** \(バグの重大度) を作成します。  
   
    ![](./media/button-flow-with-user-input-tokens/8.png)

## <a name="customize-the-bug"></a>バグをカスタマイズする
1. カードのタイトル バー **[新しい作業項目を作成]** をタップします。
   
    ![](./media/button-flow-with-user-input-tokens/9.png)  
2. VSTS 環境に適した内容を選択し、 **[編集]** を選択します。
   
    たとえば、**myinstance** と入力して、myinstance.visualstudio.com に接続します。
   
    ![](./media/button-flow-with-user-input-tokens/10.png)  
3. **[詳細オプションの表示]** を選択して、このカードの他のフィールドを表示します。
   
    ![](./media/button-flow-with-user-input-tokens/11.png)  
4. **[Bug title]** \(バグのタイトル) トークンの前にカーソルを置き、 **[タイトル]** テキスト フィールドに「重大度:」と入力します。
5. カーソルがタイトル テキスト フィールドに置かれた状態で、 **[Bug severity]** \(バグの重大度) トークンを選択して、「 -- 」と入力します。  
6. **[説明]** テキスト フィールドで、 **[Bug description]** \(バグの説明) トークンの直後にカーソルを置き、Enter キーを押して新しい行を開始します。
7. 新しい行にカーソルを置き、 **[Bug Repro steps]** \(バグの再現手順) トークンを選択します。
   
    ![](./media/button-flow-with-user-input-tokens/12.png)

## <a name="customize-the-push-notification"></a>プッシュ通知をカスタマイズする
1. **[プッシュ通知を送信]** カード上のタイトル バーをタップして展開します。
2. 動的なコンテンツのトークンの一覧で、 **[詳細を表示]** を選択し、 **[リンク]** テキスト フィールドに **[URL]** トークンを追加します。
3. **[リンク ラベル]** テキスト フィールドに、 **[ID]** トークンを追加します。
   
    ![](./media/button-flow-with-user-input-tokens/13.png)  
4. メニュー上の **[フローの作成]** をタップして、フローを作成します。![](./media/button-flow-with-user-input-tokens/14.png)  

## <a name="run-your-flow"></a>フローを実行する
このチュートリアルでは、先ほど作成したボタンのフローを、Power Automate 用のモバイル アプリを使用して実行します。 タイトル、説明、再現ステップ、重大度レベルを使用してバグを作成するために必要とされるあらゆるユーザー入力を指定します。  

1. Power Automate 用のモバイル アプリでは、 **[ボタン]** タブをタップし、 **[Create bug report with steps]** \(ステップを含むバグ レポートを作成) ボタンをタップします。
   
    ![](./media/button-flow-with-user-input-tokens/runmt1.png)  
2. 報告するバグのタイトルを入力し、 **[次へ]** をクリックします。 例:
   
    ![](./media/button-flow-with-user-input-tokens/runmt2.png)  
3. 報告するバグの説明を入力し、 **[次へ]** をタップします。 次に例を示します。
   
    ![](./media/button-flow-with-user-input-tokens/runmt3.png)  
4. 報告するバグを再現するためのステップを入力し、 **[次へ]** をタップします。 例:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3-1.png)  
5. 報告するバグの重大度を入力し、 **[完了]** をタップします。  
    ![](./media/button-flow-with-user-input-tokens/runmt3-2.png)  
   
    フローが実行されます。
6. (省略可能) **[アクティビティ]** タブをタップして、結果を表示します。
   
    ![](./media/button-flow-with-user-input-tokens/runmt5.png)  
7. (省略可能) **[新しい作業項目の作成]** ステップをタップすることにより、フローの実行の詳細な結果を表示します。
   
    ![](./media/button-flow-with-user-input-tokens/runmt6.png)


## <a name="use-different-input-types"></a>異なる入力の種類を使用する

ボタン フローではまた、豊富な種類のデータが受け入れられます。 ボタン フローで受け入れられるデータ入力の種類をまとめると以下のようになります。 

- テキスト
- ドロップダウン (ラジオボタンなど)
- 電子メール アドレス
- ファイル (電話の写真など)
- [はい/いいえ] チェック ボックス
- 数値
- 日付 (予定表の選択付き)

以上の種類の入力を使用するには、 **[手動でフローをトリガーします]** トリガーを追加し、いずれかの種類をフローに追加します。

![入力オプション](media/button-flow-with-user-input-tokens/input-options.png)

また、入力に必須か任意を指定すると便利です。 各入力フィールドのアクション メニュー (右側にある [...]) を使用します。 ボタンに 1 個につき入力は 5 つまでという上限があります。

![オプション フィールドを選択する](media/button-flow-with-user-input-tokens/required-optional.png)

## <a name="next-steps"></a>次の手順
* [ボタン フローを共有する](share-buttons.md)
* [ボタン フローについて](introduction-to-button-flows.md)  
* [トリガー トークンのあるボタン フローについて](introduction-to-button-trigger-tokens.md)  

