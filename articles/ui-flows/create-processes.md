---
title: WinAutomation で UI フローを作成する方法を学ぶ | Microsoftドキュメント
description: WinAutomation で UI フローを作成する方法を学ぶ。
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
ms.date: 05/19/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1b9bd3a1f79885d17406e882b4432eff930d342c
ms.sourcegitcommit: 549224cf13fc761f473c880e8d0d8f2741cc7b0f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "3435042"
---
# <a name="use-softomotives-winautomation-with-ui-flows"></a>UI フローで Softomotive の WinAutomation を使用する

ご利用の有人型 Power Automate RPAライセンス (有料版または試用版) は、Softomotive の [WinAutomation](https://www.winautomation.com/) にフルアクセスできるようになりました。 このドキュメントでは、WinAutomation のプロセスを  Power Automateで動作させる方法を説明します。

既存の WinAutomation ユーザーは、[Softomotive のサポートページ](https://support.softomotive.com/support/home)で詳細情報をご確認いただきます

## <a name="overview-for-existing-ui-flows-users"></a>既存の UI フローユーザーの概要

[ダウンロード](https://aka.ms/rpaDesktopAutomationInstallPage)およびインストール後、Power Automate の職場/学校アカウントで WinAutomation にサインインします。 WinAutomation でプロセスを作成した後は、UI フローを使用して Power Automate からプロセスを有人または無人で実行できます。 これを行うには、次の手順を実行します。

1. UIフロー デスクトップの記録を開始します。
1. コマンド プロンプトを開きます。
1. コマンドを入力してプロセスをトリガーします。
   - 入力変数が必要ないプロセスの場合は、*"%programfiles%\WinAutomation\WinAutomationController.exe" /start "/My Robots/MyAutomationName"* と入力します。
   - 入力変数が必要なプロセスの場合は、プロセス名の後にそれらを入力します。 たとえば、*MyAutomationName* という名前のプロセスに、*変数 A* と*変数 B*の入力が必要な場合は、*"%programfiles%\WinAutomation\WinAutomationController.exe" /start "/My Robots/MyAutomationName" 変数 A 変数 B* のように入力します。

   >[!TIP] 
   >UI フローの入力と動的なコンテンツを使用して、Power Automate からターゲットの WinAutomationプロセスを変更します。

1. コマンド プロンプトでエンター キーを押下し、続いて UI フローの記録を停止します。 
   UI フローは、WinAutomation プロセスの開始時に必要なすべての情報を取得します。
   
1. UI フローをフローに追加後は、実行タイプに*有人*または*無人*を選択します。

   >[!TIP] 
   >WinAutomation プロセスでは、*コマンドライン引数を取得する*アクションを使用して、コマンドラインの引数を取得すします。 引数は配列となっています。 これらのインデックスを使用して、各引数を参照します。
   
## <a name="set-up-winautomation"></a>WinAutomation の設定

>[!TIP]
>**プロセス**と呼ばれる、WinAutomation の自動化スクリプトが呼び出されます。 Power Automate では、自動化スクリプトは、*flows* または *UI flows*と呼ばれます。

WinAutomation プロセスを作成する前に、[コネクタの一覧](https://flow.microsoft.com/connectors/)を確認して、自動化するアプリケーションに既にコネクタがあるかどうかを確認します。 既に存在する場合は、UI フローではなくフローを作成することを検討してください。 [独自のコネクタを作成](https://docs.microsoft.com/connectors/custom-connectors/)することもできます。 一般に、API ベースのコネクタは、拡張性、信頼性、低コストの点でUI自動化よりも全体的に優れたエクスペリエンスを提供します。

>[!TIP]
>Power Automate から WinAutomation スクリプトを実行するには、まず UI フローからスクリプトの再生を開始する必要があります。

## <a name="prerequisites"></a>前提条件 

WinAutomation を Power Automate の一環として実行するには、以下が必要となります :
1. ご利用のマシンが [UI フローの要件](https://docs.microsoft.com/power-automate/ui-flows/setup#prerequisites)を満たしていることを確認してください。
1. [UI フロー](https://docs.microsoft.com/power-automate/ui-flows/setup)アプリをインストールし、続いてにオンプレミスのデータ ゲートウェイをインストールして構成します。

## <a name="licensing"></a>ライセンス

UI フローと WinAutomation を使用するには、*有人型 RPA を使用したユーザーごとのプラン*が必要となります。 有料版のプランに登録していない場合は、Power Automate にアクセスして**自分のフロー**配下の**UI フロー**タブを選択して、*有人型 RPA を使用したユーザーごとのプラン* の試用版を開始することができます。 試用版のダイアログが表示され、試用版を開始できます。

![試用を開始するか、ライセンスを購入する](../media/create-processes/trial.png)

すでに有料プランをお持ちの場合、または以前に試用版を使用している場合は、試用版を新規利用することはできません。 この場合は、管理者に問い合わせを行い、 Power Automate  *有人型 RPA を使用したユーザーごとのプラン* 試用版の購入または開始を依頼する必要があります。 これについては、Microsoft 365 管理センターで、**課金** > **サービスの購入** にアクセスして、適切なプランを検索して購入してください。

![有人型 RPA を使用したユーザーごとのプラン](../media/create-processes/license-plan.png)

プランの購入、または無料試用版の入手後は、プランをユーザーに割り当てる必要があります。 

>[!NOTE]
>ユーザーにプランを割り当てる際は、割り当てが有効化されるまでに数分かかる場合があります。

>[!WARNING]
>UI の自動化を記録、テスト、実行するには、各コンポーネントの最新バージョンが必要です。

## <a name="install-winautomation"></a>WinAutomation をインストールする

マシンに UI フローをインストール後は、以下の手順に従って、WinAutomation をインストールし、デスクトップの自動化スクリプトを記録、編集、テストできます。

1.  [WinAutomation インストーラー](https://aka.ms/rpaDesktopAutomationInstallPage)をダウンロードします。

1.  **WinAutomationSetup.exe** ファイルを開きます。 このファイルは、**ダウンロードフォルダ**にある可能性があります。

1.  WinAutomation インストーラーの指示に従い、インストールを完了させます。 インストール中に、**ライセンスの種類**が**Microsoft Power Automate** になっていることを確認してください。

## <a name="sign-in-to-winautomation"></a>WinAutomation へのサインイン 

インストールの完了後は、Windows のスタートメニューから WinAutomation コンソールを起動します。 アプリケーションが起動し、ログインを求められます。 Power Automate の *有人型 RPA を使用したユーザーごとのプラン*のライセンスをすでに持っている場合、または Power Automate の試用版ライセンスを持っている場合は、[Power Automate](https://flow.microsoft.com) で使用しているユーザーの資格情報を入力してください。 [価格ページ](https://flow.microsoft.com/pricing/)にアクセスして、ライセンスの詳細情報の確認や、試用版ライセンスの取得ができます。

有効なライセンスがない場合は、このエラーメッセージが表示されます。

![ライセンス エラー](../media/create-processes/license-error.png)


>[!WARNING]
>WinAutomationを使用した、 Power Automate の職場または学校のアカウントの使用を同意するにはテナント管理者権限が必要です。 そのためには、WinAutomation をインストールし、テナントの管理者アカウントでログインして、同意を与えることができます。

![アクセス許可の要求](../media/create-processes/permissions-request.png)

サインインすると、WinAutomation コンソールにいくつかのサンプル プロセスが表示されます。 使用を開始するには、**オプション** > **ヘルプ** > **開始する** にアクセスし、続いて、簡単なプロセスを作成するいくつかの例を参照してください。 さらに、[WinAutomation の入門チュートリアル](https://www.winautomation.com/support/tutorials/)が利用可能となっています。

## <a name="run-winautomation-processes-from-power-automate"></a>Power Automate から WinAutomation プロセスを実行する

WinAutomation で自動化スクリプトを定義すると、Power Automate のフローから実行できます。これには、コマンド プロンプトでアプリケーションを起動するための UI フローのサポートを使用します。 UI フローの作成とテストの詳細については、[こちら](https://docs.microsoft.com/power-automate/ui-flows/create-desktop)を参照してください。

### <a name="running-winautomation-processes"></a>WinAutomation プロセスを実行する 

コンソール環境を使用せずに WinAutomation プロセスを実行するには、WinAutomationController.EXE コマンドを使用します。 このプロセスは WinAutomation のインストールフォルダーに配置されており、Windows の**コマンド プロンプト** で起動できます。 多くの便利なパラメータがありますが、オートメーションの起動には、指定したプロセスを開始する「/ start」フラグを使用します。 コマンドの例は次のとおりです : **WinAutomationController /start processPath**

*processPath* は、プロセスが使用する WinAutomation Console のパスであり、左側のフォルダー ウィンドウの [自分のプロセス] ベースディレクトリに由来します。 プロセスをサブフォルダーに配置した場合は、その情報を processPath に含める必要があります。 processPath にスペースが含まれている場合は、二重引用符で囲む必要があります (例 : WinAutomationController /start "/My Processes/../../processName")。

### <a name="launching-winautomation-processes-from-ui-flows"></a>UI フローから WinAutomation プロセスを起動する

上記の WinAutomation プロセスを実行するコマンドを確認できたら、UI フローから直接このコマンドを呼び出すことができます。 実行手順:

1.  空白の UI フローがある場合は、 **起動レコーダー** をクリックして、UI フローの記録エクスペリエンスに新たなステップを追加します。 UI フローに定義済みのステップがすでにある場合は、**新しいステップ**をクリックし、続いて**アプリの記憶**を選択してレコーダーを起動します。 記録エクスペリエンスに関する詳細情報は、[こちらを](https://docs.microsoft.com/power-automate/ui-flows/create-desktop)参照してください。

1.  起動したレコーダーで**記録**を選択します。

1.  Windows で、**コマンド プロンプト** を起動します。

1.  前述の手順でに作成した WinAutomationController コマンドを入力します (例 : WinAutomationController /start "/My Processes/../../process")。

1.  レコーダーで **完了** を選択します。

レコーダーが、UI フローに新しいステップを追加し、WinAutomationController の起動が含まれます。


>[!TIP]
>UI フローは、有人型と無人型の両方において、自動化モードで実行できます。 どちらの場合であっても WinAutomationController を実行できます。 無人型のクラスターで UI フローを実行している場合は、上記で指定した WinAutomationController コマンドがクラスター内のすべてのマシンで実行されることを確認してください。 有人型と無人型 UI フローの詳細については、[こちら](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow)を参照してください。

## <a name="waiting-for-a-winautomation-process-to-complete-in-ui-flows"></a>UI フローで WinAutomation プロセスの完了を待機する

既定では、WinAutomationController.exe はプロセスをバックグラウンドで実行します。 WinAutomation プロセスの自動化が完了するまで UI フローを待機させる場合は、**メッセージの表示** コマンドを使用して WinAutomation プロセスの最後に情報のメッセージ ボックスを表示し、UI フローで当該メッセージ ボックスのボタンをクリックして待機させることができます。 実行手順:

1.  WinAutomation プロセスの最後のステップに、「メッセージの表示」コマンドを追加します。 これを行うには、左側のアクション パネルをフィルター処理して[メッセージの表示]を見つけ、このコマンドをプロセス スクリプト エディターにドラッグ アンド ドロップします。 わかりやすいタイトルと説明を付け、[OK]ボタンが表示されている既定のボタン選択をそのままにしておきます。
1.  メッセージ ボックスが表示されるまで、WinAutomation プロセスを実行します。 
1.  新しい UI フローの記録を追加し、[メッセージの表示] ボックスのタイトルをクリックして、[OK] をクリックします。 
1.  [完了] をクリックして記録を停止します。 以上で、UI フローのスクリプトに、ダイアログ ボックスをクリックしてメッセージボックスを破棄する、新たなアクションが追加されたことがわかります。
1.  最後に、WinAutomation が完了するまでに一定の時間を与えるよう、UI フローに指示する必要があります。 これを行うには、WinAutomationController.exe コマンドを起動する前の Send Keys コマンドを展開して拡張オプションを表示し、Wait After プロパティを設定して、WinAutomation プロセスのスクリプトが実行されるまでの最大限の時間待機させます。


## <a name="uninstall-winautomation"></a>WinAutomation をアンインストールする

1.  **スタート** メニュー \> **設定** \> **アプリ**を開きます。

1.  **WinAutomation** を検索して選択します。

1.  **アンインストール** を選択します。

## <a name="troubleshooting-winautomation-licensing-issues"></a>WinAutomation のライセンスに関する問題のトラブルシューティング

WinAutomation の起動中にライセンス エラーが発生する場合は、ログインしているユーザーが UI フローの有効なライセンスを持っていることを確認してください。 実行する操作: 

1.  [Power Automate](https://flow.microsoft.com) に移動してサインインします。
1.  左側のナビゲーション バーで [自分のフロー] を選択します。
1.  右側のページで UI フローを選択します。 試用版を開始する、または管理者に試用版を利用できるように依頼してください。

WinAutomation が保存したライセンス情報をリセットするには、次のファイルを削除できます : %localappdata%\Softomotive\WinAutomation\msalcache.bin3

>[!NOTE]
>このライセンスは、ユーザーがインターネットに接続しているときに WinAutomation を起動するとキャッシュされます。 


## <a name="learn-more"></a>詳細はこちら

- [WinAutomation の取得](https://flow.microsoft.com/blog/microsoft-acquires-softomotive-to-expand-low-code-robotic-process-automation-capabilities-in-microsoft-power-automate/)について
- [WinAutomation](https://support.softomotive.com/support/home) のサポートを受ける。
- [ WinAutomation チュートリアル](https://www.winautomation.com/support/tutorials/)でスムーズに開始する。
- [デスクトップ UI フローの作成](https://docs.microsoft.com/power-automate/ui-flows/create-desktop)を身につける。
- [UI フローの実行](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow)方法を身につける。
- [UI フローの管理](https://docs.microsoft.com/power-automate/ui-flows/manage)を身につける。
- [オンプレミス ゲートウェイ](https://docs.microsoft.com/power-automate/gateway-reference#use-a-gateway)を深く理解する。
