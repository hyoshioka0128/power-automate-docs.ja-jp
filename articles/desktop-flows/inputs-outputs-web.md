---
title: Selenium IDE のフローで入力と出力を使用する | Microsoft Docs
description: Selenium IDE のフローで入力と出力を使用します。
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
ms.date: 03/30/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c722003b092005f2ed341d1c0928df67f8806ca4
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711600"
---
# <a name="use-inputs-and-outputs-in-selenium-ide-flows"></a>Selenium IDE のフローで入力と出力を使用します

再生中に自動化されたアプリケーションに渡す入力を定義できます。 また、自動化されたアプリケーションからの *出力* をフローに渡すこともできます。

## <a name="define-inputs-for-a-web-ui-flow"></a>Web UI フローの入力を定義する

UI フローの入力により、データベースや他の UI フローなどの外部ソースから、自動化する対象のレガシー ソフトウェアに情報を渡すことができます。

初期化 (通常は **store** コマンドで行われる) の前に使用 (読み込み) された変数は、自動的に入力変数として処理され、**Web の UI フローの実行** アクション カードに表示されます。

変数は文字列補間を通じて使用できます。たとえば、click コマンドの Target フィールドを "id=\${elementId}" に変更することができます。 type コマンドの Value フィールドを "\${inputText}" に変更することができます。

次のスクリーンショットのコマンド **ウィンドウ サイズを設定** とコマンド **タイプ** では、初期化されていない変数 \${Width}、\${Height}、 \${search} が使用されています。 これらの変数が入力値となります。

![ウィンドウのサイズと種類を設定する](../media/inputs-outputs-web/set-window-size.png "ウィンドウのサイズと種類を設定する")

一部のコマンドでは、変数を直接使用することができます。たとえば、forEach コマンドのターゲットと値のフィールドは両方とも変数なので、"\${}" で囲む必要はありません。

変数名を直接取得するコマンドについては、[Selenium コマンド](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) リファレンスを参照してください。

## <a name="define-outputs-for-a-web-ui-flow"></a>Web の UI フローの出力を定義する

selenium スクリプトで定義された変数は、自動的に出力値になります。 変数を宣言するには、以下のコマンドを使用します。

[ストア](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store)

[ストア属性](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-attribute)

[ストア json](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-json)

[ストア タイトル](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-title)

[ストアの値](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-value)

[ストア ウィンドウ ハンドル](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-window-handle)

[ストア xpath カウント](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-xpath-count)

[スクリプトの実行](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#execute-script) (スクリプトの最後に 'return' 構文を追加して、格納するオブジェクトを返します)

## <a name="next-steps"></a>次の手順

- [Selenium IDE フローを作成する](create-web.md)方法について説明します。
- [Windows レコーダー (V1) フローのトリガー](run-desktop-flow.md)方法について説明します。

