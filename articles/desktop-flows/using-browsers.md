---
title: ブラウザーの使用と拡張機能の管理 | Microsoft Docs
description: ブラウザーの使用と拡張機能の管理
author: georgiostrantzas
ms.service: flow
ms.topic: article
ms.date: 09/22/2020
ms.author: getrantz
ms.reviewer: ''
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4fa9137953afba6c04c34c39a55dbfd8deb06daf
ms.sourcegitcommit: 3ee73d8cdfd40c8988f329ba5e8c6598f4704e12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "4740465"
---
# <a name="use-browsers-and-manage-extensions"></a>ブラウザーの使用と拡張機能の管理



Web 関連のタスクの自動化には、Microsoft Power Automate Desktop が提供する既成の **オートメーション ブラウザー** を使用できます。 

**オートメーション ブラウザ** に加えて、このプラットフォームでは 4 つの最も人気のあるブラウザーに対応しています: **Microsoft Edge**、**Internet Explorer**、**Google Chrome**、**Mozilla Firefox**。 これらのブラウザーが機能するには、追加の設定やブラウザーの拡張機能が必要です。

> [!IMPORTANT]
> Microsoft Edge を使用するには、Chromium に基づくバージョンがインストールされていることを確認してください。 それ以外の古いバージョンはサポートされていません。 

## <a name="configuring-internet-explorer"></a>Internet Explorer を構成する

既定では、**Internet Explorer** は保護モードで動作し、外部アプリケーションからの制御を防ぎます。

このモードを無効にして Power Automate Desktop がブラウザーを処理できるようにする方法:

1. **Internet Explorer** を起動し、**歯車アイコン** をを選択します。メニューで **インターネット オプション** を選択します。

    ![Internet Explorer オプション。](media/using-browsers/internet-explorer-options.png)

1. **インターネット設定** ダイアログ ボックスで、**セキュリティ** タブを開き、**インターネット** ゾーンを選択して **保護モードを有効にする** オプションを無効化します。

    ![Internet Explorerオプションのセキュリティ タブ。](media/using-browsers/internet-explorer-internet-protected-mode.png)

1. **ローカル イントラネット** と **信頼済みサイト** ゾーンに対して同じ手順を繰り返します。

    ![Internet Explorerオプションのローカル イントラネットと信頼済みサイトゾーン。](media/using-browsers/internet-explorer-local-intranet-protected-mode.png)

1. **適用** と **OK** を選択して変更婦負用を保存してダイアログ ボックスを閉じます。

## <a name="configuring-internet-explorer-for-servers"></a>サーバーに向けて Internet Explorer を構成する

Windows Server で Internet Explorer を使用するには、**Internet Explorer の強化されたセキュリティ構成** 機能を無効にする必要があります。

この機能は、すべてのフローが新しい **Internet Explorer** アクションを使用して **Internet Explorer** や **オートメーション ブラウザー** インスタンスを適切に起動することを禁止します。 さらに、Web ヘルパーが期待どおりに機能しなくなります。 

**IEESC** 機能を無効にする方法 :

1. **サーバー マネージャー** を起動し、**ローカル サーバー** タブに移動します。

1. **Internet Explorer強化されたセキュリティ構成** オプションを選択し、それぞれの構成ダイアログボックスを開きます。

1. 管理者とユーザーの両方で **IEESC** 機能を無効にします。

    ![ローカルサーバー設定の IEESC 機能。](media/using-browsers/internet-explorer-servers.png)

1. **OK** を選択して変更を適用します。

## <a name="configuring-microsoft-edge"></a>Microsoft Edge を構成する

**Microsoft Edge** を使って Web 関連の作業を自動化するには、それぞれのブラウザの拡張機能をインストールする必要があります。

拡張機能をインストールする方法:

1. **フロー デザイナー** を起動し、**ツール** -> **ブラウザ拡張機能** に移動して、**Microsoft Edge** を選択します。

    ![フロー デザイナーの Microsoft Edge 拡張オプション。](media/using-browsers/edge-extension-option.png)

1. 拡張機能の Web ページで、**取得する** を選択して拡張機能をインストールします。 

   ![拡張機能のページの[取得]オプション。](media/using-browsers/edge-get-extension.png)

1. ポップアップ ダイアログボックスで、**拡張機能の追加** を選択してインストールを確認します。 

   ![拡張機能ページの拡張機能の追加オプション。](media/using-browsers/edge-add-extension.png)

**Microsoft Edge** が Power Automate Desktop で期待通りに動作することを確認するには、Edge が閉じているときにバックグラウンドで実行しているアプリを無効にします。 

このオプションを無効にするには、**Settings** -> **System** にアクセスし、**Microsoft Edge が終了してもバックグラウンド アプリの実行を続ける** の横にある **スライダー** を選択します。

![Edge の設定。](media/using-browsers/edge-options.png)

## <a name="configuring-google-chrome"></a>Google Chrome を構成する

Power Automate Desktop フローで **Google Chrome** を使用するには、対応するブラウザーの拡張機能をインストールする必要があります。

拡張機能をインストールする方法:

1. **フロー デザイナー** を起動し、**ツール** -> **ブラウザ拡張機能** に移動して、**Google Chrome** を選択します。

    ![フロー デザイナーの Google Chrome 拡張オプション。](media/using-browsers/chrome-extension-option.png)

1. 表示された Web ページで、**Chrome に追加** を選択して拡張機能をインストールします。 

   ![拡張機能ページの Chrome に追加するオプション。](media/using-browsers/chrome-add-extension.png)

1. ポップアップ ダイアログボックスで、**拡張機能の追加** を選択してインストールを確認します。 

   ![拡張機能のインストール オプション ページ。](media/using-browsers/chrome-add-extension-confirmation.png)

**Google Chrome** が Power Automate Desktop で期待通りに動作することを確認するには、Chrome が閉じているときにバックグラウンドで実行しているアプリを無効にします。 

このオプションを無効にするには、**設定** -> **詳細** -> **システム** にアクセスし、**Google Chrome が終了してもバックグラウンド アプリの実行を続ける** の横にある **スライダー** を選択します。

![Chrome の設定。](media/using-browsers/chrome-options.png)

## <a name="configuring-mozilla-firefox"></a>Mozilla Firefox の設定

Power Automate Desktop フローで **Mozilla Firefox** を使用するには、対応するブラウザーの拡張機能をインストールする必要があります。

拡張機能をインストールする方法:

1. **フロー デザイナー** を起動し、**ツール** -> **ブラウザ拡張機能** に移動して、**Firefox** を選択します。

    ![フロー デザイナーの Firefox 拡張オプション。](media/using-browsers/firefox-extension-option.png)

1. 起動したブラウザー ダイアログボックスで、**追加** を選択して拡張機能をインストールします。 

   ![拡張機能のページの [追加] オプション。](media/using-browsers/firefox-add-extension.png)

1. 表示されたダイアログボックスで、**了解** を選択してインストールを確認します。

   ![拡張機能ページの了解オプション。](media/using-browsers/firefox-add-extension-confirmation.png)

ブラウザをフリーズさせ、ユーザーが他のタブやウィンドウに切り替えられないようにする Firefox アラートは、フローの機能に影響を与える可能性があります。 

この機能を無効にする方法 :

1. **URL バー** に **about:config** を入力します。

1. 結果のリストから **prompts.tab_modal.enabled**  のプリファレンスを検索し、**false** に変更します。

    ![Firefox の prompts.tab_modal.enabled preference。](media/using-browsers/firefox-options.png)

## <a name="using-the-actual-internet-explorer-vs-the-automation-browser"></a>実際の Internet Explorer とオートメーション ブラウザーの使用

**オートメーション ブラウザー** は、**Internet Explorer** に基づくものですが、自動化の有効性を高めるいくつかの機能と制限を提供します。

1. **オートメーション ブラウザー** は既成の機能ですが、**Internet Explorer** には追加の構成が必要です。 手動による変更を禁止する厳格なセキュリティポリシーを持つ組織では、セキュリティ構成が望まれない場合があります。 

1. **Web ページ上のリンクをクリックしてダウンロードする** アクションは、**Internet Explorer** のバージョンを問わず、**オートメーション ブラウザー** で動作します。 実際の **Internet Explorer** では、アクションにはバージョン 8 以下が必要です。

1. **オートメーション ブラウザー** は、実際の **Internet Explorer** で防ぐことのできない可能性のあるポップアップ メッセージ ダイアログボックスを抑制します。 この機能が望ましくない場合は、**新規起動Internet Explorer** アクションの URL の末尾にある **(ShowDialogs)** 接尾辞を適用します。

1. **オートメーション ブラウザー** では、ウィンドウでタブやリンクを開くことには対応していません。 ユーザーがリンクをクリックすると、ブラウザは同じウィンドウ/インスタンスでリンクを開きます。

1. **オートメーション ブラウザー** は実際の **Internet Explorer** のように不要な要素やアドオンを読み込まないため、性能的には少し有利です。



