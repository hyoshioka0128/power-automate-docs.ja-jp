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
ms.date: 06/30/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: dd3019c457316e58f86bda829bc2402b2be824a6
ms.sourcegitcommit: a51ebdce86c0c2399afa4ba36591fb3230eb82d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "3527300"
---
# <a name="use-softomotives-winautomation-with-ui-flows"></a>UI フローで Softomotive の WinAutomation を使用する


ここでは、UI フローで WinAutomation を使い始める前のヒントをいくつか紹介します。

1.  Power Automate 有人型 RPA ライセンス (有料または試用版) があると、[WinAutomation](https://www.winautomation.com/) にフル アクセスできます。 このドキュメントでは、WinAutomation のプロセスを Power Automateで動作させる方法を説明します。

1.   **プロセス**と呼ばれる、WinAutomation の自動化スクリプトが呼び出されます。 Power Automate では、自動化スクリプトは、 *フロー* または  *UI フロー*と呼ばれます。

1.  WinAutomation プロセスを作成する前に、 [コネクタの一覧](https://flow.microsoft.com/connectors/) を確認して、自動化するアプリケーションに既にコネクタがあるかどうかを確認します。 既に存在する場合は、UI フローではなくフローを作成することを検討してください。  [独自のコネクタを作成](https://docs.microsoft.com/connectors/custom-connectors/)することもできます。 一般に、API ベースのコネクタは、拡張性、信頼性、低コストの点でUI自動化よりも全体的に優れたエクスペリエンスを提供します。

1.  WinAutomation のライセンスを取得している既存のユーザーは [Softomotive のサポート ページ](https://support.softomotive.com/support/home)で参照を確認できます。

## <a name="prerequisites"></a>前提条件

WinAutomation を Power Automate の一環として実行するには、以下が必要となります :

1.  ご利用のマシンが  [UI フローの要件](https://docs.microsoft.com/power-automate/ui-flows/setup#prerequisites)を満たしていることを確認してください。

2.   [UI フロー](https://docs.microsoft.com/power-automate/ui-flows/setup)  アプリをインストールし、続いてにオンプレミスのデータ ゲートウェイをインストールして構成します。

>[!IMPORTANT]
>UI オートメーションを記録、テスト、または実行するには、最新バージョンの WinAutomation と UI フローが必要です。

## <a name="licensing"></a>ライセンス

UI フローと WinAutomation を使用するには、Power Automate の*有人型 RPA を使用したユーザーごとのプラン* が必要となります。 有料プランがない場合、Power Automate に移動して試用版を開始できます。

 
## <a name="install-winautomation"></a>WinAutomation をインストールする

1.   [WinAutomation インストーラー](https://aka.ms/rpaDesktopAutomationInstallPage)をダウンロードします。

1.   **WinAutomationSetup.exe** ファイルを実行します。 このファイルは、 **ダウンロード**  フォルダにある可能性があります。

1.  WinAutomation インストーラーの指示に従い、インストールを完了させます。 インストール中に、 **ライセンスの種類**  が  **Microsoft Power Automate** になっていることを確認してください。

## <a name="sign-in-to-winautomation"></a>WinAutomation へのサインイン

1.  インストールの完了後は、Windows のスタートメニューから WinAutomation コンソールを起動します。

1.  アプリケーションが起動し、ログインを求められます。 [Power Automate](https://flow.microsoft.com/) に使用するユーザー資格情報を入力してください。 有効なライセンスがない場合は、このエラーメッセージが表示されます。  [価格ページ](https://flow.microsoft.com/pricing/) にアクセスして、ライセンスの詳細情報の確認や、試用版ライセンスの取得ができます。

      ![ライセンス エラー](../media/create-processes/license-error.png)

      >[!IMPORTANT]
      > WinAutomationを使用した、 Power Automate の職場または学校のアカウントの使用を同意するにはテナント管理者権限が必要です。 そのためには、管理者が WinAutomation をインストールし、テナントの管理者アカウントでログインして、同意を与える必要があります。

      ![アクセス許可の要求](../media/create-processes/request-permissions.png)

1.  ログイン中にマスターキーを作成するように求められたら、マスターキーを作成します。

1.  サインインすると、WinAutomation コンソールにいくつかのサンプル プロセスが表示されます。 最初のステップとして、 **オプション** \> **ヘルプ** \> **はじめに** に移動した後、簡単なプロセスを作成するいくつかの例を実行するか、[ここ](https://docs.winautomation.com/en/building-a-simple-process.html)で情報を確認します。 詳細は、[WinAutomation 入門チュートリアル](https://www.winautomation.com/support/tutorials/)をご覧ください。

これで、独自の WinAutomation プロセスを作成して、ローカルでテストできます。

## <a name="run-winautomation-processes-from-power-automate"></a>Power Automate から WinAutomation プロセスを実行する

1.  WinAutomation でオートメーション プロセスを作成したら、有人または無人の UI フロー (デスクトップ) を介して Power Automate のフローから開始できます。 (**注意**: UI フローの作成と実行の詳細については、 [ここ](https://docs.microsoft.com/power-automate/ui-flows/create-desktop)をご覧ください)。

1.  新しいデスクトップ UI フローを作成します。 「アプリの記録」のデフォルトの最初のステップを削除します。

      ![レコード アプリ ステップの削除](../media/create-processes/delete-record-step.png)

1.  **新しいステップ** を選択して **WinAutomation** を選択し、**WinAutomation を実行する (プレビュー)** アクションを選択します。

      ![WinAutomation の実行の選択](../media/create-processes/select-run-winautomation.png)

1.  **WinAutomation を実行する (プレビュー)** カードで、実行する WinAutomation プロセスのプロセス パスとオプションのコマンドライン引数を入力します。

      ![WinAutomation カード](../media/create-processes/winautomation-card.png)

   >[!NOTE]
   >WinAutomation プロセスを作成してローカルに保存する必要があります。 *プロセス パス* は、左側のフォルダー ペインにある My Processes のベース ディレクトリからアクセスできる、プロセスの WinAutomation コンソールにある大文字と小文字が区別されるパスです。 プロセスをサブフォルダーに配置した場合は、その情報を ProcessPath に含める必要があります。 プロセス パスを引用符で囲まないでください。

   >[!TIP]
   >ターゲットの WinAutomation プロセスのパスで UI フロー入力と動的コンテンツを使用し、Power Automate フローで引数を使用できます。

1.  これで、UI フローを保存およびテストして、WinAutomation プロセスがどのように起動されるかを確認できます。

1.  その後、UI フローをフローに追加できます。 他の Power Automate コネクタとトリガーにも接続できます。

1.  次に、実行タイプとして *有人型* または *無人型* を選択できます。

    >[!TIP]
    >WinAutomation プロセスでは、 *コマンドライン引数を取得する* アクションを使用して、コマンドライン引数を取得できます。 引数は配列となっています。 これらのインデックスを使用して、各引数を参照します。

    >[!IMPORTANT]
    >コマンドライン引数を介してパスワードなどの機密テキストを渡さないでください。

    >[!IMPORTANT]
    >無人クラスターで UI フローを実行している場合は、ターゲット プロセスがコピーされるすべてのコンピューターに WinAutomation がインストールされていることを確認してください。 有人型と無人型 UI フローの詳細については、 [こちら](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow)を参照してください。

1.  フローを保存して実行すると、WinAutomation プロセスが起動することを確認できます。 WinAutomation プロセスの実行が完了すると、UI フローに戻ります。 Power Automate から実行結果を表示できます。 プロセスが失敗した場合は、エラー メッセージも表示されます。

    >[!TIP]
    >例外が発生した場合、最新の UI フローがインストールされていない可能性があります。 [最新の UI フロー](https://docs.microsoft.com/power-automate/ui-flows/upgrade)をインストールします。

1.  プロセスが失敗したときに WinAutomation がスクリーンショットをキャプチャするようにするには、次の手順を実行します。

1.  WinAutomation コンソールから、プロセスを右クリックして、[プロセスのプロパティの編集] を選択します。 [エラー処理] タブに移動し、[既定のオプションを上書きする] を選択します。 [スクリーンショットをログに追加] をクリックして保存します。 このとき、プロセスが失敗した場合、Power Automate UI フロー実行の詳細から実行時にキャプチャされたスクリーンショットを参照できます。  

    ![プロセスのプロパティ画面](../media/create-processes/process-properties.png)

現在、特定の WinAutomation ステップを使用して、プロセスからの結果と出力をクラウド共有のファイルに書き込むか、結果をメールで送信する必要があります。次に、Power Automate からコネクタを使用し、それらの結果にアクセスして使用できます。

## <a name="how-to-obtain-an-rpa-trial-license"></a>RPA 試用版ライセンスの取得方法

[Power Automate](https://flow.microsoft.com/) にログインし、次に **マイ フロー**の下の **UI フロー** タブを選択します。 試用版のダイアログが表示され、試用版を開始できます。

![試用を開始するか、ライセンスを購入する](../media/create-processes/trial-buy.png)

すでに有料プランをお持ちの場合、または以前に試用版を使用している場合は、試用版を新規利用することはできません。 この場合は、管理者に問い合わせを行い、Power Automate *有人型 RPA を使用したユーザーごとのプラン*試用版の購入または開始を依頼する必要があります。 これについては、Microsoft 365 管理センターで、 **課金** \> **サービスの購入**  にアクセスして、適切なプランを検索して購入してください。

![有人型 RPA を使用したユーザーごとのプラン](../media/create-processes/per-user-rpa.png)

プランの購入、または無料試用版の入手後は、プランをユーザーに割り当てる必要があります。

>[!IMPORTANT]
>ユーザーにプランを割り当てる際は、割り当てが有効化されるまでに数分かかる場合があります。

## <a name="troubleshooting-winautomation-licensing-issues"></a>WinAutomation のライセンスに関する問題のトラブルシューティング

WinAutomation の起動中にライセンス エラーが発生する場合は、ログインしているユーザーに有効な Power Automate RPA ライセンスがあることを確認してください。 これを確認するには、次の手順を実行します。

1.   [Power Automate](https://flow.microsoft.com/)  に移動してサインインします。

1.  左側のナビゲーション バーで [自分のフロー] を選択します。

1.  右側のページで UI フローを選択します。 正しいライセンスがあれば、そこで新しい UI フローを作成できることがわかるはずです。

1.  試用版を開始するか、管理者に依頼してください。

    >[!NOTE]
    >ユーザーがインターネットに接続しているときに WinAutomation を起動すると、ライセンスがキャッシュされます。

WinAutomation が保存したライセンス情報をリセットするには、次のファイルを削除できます: %localappdata%\\Softomotive\\WinAutomation\\msalcache.bin3。

## <a name="learn-more"></a>詳細はこちら

-    [WinAutomation の取得](https://flow.microsoft.com/blog/microsoft-acquires-softomotive-to-expand-low-code-robotic-process-automation-capabilities-in-microsoft-power-automate/)についてご覧ください。
-    [WinAutomation](https://support.softomotive.com/support/home) のサポートを受ける。
-    [ WinAutomation チュートリアル](https://www.winautomation.com/support/tutorials/)でスムーズに開始する。
-    [デスクトップ UI フローの作成](https://docs.microsoft.com/power-automate/ui-flows/create-desktop)を身につける。
-    [UI フローの実行](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow)方法を身につける。
-    [UI フローの管理](https://docs.microsoft.com/power-automate/ui-flows/manage)を身につける。
-    [オンプレミス ゲートウェイ](https://docs.microsoft.com/power-automate/gateway-reference#use-a-gateway)を深く理解する。
