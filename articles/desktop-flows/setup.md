---
title: デバイスで Power Automate Desktop を設定する | Microsoft Docs
description: ご利用のデバイスで Power Automate Desktop を設定します。
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
ms.openlocfilehash: ae3aa4589b88434807d35b3f565e06b5fc574143
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711679"
---
# <a name="set-up-power-automate-desktop"></a>Power Automate Desktop の設定

デバイスを使用してデスクトップ フローを作成する前に、デバイスがここに記載されている要件を満たしていることを確認する必要があります。

> [!TIP]
> デスクトップ フローを作成する前に、[コネクタの一覧](https://flow.microsoft.com/connectors/)を調べて、自動化をするアプリケーションに既にコネクタがあるかどうかを確認します。 存在する場合は、デスクトップ フローではなく、クラウド フローの作成を検討してください。 [独自のコネクタ](https://docs.microsoft.com/connectors/custom-connectors/) を作成することもできます。

## <a name="prerequisites"></a>前提条件

- Power Automate アテンド型 RPA の [有償版](https://flow.microsoft.com/pricing/) または [試用版](https://flow.microsoft.com/manage/) のライセンス。

- 管理者特権と Power Automate で Windows デバイスにサインインするための職場または学校アカウント。

- Windows 10 Pro、Windows 10 Entreprise、Windows Server 2016、Windows Server 2019 を実行するデバイス。

- [Microsoft Edge](https://www.microsoft.com/edge/) (バージョン 80 以降)   または Google Chrome ブラウザー。

- [Microsoft Dataverse データベース](https://docs.microsoft.com/power-platform/admin/create-database) のある [環境](https://docs.microsoft.com/power-platform/admin/environments-overview)。

- サポートするキーボードが接続されていること。

> [!IMPORTANT]
> デスクトップ フローを記録、テスト、実行するには、各コンポーネントの最新バージョンが必要です。

## <a name="install-power-automate-desktop-on-your-device"></a>ご利用のデバイスに Power Automate Desktop をインストールする

インストーラーは、自動化の記録、編集、テストに必要なコンポーネントをすべて含みます。 

釣りの手順で  Power Automate Desktop アプリをインストールします:

1. [Power Automate Desktop のインストーラーをダウンロードする](https://go.microsoft.com/fwlink/?linkid=2102613)。
1. **Setup.Microsoft.PowerAutomateDesktop.exe** ファイルを開きます。 

   このファイルは、前の手順でダウンロードした後、**ダウンロード** フォルダーにあるはずです。

1. **Power Automate Desktop の設定** インストーラーの指示に従い、インストールを完了させます。 
1. インストールを完了するために各機能を選択します。 

>[!IMPORTANT]
>インストーラーでは、WebDriver コンポーネントがインストールされます。 このコンポーネントは、Selenium IDE で作成されたデスクトップ フローの実行に必要となります。
>また、これにより Power Automate Desktop アプリとサードパーティのコンポーネントがインストールされます。

![インストール オプションの画像](../media/desktop-flows-setup/installer-checkboxes.png)

### <a name="set-data-collection-options"></a>データ収集オプションを設定する

使用状況データを Microsoft に送信しない場合は、インストール中に既定の設定を変更できます。 これを行うには、**使用状況データの収集を Microsoft に許可して Power Automate を向上させる** をオフにします。

## <a name="install-the-power-automate-browser-extension"></a>Power Automate ブラウザ拡張機能をインストールする 

インストールの完了後は、Power Automate Desktop の次の拡張機能をインストールして有効にする必要があります。 この拡張機能を使用すると、デスクトップ フローで Web アクションを記録して実行できます。

![インストール成功の画像](../media/desktop-flows-setup/screen.png)

インストーラーに表示されるリンクの 1 つを選択します。 たとえば、Microsoft Edge で Web オートメーションを記録する場合は、**Microsoft Edge** リンクを選択します。

   ブラウザのストアが拡張機能の公式ページに直接開きます。

> [!IMPORTANT]
> すでに Power Automate 拡張機能をインストールしている場合、再インストールする必要はありません

#### <a name="microsoft-edge"></a>Microsoft Edge: 
- [Edge の拡張機能をインストールする](https://go.microsoft.com/fwlink/?linkid=2151411): **取得する** を選択し、プロンプトが表示されたら、**拡張機能の追加** を選択します。 
- ページ上部に *この拡張機能は Microsoft Edge でオフになっています* というメッセージが表示される場合は、**拡張機能をオンにする** を選択します。

#### <a name="google-chrome"></a>Google Chrome: 
- [Chrome の拡張機能をインストールする](https://go.microsoft.com/fwlink/?linkid=2150929): **Chrome に追加する** を選択し、プロンプトが表示されたら、**拡張機能の有効化** を選択します。 
- ページ上部に *この項目は Chrome で無効になっています* とメッセージが表示される場合は、**この項目を有効化する** を選択します。

#### <a name="mozilla-firefox"></a>Mozilla Firefox:
- [Firefox  の拡張機能をインストールする](https://go.microsoft.com/fwlink/?linkid=2151511): **Firefox に追加する** を選択し、プロンプトが表示されたら、**追加** を選択します。 


> [!TIP]
> ご利用のブラウザで拡張機能を有効にできない場合は、[Microsoft Edge](https://www.microsoft.com/edge/) (バージョン 80 またはそれ以降)、または GoogleChrome、Firefox を使用する必要があります。 その他のブラウザーはサポートされていません。 

## <a name="install-the-on-premises-data-gateway-to-run-your-desktop-flows-from-the-cloud"></a>オンプレミス データ ゲートウェイをインストールして、クラウドからデスクトップ フローを実行します

[イベント、スケジュール、またはボタン フロー](..\flow-types.md)からデスクトップをトリガーするには、ゲートウェイが必要です リモート デバイス上。

>[!TIP]
>デバイスでフローを作成、編集、テストするだけの場合は、ゲートウェイは必要ありません。

必要に応じて [オンプレミス データ ゲートウェイをインストールします](https://docs.microsoft.com/data-integration/gateway/service-gateway-install)。


>[!IMPORTANT]
>ゲートウェイをインストールすると、既定で、Power Automate が使用するリージョンになります。


## <a name="setup-desktop-flows-connections-and-machine-credentials"></a>デスクトップ フローの接続とマシンの資格情報を設定する

1. [Power Automate](https://powerautomate.microsoft.com) にサインインする。
1. 画面左側の **データ** を展開します。
1. **接続** を選択します。

   ![[接続] タブのスクリーンショット](../media/desktop-flows-setup/connections-tab.png)

1. 新規接続 を選択します。

   ![接続のスクリーンショット](../media/desktop-flows-setup/new-connection.png)

1. *デスクトップ フロー* を検索し、**デスクトップ フロー** を選択します。

   <!-- ![A screenshot of the search box](../media/desktop-flows-setup/search-desktop-flow.png) -->

1. ゲートウェイ情報とデバイスの資格情報を指定します: 

    - **ドメインとユーザー名**: デバイス アカウントを提供します。 ユーザーの名前 (例: “マシン名\\ユーザー” または “local\\ユーザー”)、または “ドメイン\\ユーザー” などの Active Directory アカウントを使用してローカル アカウントを使用できます。
    - **パスワード**: アカウントのパスワード。
    - **ゲートウェイを選択**: 使用するゲートウェイを選択します。

      ![接続の資格情報を入力する場所を示すスクリーンショット](../media/desktop-flows-setup/credentials-screen.png)

1. **作成** を選択します。

## <a name="install-power-automate-desktop-silently"></a>Power Automate Desktop を静的にインストールする

Power Automate Desktop をサイレントインストールする場合は、次の手順に従ってください。

>[!NOTE]
>Power Automate Desktop の手動インストールとサイレント インストールには同じインストーラーが使用されます。

### <a name="install-power-automate-desktop-using-the-command-line"></a>コマンド ラインを使用した Power Automate Desktop をインストールする

1. [Power Automate Desktop のダウンロード](https://go.microsoft.com/fwlink/?linkid=2102613) をダウンロードする。

1. **開始** を開きます。

1. **コマンド プロンプト** を検索し、管理者として実行します。

   ![スタートメニュー表示されたコマンド プロンプトのスクリーンショット](../media/desktop-flows-setup/command-prompt.png)

1. ダウンロードするディレクトリ (または Power Automate Desktop をダウンロードしたディレクトリ) を変更します :

   以下に入力例を示します:
   
   ```
    cd C:\Users\JohnDoe\Downloads\
   ```

1. 入力:

   ```
   Setup.Microsoft.PowerAutomateDesktop.exe -Silent -Install -ACCEPTEULA
   ```
   
   インストーラーが実行され、Power Automate Desktop の設定が完了します。

   >[!IMPORTANT]
   > Power Automate Desktop の[利用規約](https://go.microsoft.com/fwlink/?linkid=2147215)を受け入れることを示す `-ACCEPTEULA` 引数を入力する必要があります。

1.  以上でスタートメニューから Power Automate Desktop を起動できるようになります。

### <a name="command-line-argument-details"></a>コマンド ライン引数の詳細

また、コマンド プロンプトのヘルプ メニューから、すべてのコマンド ライン引数の詳細を取得することもできます:

   ```
   Setup.Microsoft.PowerAutomateDesktop.exe -HELP
   ```

| command              | 内容                                                                                                                                                                        |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| -INSTALLPATH:Value  | 作成されるインストール フォルダーのフルパスです。 既定値は `%PROGRAMFILES(X86)%\Power Automate Desktop` です。                                                             |
| -DISABLEPADSHORTCUT | 既定では、Power Automate Desktop アプリのショートカットはデスクトップ上に作成されます。この引数を使用すると、これを作成ないことを明示します。                                                                 |
| - DISABLETURNONRD   | インストーラーでデバイスのリモートデスクトップをオンにない場合は、引数を使用します。 無人実行のサポートが必要な場合は、リモート デスクトップをオンにする必要があります。 |
| -ACCEPTEULA  | この引数を使用して、Power Automate Desktop の使用条件に同意することを示します                                                                                                                     |
| -HELP               | この引数は、インストーラーの引数に関するすべての詳細を表示します。 プロンプト                                                                                                                   |

以下は、Power Automate Desktop をインストールするコマンドラインの例です: 

   ```
   Setup.Microsoft.PowerAutomateDesktop.exe -SILENT -Install -ACCEPTEULA -INSTALLPATH: D:\My Programs\foo
   ```

### <a name="uninstall-power-automate-desktop-using-the-command-line"></a>コマンド ラインを使用した Power Automate Desktop をアンストールする

次のコマンドを使用して、Power Automate Desktop をサイレント アンインストールします:
   
   ```
   Setup.Microsoft.PowerAutomateDesktop.exe -Silent -Uninstall
   ```

### <a name="update-your-version-of-power-automate-desktop"></a>Power Automate Desktop のバージョンを更新する

Power Automate Desktop を更新するには、インストールに使用するのと同じコマンドライン引数を使用します。 

>[!NOTE]
>テレメトリ、ショートカットなどを含むすべてのデータと構成は、Power Automate Desktop の更新時に保持されます。 以前に無効にしたパラメータを有効にする場合は、まず Power Automate Desktop をアンインストールし、再インストールする必要があります。 

### <a name="install-the-gateway-with-powershell-cmdlets"></a>PowerShell コマンドレットを使用してゲートウェイをインストールする

クラウド フローからデスクトップ フローをトリガーするには、オンプレミスのデータ ゲートウェイが必要となります。

[PowerShell コマンドレット](https://docs.microsoft.com/powershell/gateway/overview?view=datagateway-ps)を使用して、ゲートウェイをインストール、構成、管理できます。

>[!IMPORTANT]
>PowerShell コマンドレットを使用するには、昇格されたセッションで PowerShell 7.0.0 以降からコマンドレットを実行する必要があります。

## <a name="troubleshoot-missing-gateway"></a>ゲートウェイが見つからない場合のトラブルシューティング

次の理由により、接続の作成中にゲートウェイがリストに表示されない場合があります:

- ゲートウェイは、Power Automate リージョンとは異なるリージョンにインストールされる場合があります。 この問題を解決するには、デバイスからゲートウェイをアンインストールしてから、[適切な Power Automate リージョン](../regions-overview.md#region-mappings-for-power-automate-and-gateways) 選択して、再インストールします。
- 所有者がゲートウェイを削除しました。

## <a name="install-windows-recorder-v1-extension-optional"></a>Windows レコーダー (v1) 拡張機能のインストール (オプション)

Windows レコーダー (V1) は、デスクトップ オートメーションを記録、再生するもう1つのオプションです。 Power Automate Desktop は最新の RPA ソリューションであるため、これを使用することを推奨します。

次の手順に従って、Windows レコーダー (V1) 拡張機能をインストールします:

1. ストアから Micrsodt Edge や Google Chroome に拡張機能をインストールします (Firefox Windows レコーダー (V1) ではサポートされていません)

#### <a name="microsoft-edge"></a>Microsoft Edge: 
- [Edge の拡張機能をインストールする](https://go.microsoft.com/fwlink/?linkid=2151412): **取得する** を選択し、プロンプトが表示されたら、**拡張機能の追加** を選択します。

#### <a name="google-chrome"></a>Google Chrome: 
- [Chrome の拡張機能をインストールする](https://go.microsoft.com/fwlink/?linkid=2150930): **Chrome に追加する** を選択し、プロンプトが表示されたら、**拡張機能の有効化** を選択します。 


## <a name="install-selenium-ide-to-automate-web-applications-with-desktop-flows-optional"></a>(任意) Selenium IDE をインストールして Web アプリケーションを自動化する

Selenium IDE は Web サイト上の人間の操作を記録して再生できるオープンソース ツールです。

デスクトップ フローを使用すると、Power Automate から Selenium IDE スクリプトを実行し、Dataverse に安全に (適切な IT ガバナンスで) 保存することができます。

Selenium IDE をインストールするには、次の手順に従います。

1. Windows レコーダー (V1) の拡張機能をインストールして有効化されていることを確認してください (前述のセクションを参照)

1. [Microsoft Edge](https://www.microsoft.com/edge/) (バージョン 80 以降) または Google Chrome の Selenium IDE を [ダウンロードしてインストールします](https://go.microsoft.com/fwlink/?linkid=2107665)。

1. Microsoft Edge (バージョン 80 以降) で、**他のストアからの拡張機能を許可する** を選択し、**Chrome に追加** を選択します。

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

デスクトップ フローで英語以外にサポートされる言語は次のとおりです:

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
>Power Automate Desktop が対応している言語: 英語、フランス語、ドイツ語、日本語、スペイン語、デンマーク語、オランダ語、フィンランド語、イタリア語、ノルウェー語、ポーランド語、ポルトガル語 (ブラジル)、中国語 (簡体字)、中国語 (繁体字)、スウェーデン語、トルコ語。

## <a name="uninstall-power-automate-desktop"></a>Power Automate Desktop をアンインストールする

1. **スタート** メニュー > **設定** > **アプリ** を開きます。
1. **Power Automate Desktop** を検索し、選択します。
1. **アンインストール** を選択します。

## <a name="limitations"></a>制限

以下はサポートしません:
- Windows 10 Home のインストールはサポートしていません。

-   Windows レコーダー v1 デスクトップ フロー

    -   複数のモニター。
    -   ダブルクリック、マウス ポイント、タッチ/ペン入力。
    -   Windows 上の操作 (ファイル エクスプローラー、スタートアップ メニュー、タスク バーなど。)

-   セレニウム デスクトップ フロー

    -   右クリック。
    -   ユーザー セッション情報 (Cookie など) は再生中に再利用されません。 Web サイトで必要な場合にサインイン情報を埋め込む際は、スクリプトを編集する必要があります。

機能固有の制限事項については、各機能のドキュメントをご覧ください。

## <a name="learn-more"></a>詳細情報を見る

- [ Power Automate Desktop フローの作成](create-flow.md)について説明します。
- [Windows レコーダー (V1) フローの作成](create-desktop.md)方法について説明します。
- [Selenium IDE フローを作成する](create-web.md)方法について説明します。
- [デスクトップ フロー](run-desktop-flow.md)の実行について説明します。
- [ デスクトップ フローの管理](manage.md)について説明します。
- [オンプレミス ゲートウェイ](../gateway-reference.md#use-a-gateway)を深く理解する。
