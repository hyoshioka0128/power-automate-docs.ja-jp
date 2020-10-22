---
title: WinAutomation で UI フローを作成する方法 | Microsoft Docs
description: WinAutomation で UI フローを作成する方法について説明します。
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
ms.date: 07/08/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d4df7419712b406004c029c3bea75295c0e2990e
ms.sourcegitcommit: c3eee935e8e8c64963817d2a692a38e8c90400b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "3835141"
---
# <a name="use-softomotives-winautomation-with-ui-flows"></a>UI flows で Softomotive の WinAutomation を使用する

>[!IMPORTANT]
>WinAutomation の新機能については [Power Automate Desktop (プレビュー)](./desktop/introduction.md) のドキュメントを参照してください。

UI フローで WinAutomation を使い始める前のヒントをいくつか紹介します。

1.  Power Automate に付随する RPA ライセンス (有料版または試用版) を使用すると、[WinAutomation](https://www.winautomation.com/) への完全なアクセス権が得られます。 このドキュメントでは、WinAutomation プロセスを Power Automate で実行する方法を説明します。

1.  WinAutomation における自動化スクリプト、 **プロセス**とは呼ばれます。 Power Automate では、自動化スクリプトは、 *フロー* または  *UI フロー*と呼ばれます。

1.  WinAutomation プロセスを作成する前に、 [コネクタの一覧](https://flow.microsoft.com/connectors/) を調べて、自動化を行うアプリケーションに既にコネクタがあるかどうかを確認します。 既に存在する場合は、UI フローではなくフローを作成することを検討してください。  [独自のコネクタを作成](https://docs.microsoft.com/connectors/custom-connectors/)することもできます。 一般に API ベースのコネクタは、スケーラビリティ、信頼性、低コストの点で UI 自動化より優れたエクスペリエンスを提供します。

1.  既存の WinAutomation ライセンスが付与されているユーザーは、 [Softomotive のサポート ページ](https://support.softomotive.com/support/home)で詳細を確認できます

## <a name="prerequisites"></a>前提条件

Power Automate の一環として WinAutomation を実行するには、次が必要となります :

1.  ご利用のマシンが  [UI フローの要件](https://docs.microsoft.com/power-automate/ui-flows/setup#prerequisites)を満たしていることを確認してください。

2.   [UI フロー](https://docs.microsoft.com/power-automate/ui-flows/setup)  アプリをインストールし、続いてにオンプレミスのデータ ゲートウェイをインストールして構成します。

>[!IMPORTANT]
>UI の自動化を記録、テスト、実行するには、WinAutomation と UI フローの最新バージョンが必用となります。

## <a name="licensing"></a>ライセンス

UI フローや WinAutomation を利用するためには、*RPA を利用したユーザーごとのプラン* に Power Automateが必要となります。 有料プランがない場合、Power Automate に移動して試用版を開始できます。

 
## <a name="install-winautomation"></a>WinAutomation のインストール

1.   [WinAutomation のインストーラー](https://aka.ms/rpaDesktopAutomationInstallPage) をダウンロードします。

1.   **WinAutomationSetup.exe** ファイルを実行します。 このファイルは、 **ダウンロード**  フォルダにある可能性があります。

1.  WinAutomation インストーラーに表示される指示に従ってインストールを完了します。 インストール中に、 **ライセンスの種類**  が  **Microsoft Power Automate** になっていることを確認してください。

## <a name="sign-in-to-winautomation"></a>WinAutomation にサインインする

1.  インストールの完了後は、Windows スタートメニューから WinAutomation コンソールを起動します。

1.  アプリケーションが起動し、ログインを求められます。 [Power Automate](https://flow.microsoft.com/) に使用するユーザー資格情報を入力してください。 有効なライセンスがない場合は、このエラーメッセージが表示されます。  [価格ページ](https://flow.microsoft.com/pricing/) にアクセスして、ライセンスの詳細情報の確認や、試用版ライセンスの取得ができます。

      ![ライセンス エラー](../media/create-processes/license-error.png)

      >[!IMPORTANT]
      > Power Automate の職場または学校のアカウントで WinAutomation を使用するには、テナントの管理者の同意が必要となります。 そのためには、管理者がテナントの管理者アカウントでログインして WinAutomation をインストールし、同意をする必要があります。

      ![アクセス許可の要求](../media/create-processes/request-permissions.png)

1.  サインイン時にマスターキーの作成を求められる場合はマスターキーを作成します。

1.  ログインすると、いくつかのプロセス例とともに WinAutomation のコンソールが表示されます。 使用を開始するには、 **オプション** \> **ヘルプ** \> **開始する**に移動し、続いて簡単なプロセスを作成するいくつかの例を実行するか、または[WinAutomation ドキュメント : 簡単なプロセスの構築](https://docs.winautomation.com/en/building-a-simple-process.html)に記載の情報を確認してください。 [WinAutomation チュートリアル](https://www.winautomation.com/support/tutorials/)にて詳細を参照することができます。

これで、WinAutomation のプロセスを自分で作成し、ローカルでテストできるようになりました。

## <a name="run-winautomation-processes-from-power-automate"></a>Power Automate から WinAutomation のプロセスを実行する

1.  WinAutomation で自動化のプロセスを作成後は、有人または無人の UIフロー (デスクトップ) を介して Power Automate のフローからこのプロセスを実行できます。 
    
    >[!TIP]
    >[UI フローの作成と実行](https://docs.microsoft.com/power-automate/ui-flows/create-desktop) に関する詳細情報。

1.  新しいデスクトップ UI フローを作成します。 「アプリの記録」のデフォルトの最初のステップを削除します。

      ![レコード アプリ ステップの削除](../media/create-processes/delete-record-step.png)

1.  **新しいステップ**を選択し、**WinAutomation**を選択します。続いて**WinAutomation (プレビュー) の実行**アクションを選択します。

      ![WinAutomation の実行を選択します。](../media/create-processes/select-run-winautomation.png)

1.  **WinAutomation の実行 (プレビュー)** カードにて、実行する WinAutomation プロセスのプロセス パスとオプションのコマンドライン引数を入力します。

      ![WinAutomation カード](../media/create-processes/winautomation-card.png)

   >[!NOTE]
   >WinAutomation プロセスは、ローカルで作成して保存する必要があります。 *プロセス パス* は、WinAutomation コンソールのプロセスで使用するパスで、大文字と小文字を区別します。これは左側のフォルダ ペインのマイ プロセスにあるベース ディレクトリに由来します。 プロセスをサブフォルダーに配置した場合は、その情報を ProcessPath に含める必要があります。 プロセス パスを引用符で囲まないでください。

   >[!TIP]
   >対象とする WinAutomation のプロセス パスの UI フロー入力と動的コンテンツ、Power Automate フローからの引数を使用することができます。

1.  以上で、UIフローを保存してテストし、WinAutomation プロセスがどのように起動するかを確認できます。

1.  その後、UI フローをフローに追加できます。 他の Power Automate コネクタとトリガーにも接続できます。

1.  次に、実行タイプとして *有人型* または *無人型* を選択できます。

    >[!TIP]
    >ご利用の WinAutomation プロセスでは、 *コマンドライン引数を取得する* アクションを使用してコマンドライン引数を取得することができます。 引数は配列となっています。 これらのインデックスを使用して、各引数を参照します。

    >[!IMPORTANT]
    >コマンドライン引数を介してパスワードなどの機密テキストを渡さないでください。

    >[!IMPORTANT]
    >無人のクラスターで UI フローを実行している場合は、ターゲットのプロセスがコピーされるすべてのマシンに WinAutomation がインストールされていることを確認してください。 有人型と無人型 UI フローの詳細については、 [こちら](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow)を参照してください。

1.  フローを保存して実行すると、WinAutomation プロセスが起動するのを確認できます。 WinAutomation プロセスの実行が完了すると、UI フローが返されます。 Power Automate から実行結果を表示できます。 プロセスが失敗した場合は、エラー メッセージも表示されます。

    >[!TIP]
    >例外が発生した場合、最新の UI フローがインストールされていない可能性があります。 [最新の UI フロー](https://docs.microsoft.com/power-automate/ui-flows/upgrade)をインストールします。

1.  WinAutomation のプロセスが失敗したときにスクリーンショットをキャプチャするには、次手順に従ってください :

1.  WinAutomation コンソールで、プロセスを右クリックし、「プロセスのプロパティを編集する」を選択します。 [エラー処理] タブに移動し、[既定のオプションを上書きする] を選択します。 [スクリーンショットをログに追加] をクリックして保存します。 このとき、プロセスが失敗した場合、Power Automate UI フロー実行の詳細から実行時にキャプチャされたスクリーンショットを参照できます。 プロセスのプロパティの詳細については、[WinAutomation ドキュメント : プロセスのプロパティ](https://docs.winautomation.com/en/process-properties.html) を参照してください。  

    ![プロセスのプロパティ画面](../media/create-processes/process-properties.png)

現在のところは、WinAutomation の特定のステップを使用して、プロセスの結果と出力をクラウド シェアのファイルに書き込むか、結果を電子メールで送信する必要があります。その後、Power Automate のコネクタを使用して、それらの結果にアクセスして使用することができます。

## <a name="how-to-obtain-an-rpa-trial-license"></a>RPA 試用版ライセンスの取得方法

[Power Automate](https://flow.microsoft.com/) にログインし、次に **マイ フロー**の下の **UI フロー** タブを選択します。 試用版のダイアログが表示され、試用版を開始できます。

![試用を開始するか、ライセンスを購入する](../media/create-processes/trial-buy.png)

すでに有料プランをお持ちの場合、または以前に試用版を使用している場合は、試用版を新規利用することはできません。 この場合は、管理者に問い合わせを行い、Power Automate *有人型 RPA を使用したユーザーごとのプラン*試用版の購入または開始を依頼する必要があります。 これについては、Microsoft 365 管理センターで、 **課金** \> **サービスの購入**  にアクセスして、適切なプランを検索して購入してください。

![有人型 RPA を使用したユーザーごとのプラン](../media/create-processes/per-user-rpa.png)

プランの購入、または無料試用版の入手後は、プランをユーザーに割り当てる必要があります。

>[!IMPORTANT]
>ユーザーにプランを割り当てる際は、割り当てが有効化されるまでに数分かかる場合があります。

## <a name="troubleshooting"></a>トラブルシューティング​​

### <a name="troubleshooting-winautomation-licensing-issues"></a>WinAutomation のライセンスに関する問題のトラブルシューティング

WinAutomation の起動中にライセンス エラーが発生した場合、ログインしているユーザーに有効な Power Automate RPAライセンスが付与されていることを確認してください。 これを確認するには、次の手順を実行します。

1.   [Power Automate](https://flow.microsoft.com/)  に移動してサインインします。

1.  左側のナビゲーション バーで [自分のフロー] を選択します。

1.  右側のページで UI フローを選択します。 正しいライセンスがあれば、そこで新しい UI フローを作成できることがわかるはずです。

1.  試用版を開始するか、管理者に依頼してください。

    >[!NOTE]
    >インターネットに接続されている場合は、ユーザーが WinAutomation を起動する際にライセンスがキャッシュされます。

WinAutomation が保存したライセンス情報をリセットするには、次のファイルを削除します : %localappdata%\\Softomotive\\WinAutomation\\msalcache.bin3

### <a name="troubleshooting-other-issues"></a>その他の問題のトラブルシューティング

発生する可能性がある問題のトラブルシューティングについては、このセクションのリンクをご利用ください。

WinAutomation
- [インストール エラー](https://support.softomotive.com/support/solutions/folders/35000220522)
- [コンソール](https://support.softomotive.com/support/solutions/folders/35000220523)
- [プロセス エラー](https://support.softomotive.com/support/solutions/folders/35000220524)
- [Web オートメーション](https://support.softomotive.com/support/solutions/folders/35000220531)
- [UI オートメーション](https://support.softomotive.com/support/solutions/folders/35000220532)
- [Excel の自動化](https://support.softomotive.com/support/solutions/folders/35000220533)
- [画像の処理](https://support.softomotive.com/support/solutions/folders/35000220534)
- [メールの自動化](https://support.softomotive.com/support/solutions/folders/35000220535)
- [データベース](https://support.softomotive.com/support/solutions/folders/35000220536)

ProcessRobot
- [コントロール デスク](https://support.softomotive.com/support/solutions/folders/35000220525)
- [プロセス スタジオ](https://support.softomotive.com/support/solutions/folders/35000220526)
- [ProcessRobot データベース](https://support.softomotive.com/support/solutions/folders/35000220528)
- [ロボット エラー](https://support.softomotive.com/support/solutions/folders/35000220529)
- [プロセス エラー](https://support.softomotive.com/support/solutions/folders/35000220530)
- [Web オートメーション](https://support.softomotive.com/support/solutions/folders/35000220531)
- [UI オートメーション](https://support.softomotive.com/support/solutions/folders/35000220532)
- [Excel の自動化](https://support.softomotive.com/support/solutions/folders/35000220533)
- [画像の処理](https://support.softomotive.com/support/solutions/folders/35000220534)
- [メールの自動化](https://support.softomotive.com/support/solutions/folders/35000220535)
- [データベース](https://support.softomotive.com/support/solutions/folders/35000220536)


## <a name="best-practices-for-creating-processes"></a>プロセス作成のベスト プラクティス

プロセス作成時に考慮すべきヒントを以下にいくつか示します。


WinAutomation

- [トリガー](https://support.softomotive.com/support/solutions/folders/35000220511)
- [Web オートメーション](https://support.softomotive.com/support/solutions/folders/35000220512)
- [UI 自動化](https://support.softomotive.com/support/solutions/folders/35000220513)
- [Excel の自動化](https://support.softomotive.com/support/solutions/folders/35000220514)
- [テキスト操作](https://support.softomotive.com/support/solutions/folders/35000220515)
- [画像の処理](https://support.softomotive.com/support/solutions/folders/35000220516)
- [メールの自動化](https://support.softomotive.com/support/solutions/folders/35000220517)
- [データベース](https://support.softomotive.com/support/solutions/folders/35000220518)
- [数学演算](https://support.softomotive.com/support/solutions/folders/35000220519)
- [変数](https://support.softomotive.com/support/solutions/folders/35000220520)

ProcessRobot

- [コントロール デスク](https://support.softomotive.com/support/solutions/folders/35000220537)
- [ダッシュボード](https://support.softomotive.com/support/solutions/folders/35000220538)
- [トリガー](https://support.softomotive.com/support/solutions/folders/35000220521)
- [Web オートメーション](https://support.softomotive.com/support/solutions/folders/35000220512)
- [UI 自動化](https://support.softomotive.com/support/solutions/folders/35000220513)
- [Excel の自動化](https://support.softomotive.com/support/solutions/folders/35000220514)
- [テキスト操作](https://support.softomotive.com/support/solutions/folders/35000220515)
- [画像の処理](https://support.softomotive.com/support/solutions/folders/35000220516)
- [メールの自動化](https://support.softomotive.com/support/solutions/folders/35000220517)
- [データベース](https://support.softomotive.com/support/solutions/folders/35000220518)
- [数学演算](https://support.softomotive.com/support/solutions/folders/35000220519)
- [変数](https://support.softomotive.com/support/solutions/folders/35000220520)


## <a name="learn-more"></a>詳細情報を見る

-    [WinAutomation の取得](https://flow.microsoft.com/blog/microsoft-acquires-softomotive-to-expand-low-code-robotic-process-automation-capabilities-in-microsoft-power-automate/)について参照する。
-   詳細については、[WinAutomation ドキュメント](https://docs.winautomation.com/index.html?lang=en) を参照してください。
-   詳細については、[WinAutomation アカデミー](https://academy.softomotive.com/)を参照してください。
-    [WinAutomation](https://support.softomotive.com/support/home) に移動してサポート情報にアクセスしてください。
-    [WinAutomation のチュートリアル](https://www.winautomation.com/support/tutorials/)を参照してスムーズに利用を開始する。
-    [デスクトップ UI フローの作成](https://docs.microsoft.com/power-automate/ui-flows/create-desktop)を身につける。
-    [UI フローの実行](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow)方法を身につける。
-    [UI フローの管理](https://docs.microsoft.com/power-automate/ui-flows/manage)を身につける。
-    [オンプレミス ゲートウェイ](https://docs.microsoft.com/power-automate/gateway-reference#use-a-gateway)を深く理解する。
