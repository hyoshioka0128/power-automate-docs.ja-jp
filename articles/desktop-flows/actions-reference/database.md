---
title: データベース | Microsoft Docs
description: データベースのアクションに関する参考情報
author: mariosleon
ms.service: flow
ms.topic: article
ms.date: 12/02/2020
ms.author: marleon
ms.reviewer: ''
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7decf8febd4706060791c254c5c1fab048a33210
ms.sourcegitcommit: ea8954074525c40bb78fde7187f1138dd39a3382
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "5075007"
---
# <a name="database"></a>データベース

データベースに接続して SQL ステートメントを実行

|<!-- --> |
|-----|
|[SQL 接続を開く](#connect)|
|[SQL ステートメントの実行](#executesqlstatement)|
|[SQL 接続を閉じる](#close)|

### <a name="open-sql-connection"></a><a name="connect"></a>SQL 接続を開く
データベースへの新しい接続を開く

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|接続文字列|無効|テキスト値||データベースへの接続に使う接続文字列|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|SQLConnection|SQL 接続|新しい SQL 接続のハンドル|


##### <a name="exceptions"></a><a name="connect_onerror"></a> 例外
|例外|内容|
|-----|-----|
|データ ソースに接続できません|データソースへの接続に問題があることを示します|
|無効な接続文字列|指定された接続文字列が無効であることを示します|

### <a name="execute-sql-statement"></a><a name="executesqlstatement"></a>SQL ステートメントの実行
データベースに接続して SQL ステートメントを実行

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|接続の取得方法|N/A|接続文字列、SQL 接続変数|SQL 接続変数|指定した接続文字列から新しい接続を作成するか、既に開いている接続を選択するかを指定します|
|SQL 接続|無効|SQL 接続||新しい SQL 接続のハンドル|
|接続文字列|無効|テキスト値||データベースへの接続に使う接続文字列|
|SQL ステートメント|無効|テキスト値||データベースに対して実行する SQL ステートメント|
|タイムアウト|有効|数値|30|データベースから取得された結果を待機する最大時間|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|QueryResult|Datatable|データベースから取得された結果 (行と列があるデータ テーブル形式)|


##### <a name="exceptions"></a><a name="executesqlstatement_onerror"></a> 例外
|例外|内容|
|-----|-----|
|データ ソースに接続できません|データソースへの接続に問題があることを示します|
|無効な接続文字列|指定された接続文字列が無効であることを示します|
|SQL ステートメントでエラーが発生しました|指定された SQL ステートメントでエラーが発生したことを示します|

### <a name="close-sql-connection"></a><a name="close"></a>SQL 接続を閉じる
データベースへの開いている接続を閉じる

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|SQL 接続|無効|SQL 接続||新しい SQL 接続のハンドル|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="close_onerror"></a> 例外
- このアクションには例外は含まれません

### <a name="configuring-the-connection-string"></a>接続文字列を構成する
SQL アクションにはデータベース接続が必要です。 データベースに接続するには、文字列を手動または変数として入力します。 アクションがデータベースに接続すると、その接続を SQL 接続変数に格納します。

1. **接続文字列の作成** を選択し、**データリンクのプロパティ** ウィンドウを開きます。 データ リンク ツールは、ユーザーが必要な接続文字列を段階的に作成するのに役立ちます。 

2. ウィザードにアクセスしたら、**プロバイダー** タブでデータベースの正しいドライバを選択します。

   ![データ リンク プロパティのプロバイダー タブ](..\media\database\data-link-properties-provider-tab.png)

3. 次に、**接続** タブで、サーバー名、ユーザー名、パスワード、データベース名などの残りの詳細を入力します。 **テスト接続** ボタンを選択して、接続文字列がデータベースに正常に接続することをテストします。 または、既製の接続文字列をコピーします。

   ![データ リンク プロパティの接続タブ](..\media\database\data-link-properties-connection-tab.png)

4. **詳細設定** タブで接続タイムアウトと追加のネットワーク設定を指定します。

   ![データ リンク プロパティの詳細設定タブ](..\media\database\data-link-properties-advanced-tab.png)