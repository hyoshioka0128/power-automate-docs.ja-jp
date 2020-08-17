---
title: インスタント フローで反復タスクを自動化および実行する方法 | Microsoft Docs
description: インスタント フローの概要。
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
ms.date: 03/17/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 81ae2f466fc2bdfa688b35544971871de2e45450
ms.sourcegitcommit: 3fbffb299dd125a6a9a39fb2c1296abdfc362ba6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "3623719"
---
# <a name="introducing-instant-flows"></a>インスタント フローの概要

ボタンを 1 回タップするだけで実行できる、多くの反復的なタスクがあります。 たとえば、毎日のチームミーティングに参加するようにチームにメールで注意を促す場合や、その日に予定されているチェックインがなくなったことを通知された後に、コードベースの新しい Visual Studio Codespacesビルドを開始する場合などが考えられます。 インスタント フローを利用すれば、モバイル デバイスのボタンをタップするだけでこれらのタスクやその他の多くのタスクを実行できます。

![概要画像](./media/introduction-to-button-flows/buttons-montage.png) 

> [!NOTE]
> インスタント フローは、モバイル デバイスまたは Power Automate から作成できます。

## <a name="why-create-buttons"></a>なぜボタンを作成するのか?
場所や時間に関係なく、モバイル デバイスから繰り返し作業を簡単に実行できるようにボタンを作成します。 ボタンを実行すると時間を節約でき、実行する作業が自動化されるため、手動で行うよりエラーが少なくなります。  

## <a name="create-a-button"></a>ボタンを作成する
### <a name="prerequisites"></a>前提条件
* [Power Automate](https://flow.microsoft.com) へのアクセス
* コネクタを利用してボタンを作成するためのアクセス許可があるアカウント。 たとえば、Dropbox にアクセスするボタンを作成するには、Dropbox アカウントが必要になります。

### <a name="from-the-portal"></a>ポータルから
このチュートリアルでは、 Visual Studio Codespaces のビルドを開始し、ビルドの開始を通知を送信するボタンを作成してみましょう。

1. [Power Automate](https://flow.microsoft.com) にサインインします。
1. 画面の左側から **作成** を選択します。
1. **インスタント フロー** を選択します。
1. **フロー名** > **フローを手動でトリガーする** > **作成** でフローに名前を付けます。 
 
2. テンプレートの一覧から **Trigger a new build in VSO** (VSO で新しいビルドをトリガーする) テンプレートを選択します。  
   ![テンプレートを示す画像 ](./media/introduction-to-button-flows/create-button-2.png)  
3. **Trigger a new build in VSO** (VSO で新しいビルドをトリガーする) ページで **このテンプレートを使用** ボタンを選択します。   
   ![使用するテンプレートを示す画像](./media/introduction-to-button-flows/create-button-3.png)  
4. サインインしていない場合、この時点でサインインするように求められます:  
   ![サインイン オプションを示す画像](./media/introduction-to-button-flows/create-button-4.png)  
5. Flow にサインインすると、選択したテンプレートで使用されるコネクタにサインインするように求められます。 この例では、上の手順 2 で、**Trigger a new build in VSO** (VSO で新しいビルドをトリガーする) テンプレートを選択したので、まだサインインしていない場合、VSO (と使用しているその他のコネクタ) にサインインする必要があります:  
   ![[サインイン] ボタンを示す画像](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. VSO アカウントへのアクセス許可を Power Automate に与えることに同意する場合、**承諾** ボタンを選択します。  
   ![Visual Studio アカウントへのアクセスを承認するためのオプションを示す画像](./media/introduction-to-button-flows/create-button-5.png)   
   **注** 各コネクタを同様に承認する必要があります。 次の手順に進む準備ができると、このようなデザイナーが表示されるはずです。 **続行** ボタンを選択して先に進みます:  
   ![続行ボタン](./media/introduction-to-button-flows/create-button-6.png)   
7. これで、開始するビルドのプロパティを構成する準備ができました。    
   ![プロパティ画面](./media/introduction-to-button-flows/create-button-7.png)  
8. **新しいビルドをキューに入れる** カードで **アカウント名**、**プロジェクト名**、**ビルド定義 ID**、**ソース ブランチ** を選択するか入力し、任意で **パラメーター** を選択するか、入力します。    
   ![新しいビルドの画面](./media/introduction-to-button-flows/create-button-8.png)  
9. 次に、**プッシュ通知を送信する** カードでプッシュ通知のプロパティを構成します。 既定では、このプッシュ通知は、ビルドの状態を表示する Web ページに HTML リンクを送信するように構成されています:  
   ![プッシュ通知の画面](./media/introduction-to-button-flows/create-button-9.png)  
10. **フローの作成** ボタンを選択し、インスタント フローを保存します: ![フロー ボタンの作成](./media/introduction-to-button-flows/create-button-10.png)  
11. しばらくすると、この成功メッセージが表示されるはずです:  
    ![成功メッセージ](./media/introduction-to-button-flows/create-button-11.png)  

おめでとうございます、インスタント フローが作成されました! これで Flow アプリの **ボタン** タブから、時と場所に関係なく、このインスタント フローを実行できます。 "ボタン" を押すだけで実行されます! Power Automate モバイル アプリは、[Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios)、[Windows Phone](https://aka.ms/flowmobilewindows) で利用可能です。

### <a name="from-your-mobile-device"></a>モバイル デバイスから

>[!NOTE]
>このチュートリアルでは Android デバイスの画面を利用しますが、iOS でも画面や動作は共通しています。

アプリの場合:

1. **参照** タブを選び、**ボタン** カテゴリにスクロールします。  
   ![ランディング画面](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. **すべて表示** リンクを選択します。 すぐに使えるボタンのテンプレートがすべて表示されます。     
   ![[すべて表示] のリンク](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. **チームに対して会議への参加を通知するメールを送信する** テンプレートを選択する    
   ![チームに対して会議への参加を通知するメールを送信するの画像](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. ページの一番下にある **このテンプレートを使用** リンクを選択します。    
   ![[このテンプレートを使用] の画像](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. このテンプレートが使用するすべてのサービスにサインインする必要があります:    
   ![サービスへのサインインまたはサービスの更新の画像](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. すべてのサービスにサインインしたら、**次へ** リンクを選択します。      
   ![[次へ] のリンク](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. **作成** リンクを選択します。 ここで、フローを確認して、たとえば、メールを個人設定するために必要な変更を加えることもできます。        
   ![リンクの作成](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. しばらくすると、インスタント フローが作成されます。 **SEE MY FLOW** (自分のフローを見る) を選択します:   
   ![SEE MY FLOW (自分のフローを見る) の画像](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. **My flows** (マイ フロー) タブ上ですべてのフローを表示できます  
   ![すべてのフローの表示の画像](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

おめでとうございます、インスタント フローが作成されました! これで Flow アプリの **ボタン** タブから、時と場所に関係なく、このインスタント フローを実行できます。 "ボタン" を押すだけで実行されます! 現在のところ、Flow アプリは Android と iOS のモバイル デバイスで利用できます。  

![新しいインスタント フローの画像](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-an-instant-flow"></a>インスタント フローをトリガーする
インスタント フローが作成できたので、次は実行しましょう。 インスタント フローは Flow アプリからのみ実行できます。 Android または iOS のモバイル デバイスに Flow がインストールされていることを確認してください。  

1. Flow アプリを起動し、ページの一番下にある **ボタン** タブをタップし、トリガーするインスタント フローを表す *ボタン* をタップします。  
   ![フローのトリガー](./media/introduction-to-button-flows/trigger-button-1.png)   
2. フローの実行中に進捗状況を確認します:  
   ![実行中のフローの画像](./media/introduction-to-button-flows/trigger-button-2.png)   
3. 最後に、ページが更新され、インスタント フローの完了が示されます:  
   ![フローの完了の画像](./media/introduction-to-button-flows/trigger-button-3.png)   

フローの実行はこれで終わりです。 

電子メールが送信されたことを示すプッシュ通知を受け取るはずです。  

## <a name="monitor-your-instant-flow-runs"></a>インスタントフローの実行を監視する
Flow アプリの **アクティビティ** タブからインスタント フローを監視できます。   
![[アクティビティ] タブの画像](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

>[!ヒント] 任意のアクティビティをタップして実行結果を表示し、実行に関する情報を入手できます。  

![[アクティビティの詳細] の画像](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-instant-flows"></a>インスタント フローを管理する
インスタント フローは完全に制御でるため、時と場所に関係なく、ボタンを有効/無効にしたり、編集したり、削除したりできます。 モバイル アプリまたはフロー ポータルから、**My flows** (マイ フロー) を選択し、フローの管理を開始します。    

Flow アプリの **My flows** (マイ フロー) タブで:

1. 管理するフローを選択します:    
   ![すべてのフローの画像](./media/introduction-to-button-flows/trigger-button-4.png)   
2. 実行する操作に基づき、いずれかのオプションをタップできます:    
   ![フローの管理オプション](./media/introduction-to-button-flows/manage-flow-1.png)  

   **フローの削除** をタップすると、フローが削除されます。  

      >[!WARNING]
      >フローを削除すると、すべての実行履歴が削除されます。

      ![フロー警告の削除の画像](./media/introduction-to-button-flows/manage-flow-2.png)   

   インスタント フローの編集が完了したら **更新** をタップし、変更を保存します:   
   ![フローの更新の画像](./media/introduction-to-button-flows/manage-flow-3.png)   

   **実行履歴** をタップすると、特定のインスタント フローの全実行結果が表示されます:    
   ![実行履歴を表示する](./media/introduction-to-button-flows/manage-flow-4.png)  

   フローを無効にすると、**ボタン** タブで利用できなくなります。    
   ![無効なフローは [ボタン] タブにありません](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>次の手順
* [インスタント フローを共有します](share-buttons.md)。
* インスタント フローの実行時に [ボタン トリガー トークン](introduction-to-button-trigger-tokens.md) を使用してリアルタイムのデータを送信する方法について学習します。
* [Android](https://aka.ms/flowmobiledocsandroid) 向けの Power Automate モバイル アプリ、[iOS](https://aka.ms/flowmobiledocsios)、[Windows Phone](https://aka.ms/flowmobilewindows) をインストールします。

