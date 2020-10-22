---
title: デバイスで UI flows と Power Automate Desktop (プレビュー) を設定する | Microsoft Docs
description: デバイスで UI flows と Power Automate Desktop (プレビュー) を設定します。
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
ms.date: 09/22/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ba01a6db7688180520962beafe7e41cd1065b672
ms.sourcegitcommit: 1ffc5ec190e8f0d6105bdf61508bd6121bc43959
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830859"
---
# <a name="set-up-ui-flows-and-power-automate-desktop-preview"></a>UI flows と Power Automate Desktop (プレビュー) を設定する

自分のデバイスを使用して UI フローを作成する前に、ここで説明する要件を満たすことを確認する必要があります。

> [!TIP]
> UI フローを作成する前に [コネクタの一覧](https://flow.microsoft.com/connectors/) を確認して、自動化するアプリケーションに対する既存のコネクタがあるかどうかを確認してください。 既に存在する場合は、UI フローではなくフローを作成することを検討してください。 [独自のコネクタ](https://docs.microsoft.com/connectors/custom-connectors/) を作成することもできます。

## <a name="prerequisites"></a>前提条件

- Power Automate アテンド型 RPA の [有償版](https://flow.microsoft.com/pricing/) または [試用版](https://flow.microsoft.com/manage/) のライセンス。

- 管理者特権と Power Automate で Windows デバイスにサインインするための職場または学校アカウント。

- Windows 10 Pro、Windows 10 Entreprise、Windows Server 2016、Windows Server 2019 を実行するデバイス。

- [Microsoft Edge](https://www.microsoft.com/edge/) (バージョン 80 以降)   または Google Chrome ブラウザー。

- [Common Data Service データベース](https://docs.microsoft.com/power-platform/admin/create-database) のある [環境](https://docs.microsoft.com/power-platform/admin/environments-overview)。

- サポートするキーボードが接続されていること。

>[!IMPORTANT]
>UI フローを記録、テスト、実行するには、各コンポーネントの最新バージョンが必要です。

## <a name="install-ui-flows-and-power-automate-desktop-preview-on-your-device"></a>デバイスに UI フローと Power Automate Desktop (プレビュー) をインストールします

インストーラーは、自動化の記録、編集、テストに必要なコンポーネントをすべて含みます。 

UI flows アプリをインストールする場合は、次の手順に従います。

1. [UI flows のインストーラーをダウンロードします](https://go.microsoft.com/fwlink/?linkid=2102613)。
1. **Setup.Microsoft.PowerAutomate.UIflow.exe** ファイルを開きます。 

   このファイルは、前の手順でダウンロードした後、**ダウンロード** フォルダーにあるはずです。

1. **UI flows セットアップ** インストーラーの指示に従い、インストールを完了させます。
1. インストーラーが起動したら UI flows、Power Automate Desktop (プレビュー)、またはその両方のインストールを選択します。 
1. インストールを完了するために各機能を選択します。 

>[!IMPORTANT]
>UI flows のパッケージは、Webdriver コンポーネントと UI flows ブラウザー拡張機能をインストールします。 デスクトップで UI フローを記録、テスト、実行するために、これら両方が必要です。
>Power Automate Desktop (プレビュー) パッケージは、Power Automate Desktop アプリ、サードパーティ コンポーネント、ブラウザー拡張機能をインストールします。

![インストール オプションの画像](https://user-images.githubusercontent.com/48315710/92633908-c546e380-f2d3-11ea-8976-6a7609eb70f8.png)

### <a name="set-data-collection-options"></a>データ収集オプションを設定する

使用状況データを Microsoft に送信しない場合は、インストール中に既定の設定を変更できます。 これを行うには **UI flows を改善するために使用状況データの収集を Microsoft に許可する** をオフにします。

## <a name="activate-the-ui-flows-and-power-automate-desktop-preview-browser-extension"></a>UI flows と Power Automate Desktop (プレビュー) ブラウザ拡張機能をアクティブ化する 

インストールが完了したら、使用するブラウザーで UI flows と Power Automate Desktop (プレビュー) の拡張機能が有効なことを確認します。

![インストール成功の画像](https://user-images.githubusercontent.com/48315710/92635143-a5b0ba80-f2d5-11ea-96ec-4672d84d13b3.png)

1. インストーラーに表示されるリンクの 1 つを選択します。 たとえば Microsoft Edge で UI フローを使用する場合は、**Microsoft Edge** リンクを選択します。

   ブラウザのストアが拡張機能の公式ページに直接開きます。

1. 拡張機能がインストール済みであることを確認します。 インストールされていない場合は、次の手順に従います。

#### <a name="microsoft-edge"></a>Microsoft Edge: 
- **取得** を選択し、表示されるプロンプトで **拡張機能を追加する** を選択します。 
- ページ上部に *この拡張機能は Microsoft Edge でオフになっています* というメッセージが表示される場合は、**拡張機能をオンにする** を選択します。

#### <a name="google-chrome"></a>Google Chrome: 
- **Chrome に追加する** を選択し、表示されるプロンプトで **拡張機能の有効化** を選択します。 
- ページ上部に *この項目は Chrome で無効になっています* とメッセージが表示される場合は、**この項目を有効化する** を選択します。

> [!TIP]
> ブラウザーで拡張機能を有効化できない場合は、以下をご確認ください。
> - [Microsoft Edge](https://www.microsoft.com/edge/) (バージョン 80 以降) または Google Chrome を使用します。 Firefox は Power Automate Desktop 拡張機能でのみサポートされます。
> - 拡張機能が表示されない場合は、[UI flows インストーラー](https://go.microsoft.com/fwlink/?linkid=2102613) を使用して再インストールできます。


## <a name="install-selenium-ide-to-automate-web-applications-with-ui-flows"></a>Selenium IDE をインストールして UI フロー で Web アプリケーションを自動化する

Selenium IDE は Web サイト上の人間の操作を記録して再生できるオープンソース ツールです。

UI フロー を使用すると、Power Automate から Selenium IDE スクリプトを実行し、Common Data Service に安全に (適切な IT ガバナンスで) 保存することができます。

Selenium IDE をインストールするには、次の手順に従います。

1. [Microsoft Edge](https://www.microsoft.com/edge/) (バージョン 80 以降) または Google Chrome の Selenium IDE を [ダウンロードしてインストールします](https://go.microsoft.com/fwlink/?linkid=2107665)。

1. Microsoft Edge (バージョン 80 以降) で、**他のストアからの拡張機能を許可する** を選択し、**Chrome に追加** を選択します。

## <a name="install-the-on-premises-data-gateway"></a>オンプレミス データ ゲートウェイのインストール

[イベント、スケジュール、ボタン フロー](../getting-started.md#types-of-flows) から UI フローをトリガーするゲートウェイが必要です。 リモート デバイス上。

>[!TIP]
>デバイスでフローを作成、編集、テストするだけの場合は、ゲートウェイは必要ありません。

必要に応じて [オンプレミス データ ゲートウェイをインストールします](https://docs.microsoft.com/data-integration/gateway/service-gateway-install)。


>[!IMPORTANT]
>ゲートウェイをインストールすると、既定で、Power Automate が使用するリージョンになります。


## <a name="setup-ui-flows-connections-and-machine-credentials"></a>UI フロー接続とマシン資格情報を設定する

1. [Power Automate](https://powerautomate.microsoft.com) にサインインする。
1. 画面左側の **データ** を展開します。
1. **接続**を選択します。

   ![[接続] タブのスクリーンショット](../media/ui-flows-setup/connections-tab.png)

1. 新規接続 を選択します。

   ![接続のスクリーンショット](../media/ui-flows-setup/new-connection.png)

1. *UI flow* を検索して **UI flows** を選択します。

   ![検索ボックスのスクリーンショット](../media/ui-flows-setup/search-ui-flow.png)

1. ゲートウェイ情報とデバイスの資格情報を指定します: 

    - **ドメインとユーザー名**: デバイス アカウントを提供します。 ユーザーの名前 (例: “マシン名\\ユーザー” または “local\\ユーザー”)、または “ドメイン\\ユーザー” などの Active Directory アカウントを使用してローカル アカウントを使用できます。
    - **パスワード**: アカウントのパスワード。
    - **ゲートウェイを選択**: 使用するゲートウェイを選択します。

      ![接続の資格情報を入力する場所を示すスクリーンショット](../media/ui-flows-setup/credentials-screen.png)

1. **作成**を選びます。

## <a name="troubleshoot-missing-gateway"></a>ゲートウェイが見つからない場合のトラブルシューティング

次の理由により、接続の作成中にゲートウェイがリストに表示されない場合があります:

- ゲートウェイは、Power Automate リージョンとは異なるリージョンにインストールされる場合があります。 この問題を解決するには、デバイスからゲートウェイをアンインストールしてから、[適切な Power Automate リージョン](../regions-overview.md#region-mappings-for-power-automate-and-gateways) 選択して、再インストールします。
- 所有者がゲートウェイを削除しました。

## <a name="supported-keyboard-layouts"></a>サポートするキーボード レイアウト

- US キーボード – 英語 (米国)
- US キーボード – 英語 (オーストラリア)
- US キーボード – 英語 (カナダ)
- Microsoft ピンイン – 中国語 (簡体字、中国)
- ドイツ語キーボード – ドイツ語 (ドイツ)
- Microsoft IME – 日本語 (日本)
- UK キーボード – 英語 (イギリス)
- フランス語キーボード – フランス語 (フランス)
- ロシア語キーボード – ロシア語 (ロシア)
- ポルトガル語 (ブラジル ABNT) キーボード – ポルトガル語 (ブラジル)
- ポルトガル語 (ブラジル ABNT2) キーボード – ポルトガル語 (ブラジル)
- Microsoft IME – 韓国語 (韓国)
- スペイン語キーボード – スペイン語 (スペイン)
- イタリア語キーボード – イタリア語 (イタリア)
- ラテン アメリカ キーボード – スペイン語 (メキシコ)
- ポーランド語 (プログラマ) キーボード – ポーランド語 (ポーランド)
- 米国 - 国際キーボード - オランダ語 (オランダ)
- トルコ語 Q キーボード - トルコ語 (トルコ)
- インド キーボード - 英語 (インド)

## <a name="supported-languages"></a>サポートされている言語

UI フローがサポートする英語以外の言語は次のとおりです:

|||||
----|-----|-----|--------
バスク語  | フランス語    | ラトビア語   | スロバキア語
ブルガリア語   |   ガリシア語    |   リトアニア語  |   スロベニア語
カタルニア語 |   ドイツ語      |マレー語  |   スペイン語
中国語 (簡体字)    |   ギリシャ語   |   ノルウェー語   |   スウェーデン語
繁体中国語   |   ヒンディー語   |   ポーランド語  |   タイ語
クロアチア語    |   ハンガリー語   |   ポルトガル語 (ブラジル) |   トルコ語
チェコ語   |   インドネシア語  |   ポルトガル語 (ポルトガル)       |ウクライナ語
デンマーク語  |   イタリア語 |   ルーマニア語    |   ベトナム語
オランダ語       |日本語   |   ロシア語 
エストニア語    |カザフ語 |   セルビア語 (キリル、セルビア)  
フィンランド語     |韓国語     |セルビア語 (ラテン、セルビア)

>[!NOTE]
>Power Automate Desktop (プレビュー) は、英語、フランス語、ドイツ語、日本語、スペイン語でのみ利用できます。 プレビュー機能は運用環境での使用を想定しておらず、機能が制限されている可能性があります。


## <a name="uninstall-ui-flows"></a>UI flows のアンインストール

1. **スタート** メニュー > **設定** > **アプリ** を開きます。
1. **UI flows** を検索して選択します。
1. **アンインストール** を選択します。

## <a name="limitations"></a>制限

以下はサポートしません:
- Windows 10 Home のインストールはサポートしていません。

-   デスクトップ UI フロー

    -   複数のモニター。
    -   ダブルクリック、マウス ポイント、タッチ/ペン入力。
    -   Windows 上の操作 (ファイル エクスプローラー、スタートアップ メニュー、タスク バーなど。)

-   Web UI フロー

    -   右クリック。
    -   ユーザー セッション情報 (Cookie など) は再生中に再利用されません。 Web サイトで必要な場合にサインイン情報を埋め込む際は、スクリプトを編集する必要があります。

- Power Automate Desktop (プレビュー)

   - タッチ入力またはペン入力

機能固有の制限事項については、各機能のドキュメントをご覧ください。

## <a name="learn-more"></a>詳細情報を見る

- 以前のリリースから [UI フローをアップグレードする](upgrade.md)
- [デスクトップ UI フローの作成](create-desktop.md)を身につける。
- [Web UI フローの作成](create-web.md) に関する詳細情報。
- [UI フロー](run-ui-flow.md) の実行方法の詳細情報。
- [UI フローの管理](manage.md) に関する詳細情報。
- [オンプレミス ゲートウェイ](../gateway-reference.md#use-a-gateway)を深く理解する。
