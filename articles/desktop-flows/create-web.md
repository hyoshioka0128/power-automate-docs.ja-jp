---
title: Web サイトの Selenium IDE のフローを作成する方法 | Microsoft Docs
description: Selenium IDE のフローを使用して Web アプリを自動化する方法について説明します。
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
ms.openlocfilehash: ab838da3bd03aa78b21ec992c742a4ae088db03b
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711661"
---
# <a name="create-and-test-selenium-ide-flows"></a>Selenium IDE フローの作成とテスト

シンプルな Selenium フローを作成するには、次の手順に従います。

## <a name="create-a-selenium-ide-flow"></a>Selenium IDE フローを作成する

1. [Microsoft Edge （バージョン80以降）](https://www.microsoft.com/edge) 、または Google Chrome を開き、[Power Automate](https://flow.microsoft.com/) に移動します。

1. 必要に応じて職場または学校アカウントでサインインします。

1. **マイ フロー** > **デスクトップ フロー** > **新規** を選択します。

   ![新規 Selenium IDE フローを作成する](../media/create-windows-desktop-flow/create-new-windowsrecorder.png "新規 Selenium IDE フローを作成する")

1. **デスクトップ フローの追加オプション** をクリックします。
    
   ![デスクトップ フローの追加オプション](../media/create-windows-desktop-flow/click-Additional-desktop-flow-options.png "デスクトップ フローの追加オプション")

1. Selenium IDE を選択し、 **次へ** をクリックします。
    
   ![Web アプリ を選択](../media/create-web-desktop-flow/select-seleniumIDE-flow.png "Web アプリ を選択")

1. **フロー名** フィールドに Selenium IDE フローの名前を入力します。

1. 自動化する Web サイトの URL を **ベース URL** フィールドに入力し、**レコーダーの起動** を選択します。

   ![名前と URL の指定](../media/create-web-desktop-flow/give-a-selenium-flow-name.png "名前と URL の指定") 

   Selenium IDE が起動します。

   >[!TIP] 
   >ヒント: 同じタブ内で、複数の HTTP または HTTPS Web サイト間でアクションを記録できます。  

1. Selenium IDE で、画面の右上にある赤色の **REC** ボタンを選択してレコーダーを起動します。

   前の手順で選択した URL が開きます。

   ![REC の選択](../media/create-web-desktop-flow/select-rec.png "REC の選択")

1.  Web サイト上で記録する操作を実行します。 
    
    >[!TIP]
    >右下に記録の状態が表示されます。

    ![記録の状態](../media/create-web-desktop-flow/recording-status.png "記録の状態")

1.  記録が終了したら、Selenium IDE の右上隅にある赤い **停止** ボタンを選択します。

    ![[停止] ボタン](../media/create-web-desktop-flow/stop-button.png "[停止] ボタン" )

1. 画面の左上にある **現在のテストを実行** ボタンを選択して、先ほど作成した Selenium IDE のフローを表示します。

    ![現在のテストを実行](../media/create-web-desktop-flow/run-test.png "現在のテストを実行")

   >[!TIP]
   >ステップ間の待機時間を設定して、テストのローカル再生速度を遅くすることができます。 この設定はテストのみを目的としており、Selenium IDE のフローが展開されても影響はありません。  
  
1. Selenium IDE の右上にある **プロジェクトの保存** ボタンを選択します。 これにより、プロジェクトが閉じ、アップロードされます。

Selenium IDE フローを作成されたので、これを他のフローで使用できます。

## <a name="limitations-and-known-issues-for-selenium-ide-flows"></a>Selenium IDE のフローの制限事項と既知の問題

>[!WARNING]
>**Selenium IDE のパスワードはプレーン テキストで格納されます。**  

**再生用の一時ユーザー プロファイル**

Selenium IDE の記録は現在のユーザー プロファイルで実行されますが、再生は一時ユーザー プロファイルを使用して行われます。 つまり、認証を必要とする Web サイトで、記録セッション中は資格情報を要求されない可能性がありますが、再生時に認証手順が必要になります。 

これに対処するには、ユーザーはスクリプトを手動で編集して、ログイン プロセスに必要なコマンドを挿入する必要があります。

**その他の制限事項**

-   Web 記録セッション中のデスクトップ アプリケーションの記録。 Web アプリケーションとデスクトップ アプリケーションの両方を自動化する必要がある場合は、種類ごとに個別のデスクトップ フローを作成し、それらを 1 つのクラウド フロー内で組み合わせることができます。

- 多要素認証 (MFA) はサポートされていません。MFA を必要としないテナントを使用してください。

- 次の Selenium IDE コマンドはサポートされていません: Run、AnswerOnNextPrompt、ChooseCancelOnNextConfirmation、ChooseCancelOnNextPrompt、ChooseOkOnNextConfirmation、Debugger、ClickAt、DoubleClickAt、Echo、MouseOut、MouseUpAt、および MouseDownAt。

- Selenium IDE のアクションやステップは、実行時間が 1 分を超えることはできません。  [Power Automate Desktop](introduction.md) を代わりに使用します。

- 右クリックはサポートされていません。 

-   Foreach コマンドを使用すると、追加の Selenium IDE フローの入力が生成されます。 この問題を回避するには、追加のフィールドに任意の値を入力します。 再生には影響しません。

- .side ファイルに複数のテスト プロジェクトが含まれている場合は、作成された最初のプロジェクトだけが実行されます。 
   
   >[!TIP]
   >Selenium IDE では、作成日ではなく名前によってテストが並べ替えられるため、作成された最初のテストが一覧で最初のテストにならない場合があることに注意してください。

-   Selenium IDE での直接再生は、意図したとおりに動作しない場合があります。 ただし、実行時の再生は正常に動作します。

## <a name="next-steps"></a>次の手順

- [デスクトップ フローの実行](run-desktop-flow.md)について説明します。

- Selenium IDE で[入出力](inputs-outputs-web.md)パラメーターを使用する方法について説明します。

 
