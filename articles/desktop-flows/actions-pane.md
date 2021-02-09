---
title: アクションとアクション ペイン | Microsoft Docs
description: このセクションでは、フロー デザイナーで使用できるアクションとアクション ペインついて説明します。
author: olegmelnykov
ms.service: flow
ms.topic: article
ms.date: 09/22/2020
ms.author: olmelnyk
ms.reviewer: olmelnyk
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 335431ff3fb9304c14473ef1b410e174fa3fe001
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711667"
---
# <a name="configure-actions-and-the-actions-pane"></a>アクションとアクション ペインを構成する



フロー デザイナーを開くと、ウィンドウの左側のアクション ペインにすべてのアクショングループが表示されます。 

![アクション ペイン](\media\actions-pane\actions-pane.png)

特定のアクションを簡単に見つけるには、検索バーにアクションの名前を入力します。 検索すると、部分一致も返されます。

![アクション ペインでの検索](\media\actions-pane\actions-search.png)

## <a name="adding-an-action-to-the-workspace"></a>ワークスペースにアクションを追加する

デスクトップ フローの開発を開始するには、アクションを選択してダブル クリックするか、ワークスペースにドラッグします。 

![アクションの追加](\media\adding-actions\add-action.png)

アクションのパラメーターが表示したダイアログ ボックスが開きます。 アクションには、変数名や既定値などの特定のパラメーターがあります。 その他のアクションでは、初期化にあたってユーザーの入力が必要になります。 **保存** を選択した後、ワークスペースにアクションが表示されます。

![アクションのプロパティ](\media\adding-actions\action-properties.png)

## <a name="configuring-an-action"></a>アクションを構成する

Power Automate Desktop のアクションは、主に 2 つのセグメントで構成されています:
- 入力パラメーター - テキスト フィールド、ドロップダウン メニュー、チェックボックスのフォームがあります
- 生成された変数 - 自動生成された変数です

![コピー フォルダ アクションのパラメーターと生成される変数です。](media/configuring-actions/actions-parameteres-outputs.png)

入力パラメーターは、アクションがどのように機能し、入力としてデータを取得するかを決定します。 データにはハードコードされた値や変数を使用することができます。 

変数をパラメーターとして使用するには、フィールドの右側にあるアイコンを選択し、それぞれの変数を選択します。

各フィールドには、数字、テキスト、リストなどの特定のデータ型を受け入れることができます。 間違ったデータ型の値の変数が入力に使用した場合、アクションはエラーをスローします。 

![アクションの入力パラメータを選択するアイコンです。](media/configuring-actions/actions-parameteres.png)

生成された変数は、アクションの結果を保持し、後で使用することができます。 生成されたすべての変数は、アクションのプロパティ下部に表示されます。 

生成された変数は、そのデータによって定義されたデータ型を持っています。 **変数** ペインでは、変数のデータ型を確認することができます。 データ型についての詳細は、[関連記事](variable-data-types.md)を参照してください。

生成された変数を後で使用しない場合は、左側のアイコンを選択して **不要** を選択します。 

![アクションで生成された変数を無効にするオプションです。](media/configuring-actions/actions-outputs.png)

## <a name="configuring-action-exceptions"></a>アクション例外を構成する

アクションが例外をスローすると、フローは既定でその実行を停止します。 アクションのカスタム エラー処理の動作を設定するには、プロパティで **エラーの場合** オプションを選択します。

![アクションの [エラーの場合] オプション。](media/configuring-actions-exceptions/on-error-option-action.png)

ダイアログ ボックスの最初のオプションは、**エラーが発生した場合の再試行アクション** チェック ボックスです。これにより、フローが 2 秒後にアクションをもう 1 度実行するようになります。

![アクションの再試行アクション チェックボックス。](media/configuring-actions-exceptions/retry-action.png)

再試行オプションが失敗した場合でも、フローの実行を継続するには、**フローの実行を継続する** オプションを選択します。 ドロップダウン リストでは以下のことができます:

- **次のアクションに進む**: 次の順番に設定されているアクションを実行します。
- **アクションの繰り返し**: 実行が成功するまでアクションを実行します。 
- **ラベルに進む**: **ラベル** アクションで定義されたポイントから実行を継続します。

![アクションの [フロー実行] オプションを継続します。](media/configuring-actions-exceptions/continue-flow-run.png)

Power Automate Desktop には、さらに 2 つのエラー処理オプションが用意されています。 **新規ルール** ボタンを選択すると、次のことが実行できます:
- **変数の設定**: 指定した変数に希望の値を設定します。
- **サブフローの実行**: 指定されたサブフローを実行します。 

![アクションの [新規エラー] オプション。](media/configuring-actions-exceptions/new-rule.png)

異なるエラーが異なるエラー処理動作を必要とする場合は、**高度な** オプションを選択して、可能性のある各エラーを個別に構成します。 

## <a name="enabling-and-disabling-actions"></a>アクションを有効または無効にする

アクションを無効化または有効化するには、アクションを右クリックし、それぞれ **アクションの無効化** または **アクションの有効化** を選択します。 

![アクションのオプションを無効化する。](media\enabling-disabling-actions\enable-disable-action.png)

アクションを無効にすると、これを消去せずにフローから削除することができます。 この機能は、一般にデスクトップ フローのさまざまなバージョンをテストし、最も効率的なものを決定するために適用されます。 

アクションが無効化されている場合、そのアクションで定義されているすべての変数は **変数** ペインから非表示になります。 非表示の変数が他のアクションで使用されている場合、フローがエラーをスローする場合があります。 

以下の例では、2 つのアクションが無効化されたアクションで定義された変数を含んでいるため、エラーが発生しました。

![アクションを無効にすると、いくつかの変数が非表示になる画面例。](media\enabling-disabling-actions\enable-disable-action-variables.png)