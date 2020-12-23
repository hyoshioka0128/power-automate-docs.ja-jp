---
title: WinAutomation を使用してデスクトップ フローを作成する方法 | Microsoft Docs
description: WinAutomation を使用してデスクトップ フローを作成する方法について説明します。
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
ms.openlocfilehash: a05c12ae25cd6ceb572092433534323db903802c
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711662"
---
# <a name="use-softomotives-winautomation-with-desktop-flows"></a>デスクトップ フローで Softomotive の WinAutomation を使用する

>[!IMPORTANT]
>WinAutomation の進化については [Power Automate Desktop](introduction.md) のドキュメントを参照してください。

デスクトップ フローで WinAutomation を使用する前にこちらのヒントをご覧ください。

1.  Power Automate に付随する RPA ライセンス (有料版または試用版) を使用すると、[WinAutomation](https://www.winautomation.com/) への完全なアクセス権が得られます。 このドキュメントでは、WinAutomation プロセスを Power Automate で実行する方法を説明します。

1.  WinAutomation の自動化スクリプトは **プロセス** と呼ばれています。 Power Automate では、自動化スクリプトは、*クラウド* または *デスクトップ* フロー* と呼ばれています。

1.  WinAutomation プロセスを作成する前に、 [コネクタの一覧](https://flow.microsoft.com/connectors/)を確認し、自動化するアプリケーションにコネクタが存在することを確認してください。 存在する場合は、デスクトップ フローではなく、クラウド フローの作成を検討してください。 [独自のコネクタを作成](https://docs.microsoft.com/connectors/custom-connectors/)することもできます。 一般に API ベースのコネクタは、スケーラビリティ、信頼性、低コストの点で UI 自動化より優れたエクスペリエンスを提供します。

1.  既存の WinAutomation ライセンスが付与されているユーザーは、[Softomotive のサポート ページ](https://support.softomotive.com/support/home)で詳細を確認できます

## <a name="prerequisites"></a>前提条件

Power Automate の一環として WinAutomation を実行するには、次が必要となります :

1.  マシンが[デスクトップ フローの要件](https://docs.microsoft.com/power-automate/desktop-flows/setup#prerequisites)に適合することを確認してください。

2.  [デスクトップ フロー](https://docs.microsoft.com/power-automate/desktop-flows/setup)アプリをインストールし、オンプレミス データ ゲートウェイのインストールと構成を行います。

>[!IMPORTANT]
>UI 自動化の記録、テスト、実行をするには、WinAutomation と Power Automate Desktop の最新バージョンが必要です。

## <a name="licensing"></a>ライセンス

Power Automate Desktop と WinAutomation を使用するには、*有人RPAを使用しユーザープランごと* Power Automate が必要となります。 有料プランがない場合は、Power Automate で試用版アカウントを作成することができます。

 
## <a name="install-winautomation"></a>WinAutomation のインストール

1.  [WinAutomation のインストーラー](https://aka.ms/rpaDesktopAutomationInstallPage) をダウンロードします。

1.  **WinAutomationSetup.exe** ファイルを実行します。 このファイルは、**ダウンロードフォルダ** にある可能性があります。

1.  WinAutomation インストーラーに表示される指示に従ってインストールを完了します。 インストール中に、**ライセンスの種類** が **Microsoft Power Automate** になっていることを確認してください。

## <a name="sign-in-to-winautomation"></a>WinAutomation にサインインする

1.  インストールの完了後は、Windows スタートメニューから WinAutomation コンソールを起動します。

1.  アプリケーションが起動し、ログインを求められます。 [Power Automate](https://flow.microsoft.com/) に使用するユーザー資格情報を入力してください。 有効なライセンスがない場合は、このエラーメッセージが表示されます。 [価格ページ](https://flow.microsoft.com/pricing/)にアクセスして、ライセンスの詳細情報の確認や、試用版ライセンスの取得ができます。

      ![ライセンス エラー](../media/create-processes/license-error.png)

      >[!IMPORTANT]
      > Power Automate の職場または学校のアカウントで WinAutomation を使用するには、テナントの管理者の同意が必要となります。 そのためには、管理者がテナントの管理者アカウントでログインして WinAutomation をインストールし、同意をする必要があります。

      ![アクセス許可の要求](../media/create-processes/request-permissions.png)

1.  サインイン時にマスターキーの作成を求められる場合はマスターキーを作成します。

1.  ログインすると、いくつかのプロセス例とともに WinAutomation のコンソールが表示されます。 開始するには、 **オプション** \> **ヘルプ** \> **開始する** にアクセスし、[WinAutomation ドキュメント: 簡単なプロセスを構築する](https://docs.winautomation.com/en/building-a-simple-process.html)を参考に、簡単なプロセスやチェックアウト情報のサンプルを作成します。 [WinAutomation チュートリアル](https://www.winautomation.com/support/tutorials/)にて詳細を参照することができます。

これで、WinAutomation のプロセスを自分で作成し、ローカルでテストできるようになりました。

## <a name="run-winautomation-processes-from-power-automate"></a>Power Automate から WinAutomation のプロセスを実行する

1.  WinAutomation で自動プロセスの作成後は、Power Automate のクラウド フローから有人/無人モードで実行できます。 
    
    >[!TIP]
    >[デスクトップ フローの作成と実行](https://docs.microsoft.com/power-automate/desktop-flows/create-desktop)についての詳細。

1.  新しいデスクトップ フローを作成します。 「アプリの記録」のデフォルトの最初のステップを削除します。

      ![レコード アプリ ステップの削除](../media/create-processes/delete-record-step.png)

1.  **新規ステップ** を選択し、**WinAutomation** を選択し、**WinAutomation の実行** アクションを選択します。

      ![WinAutomation の実行を選択します。](../media/create-processes/select-run-winautomation.png)

1.  **WinAutomation の実行** カードで、プロセスのパスと、実行する WinAutomation プロセスに使用する任意のコマンドライン引数を入力します。

      ![WinAutomation カード](../media/create-processes/winautomation-card.png)

   >[!NOTE]
   >WinAutomation プロセスは、ローカルで作成して保存する必要があります。 *プロセスのパス* ではプロセス用の WinAutomation コンソールでは大文字と小文字を区別しています。左側の [フォルダー] ペインの [マイプロセス]のベースディレクトリから、[マイプロセス]　を選択します。 プロセスをサブフォルダーに配置した場合は、その情報を ProcessPath に含める必要があります。 プロセス パスを引用符で囲まないでください。

   >[!TIP]
   >デスクトップ フローの入力と、対象の WinAutomation プロセスのパスと Power Automate フローからの引数の動的コンテンツを使用することができます。

1.  以上で、Windows レコーダー (V1) のフローを保存してテストし、WinAutomation のプロセスがどのように起動するかを確認することができます。

1.  Windows レコーダー (V1) のフローをクラウド フローに追加することができます。 他の Power Automate コネクタとトリガーにも接続できます。

1.  実行タイプに *有人* や *無人* を選択できます。

    >[!TIP]
    >WinAutomation プロセスでは、*コマンドライン引数の取得* アクションを使用してコマンド ライン引数を取得できます。 引数は配列となっています。 これらのインデックスを使用して、各引数を参照します。

    >[!IMPORTANT]
    >コマンドライン引数を介してパスワードなどの機密テキストを渡さないでください。

    >[!IMPORTANT]
    >無人のクラスタでデスクトップ フローを実行している場合、ターゲット プロセスがコピーされるすべてのマシンに WinAutomation がインストールされていることを確認してください。 有人デスクトップ フローと無人デスクトップ フローの詳細については、[こちら](https://docs.microsoft.com/power-automate/desktop-flows/run-desktop-flow) を参照してください。

1.  フローを保存して実行すると、WinAutomation プロセスが起動するのを確認できます。 Windows レコーダー (V1) フローは、WinAutomation プロセスの実行が完了すると戻ります。 Power Automate から実行結果を表示できます。 プロセスが失敗した場合は、エラー メッセージも表示されます。

    >[!TIP]
    >例外が発生する場合は、最新の Power Automate Desktop がインストールされていない可能性があります。 [最新の Power Automate Desktop](https://docs.microsoft.com/power-automate/desktop-flows/upgrade)をインストールします。

1.  WinAutomation のプロセスが失敗したときにスクリーンショットをキャプチャするには、次手順に従ってください :

1.  WinAutomation コンソールで、プロセスを右クリックし、「プロセスのプロパティを編集する」を選択します。 [エラー処理] タブに移動し、[既定のオプションを上書きする] を選択します。 [スクリーンショットをログに追加] をクリックして保存します。 プロセスが失敗した場合、実行時にキャプチャしたスクリーン ショットを Windows レコーダー (V1) のフロー実行の詳細から確認できるようになりました。 プロセスのプロパティの詳細については、[WinAutomation ドキュメント : プロセスのプロパティ](https://docs.winautomation.com/en/process-properties.html) を参照してください。  

    ![プロセスのプロパティ画面](../media/create-processes/process-properties.png)

現在のところは、WinAutomation の特定のステップを使用して、プロセスの結果と出力をクラウド シェアのファイルに書き込むか、結果を電子メールで送信する必要があります。その後、Power Automate のコネクタを使用して、それらの結果にアクセスして使用することができます。

## <a name="how-to-obtain-an-rpa-trial-license"></a>RPA 試用版ライセンスの取得方法

[Power Automate](https://flow.microsoft.com/) にログインし、**マイ フロー** 配下の **デスクトップ フロー** を選択します。 試用版のダイアログが表示され、試用版を開始できます。

![試用を開始するか、ライセンスを購入する](../media/create-processes/trial-buy.png)

すでに有料プランをお持ちの場合、または以前に試用版を使用している場合は、試用版を新規利用することはできません。 この場合は、管理者に問い合わせを行い、 Power Automate  *有人型 RPA を使用したユーザーごとのプラン* 試用版の購入または開始を依頼する必要があります。 Microsoft 365 管理センターの **恪勤** \> **サービスの購入** にアクセスし、自分に合ったプランを探すして購入できます。

![有人型 RPA を使用したユーザーごとのプラン](../media/create-processes/per-user-rpa.png)

プランの購入、または無料試用版の入手後は、プランをユーザーに割り当てる必要があります。

>[!IMPORTANT]
>ユーザーにプランを割り当てる際は、割り当てが有効化されるまでに数分かかる場合があります。

## <a name="troubleshooting"></a>トラブルシューティング​​

### <a name="troubleshooting-winautomation-licensing-issues"></a>WinAutomation のライセンスに関する問題のトラブルシューティング

WinAutomation の起動中にライセンス エラーが発生した場合、ログインしているユーザーに有効な Power Automate RPAライセンスが付与されていることを確認してください。 これを確認するには、次の手順を実行します。

1.  [Power Automate](https://flow.microsoft.com/) に移動してサインインします。

1.  左のナビゲーション バーで、**マイ フロー** を選択します。

1.  ページの右側で、デスクトップ フローを選択します。 適切なライセンスがある場合は、新しいデスクトップ フローを作成することができます。

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

-   [WinAutomation の取得](https://flow.microsoft.com/blog/microsoft-acquires-softomotive-to-expand-low-code-robotic-process-automation-capabilities-in-microsoft-power-automate/)について参照する。
-   詳細については、[WinAutomation ドキュメント](https://docs.winautomation.com/index.html?lang=en) を参照してください。
-   詳細については、[WinAutomation アカデミー](https://academy.softomotive.com/)を参照してください。
-   [WinAutomation](https://support.softomotive.com/support/home) に移動してサポート情報にアクセスしてください。
-   [WinAutomation のチュートリアル](https://www.winautomation.com/support/tutorials/)を参照してスムーズに利用を開始する。
-   [Windows レコーダー (V1) フローの作成](https://docs.microsoft.com/power-automate/desktop-flows/create-desktop)について説明します。
-   [デスクトップ フローの実行](https://docs.microsoft.com/power-automate/desktop-flows/run-desktop-flow)方法について説明します。
-   [デスクトップ フローの管理](https://docs.microsoft.com/power-automate/desktop-flows/manage)方法について説明します。
-   [オンプレミス ゲートウェイ](https://docs.microsoft.com/power-automate/gateway-reference#use-a-gateway)を深く理解する。
