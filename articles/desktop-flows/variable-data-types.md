---
title: 変数のデータ型 | Microsoft Docs
description: 変数のデータ型
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
ms.openlocfilehash: 58b3eb601c08a961dfc4de8d156e8fb366831f7e
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711639"
---
# <a name="variable-datatypes"></a>変数のデータ型



フロー内に変数を作成すると、Power Automate Desktop はその内容に応じて特定の型に変換します。

これらのデータ型の中には、**数値** などのアプリケーション全体で広く使われているものもあれば、**ブラウザー インスタンス** などの明示的なアクションやアクションのグループを必要とするものもあります。

## <a name="simple-data-types"></a>シンプルなデータの種類

- **テキスト値** - メールアドレスから .txt ファイルのテキスト内容まで、あらゆる種類のテキストです。 

  [テキストデータ型プロパティ](datatype-properties.md#texts)
  
  **テキスト値** 変数を作成するには、**変数の設定アクション** を使用して、入力パラメーターに表記なしで希望のテキストを入力します。

  ![作成されたテキスト値変数の例。](media\variable-data-types\create-text-variable.png)

- **数値** - これは数値に適用される型です。 数学演算で使用できるデータ型はこれのみです。 

  **テキスト値** 変数を作成するには、**変数の設定アクション** を使用して、入力パラメーターに表記なしで希望の数値を入力します。 
  
  ハードコードされた数値を除いて、パーセント記号の範囲内で変数を使った数式を使うことができます。 数式については、[変数や % 表記の使用](variable-manipulation.md)  の記事で詳しく紹介されています。

  ![作成された数値変数の例。](media\variable-data-types\create-numeric-variable.png)

- **ブール値** - この値は、**True** または **False** のいずれかになります。 
  
  **ブール値値** 変数を作成するには、**変数の設定アクション** を使用し、入力パラメータに **%True%** または **%False%%** という式を入力します。 
  
  さらに、論理演算子、変数、パーセンテージ表記を使用して、複雑な式を作成できます。 論理式については、[変数や % 表記の使用](variable-manipulation.md)  の記事で詳しく紹介されています。

  ![作成されたブール値変数の例。](media\variable-data-types\create-boolean-variable.png)

## <a name="advanced-data-types"></a>高度なデータ型

- **リスト** - リストはアイテムの集合です。 個々のリスト項目の種類に応じて、テキスト値のリスト、数値のリストなどがあります。 リストのデータ型は、プログラミング用語では 1 次元配列に相当します。 

  **新規リストの作成** アクションでリストを作成し、**リストにアイテムを追加する** アクションでそのリストにアイテムを追加することができます。  

  ![リストの例。](media\lists\create-list.png)

  また、出力としてリストを生成するアクションを使ってリストを作成することもできます。 たとえば、**ファイルからテキストを読み込む** アクションはテキスト値のリストを返すことができ、**フォルダ内のファイルを取得する** アクションは、ファイルのリストを返します。

  リストの特定の項目を取得するには、次の表記を使用します : **％VariableName\[ItemNumber\]%**

  以下の例では、フローは先に表示されたリストの最初の番号を新しい変数に格納します。 リストの最初の項目のインデックスは 0 である必要があることに注意してください。

  ![リストの最初の項目にアクセスに使用する式。](media\lists\list-first-item.png)

  一般的な方法は、**それぞれ** のアクションを使用してリストの項目を反復処理する方法です。

  [リスト データ型プロパティ](datatype-properties.md#lists)

- **データ行** - データ行には、データ テーブルの単一行の値が含まれます。 

  [データ行 データ型プロパティ](datatype-properties.md#datarows) 

- **データテーブル** - データテーブルには、表形式のデータが含まれています。 データテーブルは、プログラミング用語では 2 次元配列に相当します。 

  データテーブルには、各アイテムの位置を一意に説明する行と列が含まれています。 データテーブルは、他のデータ行をアイテムとして含むリストと見なすことができます。

  ![データテーブル変数の例。](media\data-tables\create-data-table.png)

  Power Automate Desktop は、データテーブルを直接作成するアクション方法がありまませんが、次の 3 つのアクションが出力としてデータテーブルを生成します: **Excel ワークシートから読み込む** アクション、 **SQL ステートメントを実行する** アクション、**Web ページからデータを抽出する** アクションです。

  または、**変数を設定する** アクションとプログラミング配列表記を使用してデータテーブルを作成することもできます。 

  この表記法は、カンマで区切られた複数の一次元配列を中括弧で囲んだものです。 最終的な式は、次の形式である必要があります : **%{['Product1', '10 USD'], ['Product2', '20 USD']}%**。

  ![データテーブル変数の例。](media\data-tables\create-data-table-variable.png)

  データテーブルの特定の項目を取得するには、次の表記を使用します : **%VariableName\[RowNumber\]\[ColumnNumber\]%**

  たとえば、Excel ファイルの A2 セルにアクセスするには、次の式を使用します。 **RowNumber** と **ColumnNumber** の最初の項目 (行または列) は 0 である必要があります。

  ![読み込んだ Excel ファイルの最初の行の 2 番目のセルにアクセス二使用する式。](media\data-tables\data-table-row-item.png)

  列ヘッダーを含むデータブル内の特定の列にアクセスする場合は、**%ExcelData[rowNumber]['ColumnName']** 表記を使用します。

  **それぞれ** のアクションを使用してデータテーブルをループする場合、現在の反復のデータを含む変数はデータ行と見なされます。 

  [データテーブル データ型プロパティ](datatype-properties.md#datatables) 

- **カスタム オブジェクト** – プロパティと値のペアが含まれており、簡単に JSON 形式に変換することができます。 

  新しい **カスタム オブジェクト** を作成するには、**変数の設定** アクションと次の構造式を使用します :**%{ 'Property1': 'Value1', 'Property2': 'Value2', 'Property3': 'Value2' }%**。 

  ![作成されたカスタム オブジェクト変数の例。](media\variable-data-types\create-custom-object-variable.png)

### <a name="known-issues-and-limitations"></a>既知の問題と制限事項

- **問題**: データ行とデータテーブル変数の値が変数ペインに正しく表示されない。
- **回避策**: なし。

## <a name="instances"></a>インスタンス

- **Web ブラウザー インスタンス** – **新規 Internet Explorer を起動する** などのブラウザ起動アクションで作成されたブラウザー インスタンスが含まれています。 

  [Web ブラウザー インスタンスのデータ型のプロパティ](datatype-properties.md#web-browser-instance)

- **ウィンドウ インスタンス** – **ウィンドウを取得** アクションで作成されたウィンドウのインスタンスを含みます。

  [ウィンドウ インスタンスのデータ型のプロパティ](datatype-properties.md#window-instance) 

- **Excel インスタンス**–**Excel を起動する** アクションを通じて作成された Excel インスタンスが含まれています。

  [Excel インスタンスのデータ型のプロパティ](datatype-properties.md#excel-instance) 

- **Outlook インスタンス** – **Outlook を起動する** アクションを通じて作成された Outlook インスタンスが含まれています。

## <a name="connections"></a>接続

- **SQL 接続** - **Open SQL 接続アクション** によって確立された SQL データベースへの接続が含まれています。

  [SQL 接続データ型プロパティ](datatype-properties.md#sql-connection)

- **Exchange 接続** - **Exchange サーバーに接続しする** アクションを介して確立された Exchange サーバーへの接続が含まれています。

  [Exchange 接続データ型プロパティ](datatype-properties.md#exchange-connection)

- **FTP 接続** - **Open FTP 接続** と **Open secure FTP 接続** アクションによって作成された FTP 接続が含まれています。

  [FTP 接続データ型プロパティ](datatype-properties.md#ftp-connection) 

## <a name="others"></a>その他

### <a name="active-directory"></a>Active Directory

- **Active Directory エントリ** - **サーバーへの接続** アクションによって確立された Active Directory サーバーへの接続が含まれています。
- **グループ情報** - 指定された ActiveDirectory グループに関する情報が含まれます。
- **グループ メンバー** - 指定された ActiveDirectory グループのメンバーを表します。
- **ユーザー情報** - 指定された ActiveDirectory ユーザーに関する情報が含まれます。

[Active Directory データ型のプロパティ](datatype-properties.md#active-directory-entry)

### <a name="aws"></a>AWS

- **EC2 クライアント** - **EC2 セッションの作成** アクションを介して作成された EC2 セッションが含まれています。
- **EC2 インスタンス** - 取得した EC2 インスタンスを表します。
- **EC2 インスタンス情報** - EC2 インスタンスに関する情報が含まれています。
- **インスタンスの状態の変化** - 起動または停止した EC2 インスタンスに関する情報が含まれています。
- **EBS スナップショット** - EBS スナップショットを表します。
- **EBS ボリューム** - EBSボリュームを表します。

[AWS データ型プロパティ](datatype-properties.md#ebs-snapshot) 

### <a name="azure"></a>Azure

- **Azure クライアント** - **セッションの作成** アクションを介して作成された Azure セッションが含まれています。
- **Azure リソース グループ** - 取得した Azure リソースグループを表します。
- **Azure マネージド ディスク** - 取得した Azure ディスクを表します。
- **Azure スナップショット** - Azure のスナップショットを表します。
- **Azure 仮想マシン** - 取得した Azure 仮想マシンを表します。
- **Azure 仮想マシン情報** - Azure 仮想マシンに関する情報が含まれています。
- **Azure サブスクリプション** - 取得した Azure サブスクリプションを表します。

[Azure データ型プロパティ](datatype-properties.md#azure-managed-disk) 

### <a name="cmd"></a>CMD

- **CMD セッション** - **CMD セッションを開く** アクションを介して作成された CMD セッションが含まれています。

[CMD データ型プロパティ](datatype-properties.md#cmd-session)

### <a name="dates-and-time"></a>日付と時間

- **Datetime** - 日付と時刻の情報が含まれています。 **変数アクションの設定** を介して日時変数を作成するには、次の式 **%d"yyyy-MM-dd HH:mm:ss.ff+zzz"%** に入力パラメーターを入力します:

  | 表記 | 内容 |
  |----------|-------------|
  | **yyyy** | 年        |
  | **MM**   | 月       |
  | **dd**   | 曜日         |
  | **HH**   | 時間        |
  | **mm**   | 分    |
  | **ss**   | 秒     |
  | **ff**   | ミリ秒 |
  | **zzz**  | UTC オフセット    |

[日付と時刻のデータ型のプロパティ](datatype-properties.md#dates)

### <a name="email"></a>電子メール

- **メールメッセージ** - 電子メールメッセージを表します。 **メールを取得する** アクションはこれらの変数を設定します。

[メール データ型プロパティ](datatype-properties.md#mail-messages)

### <a name="exchange"></a>Exchange

- **Exchange メール メッセージ** - Exchange サーバーから取得した電子メールメッセージを表します。 **Exchange 電子メールメッセージの取得** アクションによって生成された変数を使用します。

[Exchange 接続データ型プロパティ](datatype-properties.md#exchange-mail-messages)

### <a name="files-and-folders"></a>ファイルとフォルダ

- **ファイル** - ファイルを表します。
- **フォルダー** - フォルダーを表します。

[ファイルとフォルダーのデータ型プロパティ](datatype-properties.md#files)

### <a name="ftp"></a>FTP

- **FTP ファイル** - FTP ファイルを表します。
- **FTP ディレクトリ** - FTP ディレクトリを表します

[FTP データ型プロパティ](datatype-properties.md#ftp-files)

### <a name="ocr"></a>OCR

- **OCR エンジン** - **OCR エンジンの作成** アクションを介して作成された OCR エンジンが含まれています。

### <a name="outlook"></a>Outlook

- **Outlook メールメッセージ** - Outlook 電子メールメッセージを表します。 **Outlook 電子メールメッセージの取得** アクションによって生成された変数を使用します。

[Outlook データ型プロパティ](datatype-properties.md#outlook-mail-messages) 

### <a name="terminal"></a>ターミナル

- **ターミナル セッション** - **ターミナル セッションを開く** アクションを介して作成されたターミナル セッションが含まれています。

[ターミナル接続データ型プロパティ](datatype-properties.md#terminal-session) 

### <a name="xml"></a>XML 
- **XML ノード** - XML ドキュメントのコンテンツが含まれています。 **ファイルから XML を読み込む** アクションはこれらの変数を設定します。

[XML データ型プロパティ。](datatype-properties.md#xml-node) 