---
title: Web における自動化 | Microsoft Docs
description: Web でのオートメーション
author: rokontol
ms.service: flow
ms.topic: article
ms.date: 09/22/2020
ms.author: rokontol
ms.reviewer: rokontol
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 204bafd8518de2694b76de4a6166664e52a42612
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711607"
---
# <a name="automate-web-flows"></a>Web フローを自動化する



フロー デザイナーには、**Webオートメーション** のカテゴリの多くのアクションが含まれており、それぞれのアクションはユーザーと Web ブラウザ間の相互作用に対応しています。

現在、4 つの Web ブラウザに対応しています:

* Internet Explorer
* Edge
* Firefox
* Chrome

Web オートメーションは、前述のブラウザを起動したり、アタッチしたりして、それらのブラウザ上でウェブ自動化アクションを実行することで達成されます。 開発は、手動で行うこともできますし、Web レコーダーを使用して行うこともできます。

## <a name="building-a-web-automation-flow"></a>Web オートメーション フローのビルド

Web オートメーション フローを開始するには、新しいブラウザ セッションを開始するか (**新規起動 Internet Explorer**、**新規 Edge の起動**、 **新規起動 Firefox**、**新規 Chrome の起動**)、既存のブラウザ セッションにアタッチするために、Web ブラウザの起動アクションのいずれかを使用します。

![Web ブラウザーの起動](.\media\web-automation\launch-web-browser-action.png)

> [!NOTE]
> ブラウザによっては、Power Automate Desktop で使用する前に設定が必要な場合があります。 詳細については、関連記事を参照してください。

ブラウザのセッションが変数に格納された後は、ブラウザのコンテンツとのやり取りに使用する他の Web オートメーションのアクションを追加します。 **Web フォーム記入** アクション グループは、Web ページへの入力に焦点を当て、**Web データの抽出** アクションは、フローで使用するデータを Web ページから引き出します。

多くの Web オートメーション アクションは、入力にブラウザーのインスタンスを必要とし、相互のやり取りには web エレメントが必要となります:

![Web アクションの入力](.\media\web-automation\web-action-inputs.png)

既存の Web 要素はリポジトリから追加することができますが、新しいものはアクションのプロパティから直接追加することもできます:

![web アクションから新しい要素を追加する](.\media\web-automation\adding-new-elements-through-a-web-action.png)

新しい要素を追加するには、ハイライトして、**Ctrl キーを押しながら左クリック** します:

![新しい要素のキャプチャ](.\media\web-automation\capturing-new-elements.png)

必要な要素をすべて追加した後は、**完了** を選択して レポジトリに保存します。

## <a name="data-population-on-the-web"></a>web 上でのデータを読み込む

Web ページへの入力をするには、対話する要素の性質に応じて適切な **Web フォーム記入** アクションを選択し、ブラウザのインスタンスを指定します。

![Web ページ アクションでのドロップダウン リストの値を設定する](.\media\web-automation\set-drop-down-list-value-on-web-page-action.png)

![Web ページのアクションでテキスト フィールドを読み込む](.\media\web-automation\populate-text-field-on-web-page-action.png)

## <a name="web-data-extraction"></a>Web データ抽出

Web ページからデータの一部を抽出するには、問題のデータが Web ページ全体に関係するものなのか、Web ページ内の要素に関係するものなのかに応じて、適切なアクションを使用します。

![Web ページのアクションの詳細を取得する](.\media\web-automation\get-details-of-web-page-action.png)

![Web ページのアクションの要素の詳細を取得する](.\media\web-automation\get-details-of-element-on-web-page-action.png)

大量のデータを抽出するには、**Web ページからデータを抽出する** アクションを使用し、Web ページ上で必要なデータを右クリックして、利用可能なオプションを表示します。

![Web ページからデータを抽出する](.\media\web-automation\extracting-data-from-web-page.png)

 データのリストやテーブルは、それら要素のうち 2 つが抽出に指定された後、自動的に識別されることに留意してください:

![Web ページからデータ テーブルを抽出する](.\media\web-automation\extracting-data-table-from-web-page.png)


[アクションの参照](actions-reference/webautomation.md)で利用可能な Web オートメーション アクションのリストが表示されます。


## <a name="interacting-with-the-web-and-web-services"></a>web と web サービスとの連携

Web ブラウザを使わずに、Web ページやファイル、API などの Web リソースと直接やりとりすることが可能です。

## <a name="downloading-web-resources"></a>Web リソースをダウンロードする

**Web からダウンロードする** アクションを使用して、Web ページのコンテンツや Web 上のファイルを直接ダウンロードします:

![Web アクションからのダウンロード](./media/interacting-web-services/download-from-web-action.png)

このアクションでは、**取得** メソッドと **投稿** メソッドの両方を使用することができます。ファイルはディスクに直接ダウンロードでき、ウェブページの内容は変数に保存されます。

## <a name="accessing-web-apis"></a>Web API にアクセスする

**Web サービスを呼び出す** アクションを使用して Web API にアクセスします:

![Web サービス アクションの呼び出し](./media/interacting-web-services/invoke-web-service-action.png)

このアクションはさまざまなメソッドと互換性があり、事実上あらゆる API に対応できるように完全にカスタマイズすることができます。


[アクションの参照](actions-reference/web.md)で利用可能な関連する Web アクションのリストが表示されます。
