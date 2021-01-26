---
title: Softomotive 製品のプロセス マイグレーター (プレビュー版) | Microsoft Docs
description: Softomotive 製品のプロセス マイグレーター (プレビュー版)
author: mariosleon
ms.service: flow
ms.topic: article
ms.date: 12/16/2020
ms.author: marleon
ms.reviewer: ''
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 21f2cbdc92f865a0e657a6bb441e31db501d323e
ms.sourcegitcommit: 15e6b42e54d4151ee582a4a6d6d29975f6d8a1e7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "4761961"
---
# <a name="process-migrator-for-softomotive-products-preview"></a>Softomotive 製品のプロセス マイグレーター (プレビュー版)
[このトピックはプレリリース ドキュメントであり、変更されることがあります。]

Softomotive 製品のプロセス マイグレーター (プレビュー版)は、WinAutomation で作成した自動化プロセスを Power Automate Desktop フローへの移行を支援するアプリケーションです。 

> [!NOTE]
> アクション グループに関する移行範囲の完全なリストを確認するには、[こちらの](#release-notes)リリースノートをご確認ください。
 
## <a name="pre-requisites"></a>前提条件 
Softomotive 製品の製品のプロセス マイグレーター (プレビュー版) をインストールして期待通りに機能させるには、以下のものが必要です: 
-   最新の公開バージョンの Power Automate Desktop がインストールされていること。 
-   WinAutomation がインストールされていること (v6 およびそれ以降) 
-   有効な Power Automate 環境へのアクセス権限があること。  
 
 
## <a name="installing-process-migrator-for-softomotive-products-preview"></a>Softomotive 製品のプロセス マイグレーター (プレビュー版) をインストールする 
Softomotive 製品のプロセス マイグレーター (プレビュー版) の[設定ファイルのダウンロード](https://go.microsoft.com/fwlink/?linkid=2151571)が成功したら、実行します。  

> [!NOTE]
> - Softomotive 製品のプロセス マイグレーター (プレビュー版) のクリーンインストールを実行してください。  
> - アプリケーションの古いインストールをすべてアンインストールします。 
> - 以前のインストールので生成されたファイルをすべて削除します (空のインストールフォルダーなど) 
> - アプリケーションの最新版をインストールします。 
 
  ![Softomotive 製品のプロセス マイグレーター (プレビュー版) のインストール手順 1](media/migrator/migrator_1.png)

   ![Softomotive 製品のプロセス マイグレーター (プレビュー版) のインストール手順 2](media/migrator/migrator_2.png)

   ![Softomotive 製品のプロセス マイグレーター (プレビュー版) のインストール手順 3](media/migrator/migrator_3.png)

Softomotive 製品のプロセス マイグレーター (プレビュー版) を実行できます
 
## <a name="running-the-process-migrator-for-softomotive-products-preview"></a>Softomotive 製品のプロセス マイグレーター (プレビュー版) を実行する 
Softomotive 製品のプロセス マイグレーター (プレビュー版) をする際には、Power Automate アカウントの入力を求められます

   ![Softomotive 製品のプロセス マイグレーター (プレビュー版) のインストール手順 4](media/migrator/migrator_4.png)

> [!NOTE]
> 移行したプロセスをデスクトップ フローとして保存する目的で、環境へのアクセスに使用するアカウントへの接続を求められる場合があります。 

   ![Softomotive 製品のプロセス マイグレーター (プレビュー版) のインストール手順 6](media/migrator/migrator_6.png)
  
WinAutomation のバージョン 9 以降では、WinAutomation マスターキーの入力が求められます。 これは、暗号化されたプロセス内でのパスワード移行に必要です。 WinAutomation マスターキーの入力を省略した場合、上記のプロセスの移行処理は続行されますが、パスワードの値は移行されません。

   ![Softomotive 製品のプロセス マイグレーター (プレビュー版) のインストール手順 5](media/migrator/migrator_5.png)

> [!NOTE]
> マスター キーを入力すると、アプリケーションは、PC 上のすべての WinAutomation プロセスを取得し、移行の対象を選択します。  
この手順の後は、多少の遅延が発生する場合がありますが、アプリケーションはバックグラウンドで正常に動作しています。 

続いて、デスクトップ フローに Power Automate へと移行する WinAutomation プロセスと、これを格納する Power Automate 環境を選択します (既定の環境は事前に選択されています)。 次に、移行処理の開始を選択します
 
 ![Softomotive 製品のプロセス マイグレーター (プレビュー版) のインストール手順 7](media/migrator/migrator_7.png)

パスワードで保護された暗号化プロセスの移行を選択すると、暗号化するにあたって WinAutomation で使用したパスワードの入力を求められます。 必要なパスワードの入力をスキップするオプションを選択した場合は、上記のプロセスの移行は省略されます。

 ![Softomotive 製品のプロセス マイグレーター (プレビュー版) のインストール手順 7a](media/migrator/migrator_7a.png)

移行が開始されると、現在の移行状態の情報を表示するテキストボックスと進行状況バーが表示されます。

 ![Softomotive 製品のプロセス マイグレーター (プレビュー版) のインストール手順 8](media/migrator/migrator_8.png)

移行が完了すると、自動生成されたログファイルが表示され、移行されたプロセスが表示されます

 ![Softomotive 製品のプロセス マイグレーター (プレビュー版) のインストール手順 9](media/migrator/migrator_9.png)
 
ログは次の場所に出力されます C:\Users\{username}\AppData\Local\Microsoft\Softomotive 製品のプロセス マイグレーター\Logs

移行の完了後は、Power Automate にアクセスし、[マイフロー] と [デスクトップ フロー] オプションを選択します。 ここでは、移行されたプロセスを確認できます。

 ![Softomotive 製品のプロセス マイグレーター (プレビュー版) のインストール手順 11b](media/migrator/migrator_11b.png)
  
> [!NOTE]
> 移行されたデスクトップ フローが表示されるまでには、しばらく時間がかかります。 移行されたデスクトップ フローを Power Automate Desktop ですぐに表示するには、Power Automate Desktop からサインアウトして Power Automate アカウントに再度サインインするか、サービスを終了し、Power Automate Desktop を再実行して、Power Automate Desktop サービスを再起動してください。  

 ![Softomotive 製品のプロセス マイグレーター (プレビュー版) のインストール手順 11](media/migrator/migrator_11.png)

移行されたプロセス (現在はデスクトップ フロー) は、Power Automate Desktop を介して次の方法で変更できます。

 ![Softomotive 製品のプロセス マイグレーター (プレビュー版) のインストール手順 12](media/migrator/migrator_12.png)

> [!TIP]
> Softomotive 製品のプロセス マイグレーター (プレビュー版) は実行時に、暗号化されたプロセスに遭遇すると一時停止し、ユーザーのパスワード入力を待機します。 暗号化されているかどうかを基にプロセスをグループ化することをお勧めします。  
このようにし、暗号化されていないプロセスは監視なしで移行され、暗号化されたプロセスは必要なユーザーの同伴を必要とさせることができます。  

> [!NOTE]
> - 移行済みの WinAutomation プロセスは、デスクトップ フローとしてアップロードされる場合、次の形式となります:  
**WA_{WinAutomation} プロセスの名前 (WinAutomation内部のフォルダパス)**。 たとえば、**“MyProcesses/Examples/01 - Beginner”** というパスの配下の **05 - Copy File** WinAutomation というプロセスを移行する場合、処理後のデスクトップ フローの名前は、**WA_05 Copy File (Examples/01 - Beginner)** となります。
> - WinAutomation プロセスの移行時に生成されるデスクトップ フローの名前が、選択した環境内の既存のデスクトップ フローの名前と重複する場合、デスクトップ フローの名称が次の形式で生成されます、[WA_{WinAutomation} (X) プロセスの名前 (WinAutomation 内部のフォルダパス)]。(X)は連番で増加します。
たとえば、**“MyProcesses/Examples/01 - Beginner”** というパス配下の **05 - Copy File** WinAutomation というプロセスを移行する場合で、選択した環境のデスクトップ フローに同名のものが存在する場合、生成されるデスクトップ フローは次のように命名されます、  
**WA_05 Copy File (1) (Examples/01 - Beginner)**。

## <a name="release-notes"></a>リリース ノート

### <a name="non-migratable-actions"></a>移行不可能なアクション 

以下の WinAutomation アクションは、WA プロセスからそれぞれの UI フローには移行されません。  

- すべての Ancora アクション 
- CyberArk アクション 
- すべての CaptureFast アクション 
- 認知 > Google > ビジョン > 顔検出 
- 認知 > IBM > 視覚認識 > 顔検出 
- 認知 > マイクロソフト > 顔 > 顔検出 
- 認知 > マイクロソフト > 顔 > 類似の顔を探す 
- メッセージボックス > 通知の表示 
- メッセージ ボックス > カスタム ダイアログの表示 
- PDF アクション > OCR を使用して PDF からテキストを抽出する 
- すべての同期アクション (アクションのグループ) 
- すべての WinAutomation アクション (アクションのグループ) 

### <a name="partially-migrated-actions"></a>部分的に移行されたアクション 

以下のアクションは、WA プロセスからそれぞれのデスクトップ フローには移行されません。 ただし、それらのパラメーターのひとつ以上は、まったく転送されないか、同じ値で転送されません。 場合によっては、デザイナーにて手動のやり直しを適用することで処理できます。 

- Azure: Azure のセッションを作成します 
    - 移行不可能なプロパティ : ユーザー名、パスワード (オプションの認証タイプ : サービス プリンシパルあり) 
    - 欠落しているプロパティ : クライアントシークレット (オプションの認証タイプ : ユーザーあり) 
- Azure: Azure マネージド ディスクの作成 
    - 欠落しているプロパティ：ストレージ アカウント名 
- 解凍: ファイルの解凍 
    - 移行不可能なプロパティ : マスキングを含める、マスキングを除外する、サブフォルダーを含める 
- 認知 : 画像分類 IBM 
    - 欠落しているプロパティ : 場所、インスタンス ID 
- 認知 : トーン分析 IBM 
    - 移行不可能なプロパティ : ユーザー名、パスワード 
    - 欠落しているプロパティ : API キー、場所、インスタンス ID 
- 認知 : 翻訳 IBM 
    - 移行不可能なプロパティ : ユーザー名、パスワード 
    - 欠落しているプロパティ : API キー、場所、インスタンス ID、バージョン日付 
- 認知 : 言語の特定 IBM
    - 移行不可能なプロパティ : ユーザー名、パスワード 
    - 欠落しているプロパティ : API キー、場所、インスタンス ID、バージョン日付 
- 認知 : 言語の検出 マイクロソフト 
    - 移行不可能なプロパティ : 検出する言語の数 
- 暗号化 : テキストの暗号化  
    - 暗号化アルゴリズムが AES と同等ではなく、暗号モードがCBCと同等でない場合は、移行不可です 
- 暗号化 : テキストの復号  
    - 暗号化アルゴリズムが AES と同等ではなく、暗号モードがCBCと同等でない場合は、移行不可です 
- 暗号化 : ファイルからの暗号化  
    - 暗号化アルゴリズムが AES と同等ではなく、暗号モードがCBCと同等でない場合は、移行不可です 
- 暗号化 : ファイルへの復号化  
    - 暗号化アルゴリズムが AES と同等ではなく、暗号モードがCBCと同等でない場合は、移行不可です 
- 暗号化 : ハッシュテキスト  
    - 暗号化アルゴリズムが AES と同等ではなく、暗号モードがCBCと同等でない場合は、移行不可です 
- 暗号化 : ファイルからのハッシュ  
    - 暗号化アルゴリズムが AES と同等ではなく、暗号モードがCBCと同等でない場合は、移行不可です 
- 暗号化 : キーを使ったハッシュ テキスト  
    - 暗号化アルゴリズムが AES と同等ではなく、暗号モードがCBCと同等でない場合は、移行不可です 
- 暗号化 : ファイルからキーを使ってハッシュ化 
    - 暗号化アルゴリズムが AES と同等ではなく、暗号モードがCBCと同等でない場合は、移行不可です 
- マウスとキーボード : マウスを動かす 
    - 移行不可 : 「マウスを記録された位置に移動する」オプション 