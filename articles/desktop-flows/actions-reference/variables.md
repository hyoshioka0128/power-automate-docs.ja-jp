---
title: 変数 | Microsoft Docs
description: 変数のアクションに関する参考情報
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
ms.openlocfilehash: c08fa9cfde09f88ddc69555620b8708284288117
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711611"
---
# <a name="variables"></a>変数



さまざまなデータ型のすべての変数関連アクション

|<!-- --> |
|-----|
|[数値の切り捨て](#truncatenumber)|
|[乱数の生成](#generaterandomnumber)|
|[リストのクリア](#clearlist)|
|[リストから項目を削除](#removeitemfromlist)|
|[一覧の並べ替え](#sortlistbase)|
|[リストのシャッフル](#shufflelist)|
|[リストの統合](#mergelists)|
|[リストを逆にする](#reverselist)|
|[リストから重複する項目を削除](#removeduplicateitemsfromlist)|
|[共通リスト項目の検索](#findcommonlistitems)|
|[リストの内容を減らす](#subtractlists)|
|[データ テーブル列をリストに取得](#retrievedatatablecolumnintolist)|
|[JSON をカスタム オブジェクトに変換](#convertjsontocustomobject)|
|[カスタム オブジェクトを JSON に変換](#convertcustomobjecttojson)|
|[項目をリストに追加](#additemtolist)|
|[新しいリストの作成](#createnewlist)|
|[変数を大きくする](#increasevariable)|
|[変数を小さくする](#decreasevariable)|
|[変数の設定](#assign)|

### <a name="truncate-number"></a><a name="truncatenumber"></a> 数値の切り捨て
数値の整数部分または小数部分を取得するか、値を指定された小数点以下の桁数の切り上げます

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|切り捨てる数値|無効|数値||切り捨て/切り上げを行う数値を保持する数字または変数|
|操作|N/A|整数部分を取得、小数部分を取得、丸める番号|整数部分を取得|指定された数値に対して実行する操作を指定します|
|小数点以下表示桁数|有効|数値|3|指定された数値を切り上げる小数点以下の桁数。 結果に整数を返すには、0 を入力します|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|TruncatedValue|数値|切り捨てまたは切り上げられた数値|


##### <a name="exceptions"></a><a name="truncatenumber_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="generate-random-number"></a><a name="generaterandomnumber"></a> 乱数の生成
最小値および最大値の間にある単一の乱数または乱数リストを生成

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|最小値|有効|数値|0|生成する乱数の下限|
|最大値|有効|数値|100|生成する乱数の上限|
|複数の数詞を生成|N/A|ブール値|無効|単一の乱数または乱数リストのどちらを生成するかを指定します|
|数値の数|有効|数値|10|生成する乱数の数を指定します|
|重複を許可|N/A|ブール値|無効|同じ数値が乱数リストに複数件存在することを許可するかどうかを指定します|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|RandomNumber|数値|新しく生成された乱数|
|RandomNumbers|数値の一覧|新しく生成された乱数リスト|


##### <a name="exceptions"></a><a name="generaterandomnumber_onerror"></a> 例外
|例外|内容|
|-----|-----|
|乱数を生成できませんでした|乱数の生成中にエラーが発生したことを示します|

### <a name="clear-list"></a><a name="clearlist"></a> リストをクリア
リストからすべての項目を削除

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|クリアするリスト|無効|全般値の一覧||要素を削除するリスト変数|


##### <a name="variables-produced"></a>生成された変数
このアクションは変数を生成しません


##### <a name="exceptions"></a><a name="clearlist_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="remove-item-from-list"></a><a name="removeitemfromlist"></a> リストから項目を削除
1 つまたは複数の項目をリストから削除

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|項目の削除基準|N/A|インデックス、値|インデックス|指定されたインデックスの項目と特定の値を持つ項目のどちらを削除するかを指定します|
|インデックス|無効|数値||削除する項目のインデックス番号|
|値|無効|一般の値||削除する項目|
|一致した項目をすべて削除|N/A|ブール値|無効|指定された項目に一致したすべての項目を削除します|
|削除元リスト|無効|全般値の一覧||削除する項目のあるリスト|


##### <a name="variables-produced"></a>生成された変数
このアクションは変数を生成しません


##### <a name="exceptions"></a><a name="removeitemfromlist_onerror"></a> 例外
|例外|内容|
|-----|-----|
|項目インデックスが範囲外です|項目インデックスが範囲外であることを示します|
|項目が見つかりません|項目がリストに存在しないことを示します|

### <a name="sort-list"></a><a name="sortlistbase"></a> リストを並べ替え
リストの項目を並べ替えます。 同じ種類のアイテムを使用する

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|並べ替えるリスト|無効|全般値の一覧||並べ替えるリストを保持する変数|
|リスト項目のプロパティで並べ替え|N/A|ブール値|無効|リストの項目がオブジェクト (ファイル、フォルダなど) の場合、このオプションを有効にすると、特定のプロパティで項目を並べ替えることができます。 このオプションを無効にしたままにしておくと、要素を既定のプロパティでソートします (たとえば、ファイル オブジェクトはフルパスでソートされます)|
|並べ替えの基準にする最初のプロパティ|有効|テキスト値||リストをソートする項目のプロパティ名。 各オブジェクトのプロパティ名については、ヘルプ ファイルを参照してください|
|並べ替え|N/A|照準、降順|昇順|最初のプロパティを基準に昇順および降順のどちらで並べ替えるかを指定します|
|並べ替えの基準にする 2 番目のプロパティ|有効|テキスト値||リストの並べ替えの基準にする 2 番目のプロパティの名前|
|並べ替え|N/A|照準、降順|昇順|2 番目のプロパティを基準に昇順および降順のどちらで並べ替えるかを指定します|
|並べ替えの基準にする 3 番目のプロパティ|有効|テキスト値||リストの並べ替えの基準にする 3 番目のプロパティの名前|
|並べ替え|N/A|照準、降順|昇順|3 番目のプロパティを基準に昇順および降順のどちらで並べ替えるかを指定します|


##### <a name="variables-produced"></a>生成された変数
このアクションは変数を生成しません


##### <a name="exceptions"></a><a name="sortlistbase_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="shuffle-list"></a><a name="shufflelist"></a> リストをシャッフルする
リストのランダム置換を作成

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|シャッフルするリスト|無効|全般値の一覧||シャッフルするリストを含む変数|


##### <a name="variables-produced"></a>生成された変数
このアクションは変数を生成しません


##### <a name="exceptions"></a><a name="shufflelist_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="merge-lists"></a><a name="mergelists"></a> リストの統合
2 つのリストを 1 つに結合

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|最初のリスト|無効|全般値の一覧||結合する項目の最初のリスト|
|2 番目のリスト|無効|全般値の一覧||結合する項目の 2 番目のリスト|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|OutputList|全般値の一覧|統合されたリスト。 初期リストが変更されていません|


##### <a name="exceptions"></a><a name="mergelists_onerror"></a> 例外
|例外|内容|
|-----|-----|
|指定されたリストの種類に互換性がありません|指定されたリストに互換性がないことを示します|

### <a name="reverse-list"></a><a name="reverselist"></a> リストを逆にする
リストの項目の順序を逆にする

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|逆にするリスト|無効|全般値の一覧||項目の順序を逆にするリスト|


##### <a name="variables-produced"></a>生成された変数
このアクションは変数を生成しません


##### <a name="exceptions"></a><a name="reverselist_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="remove-duplicate-items-from-list"></a><a name="removeduplicateitemsfromlist"></a> リストから重複する項目を削除
リスト内の重複する項目を削除し、リスト内の各項目を一意にします

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|重複する項目を削除するリスト|無効|全般値の一覧||重複する項目を削除するリスト変数|
|重複する項目の検索時にテキストの大文字と小文字を区別しない|N/A|ブール値|無効|重複する項目を検索するときに大文字と小文字を区別せずにテキスト比較を行うかどうかを指定します (テキスト項目で構成されたリストにのみ適用されます)|


##### <a name="variables-produced"></a>生成された変数
このアクションは変数を生成しません


##### <a name="exceptions"></a><a name="removeduplicateitemsfromlist_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="find-common-list-items"></a><a name="findcommonlistitems"></a> 共通リスト項目の検索
2 つのリストを比較して、両方に共通する項目を持つ新しいリストを作成

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|最初のリスト|無効|全般値の一覧||比較する最初のリストを含む変数|
|2 番目のリスト|無効|全般値の一覧||比較する 2 番目のリストを含む変数|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|IntersectionList|全般値の一覧|共通項目の新しいリスト|


##### <a name="exceptions"></a><a name="findcommonlistitems_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="subtract-lists"></a><a name="subtractlists"></a> リストの内容を減らす
2 つのリストを比較して、最初のリストに含まれていて 2 番目のリストに含まれていない項目を含む新しいリストを作成します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|最初のリスト|無効|全般値の一覧||比較する最初のリストを保持する変数|
|2 番目のリスト|無効|全般値の一覧||比較する 2 番目のリストを保持する変数|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|ListDifference|全般値の一覧|生成される新しいリスト|


##### <a name="exceptions"></a><a name="subtractlists_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="retrieve-data-table-column-into-list"></a><a name="retrievedatatablecolumnintolist"></a> データ テーブル列をリストに取得する
データ テーブル列の内容をリストに変換

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Data table|無効|Datatable||リストに変換する列を含むデータ テーブル|
|列名またはインデックス|無効|テキスト値||列名 (列名が定義されている場合)、または取得する列のインデックス番号|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|ColumnAsList|全般値の一覧|指定されたデータ テーブルの内容を保持する新しいリスト|


##### <a name="exceptions"></a><a name="retrievedatatablecolumnintolist_onerror"></a> 例外
|例外|内容|
|-----|-----|
|列名が存在しません|データ テーブルに列名が含まれていないことを示します|
|列インデックスが範囲外です|列インデックスが範囲外であることを示します|

### <a name="convert-json-to-custom-object"></a><a name="convertjsontocustomobject"></a>JSON をカスタム オブジェクトに変換
JSON 文字列をカスタム オブジェクトに変換

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|JSON|無効|テキスト値||カスタム オブジェクトに変換する JSON テキスト (または JSON テキストを含む以前に作成された変数)|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|JsonAsCustomObject|一般の値|指定された JSON の変換されたカスタム オブジェクト|


##### <a name="exceptions"></a><a name="convertjsontocustomobject_onerror"></a> 例外
|例外|内容|
|-----|-----|
|JSON の解析エラー|指定された JSON の解析中にエラーが発生したことを示します|

### <a name="convert-custom-object-to-json"></a><a name="convertcustomobjecttojson"></a>カスタム オブジェクトを JSON に変換
カスタム オブジェクトを JSON 文字列に変換

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|カスタム オブジェクト|無効|カスタム オブジェクト||JSON に変換するカスタム オブジェクト|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|CustomObjectAsJson|テキスト値|指定されたカスタム オブジェクトの変換された JSON|


##### <a name="exceptions"></a><a name="convertcustomobjecttojson_onerror"></a> 例外
|例外|内容|
|-----|-----|
|カスタム オブジェクトの解析エラー|カスタム オブジェクトの解析中にエラーが発生したことを示します|

### <a name="add-item-to-list"></a><a name="additemtolist"></a> 項目をリストに追加する
新しい項目をリストに追加

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|項目の追加|無効|一般の値||リストに追加する値または変数です。 複数の要素を追加する値のリストを提供します。 リストに特定のタイプの要素がある場合、新しい要素はそのタイプに変換されます|
|追加先リスト|無効|全般値の一覧||新しい要素を追加するリスト変数|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|NewList|全般値の一覧|新しいリスト|


##### <a name="exceptions"></a><a name="additemtolist_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="create-new-list"></a><a name="createnewlist"></a> 新しいリストの作成
新しい空のリストを作成

##### <a name="input-parameters"></a>入力パラメーター
- このアクションには入力は必要ありません

##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|一覧|全般値の一覧|新しいリスト|


##### <a name="exceptions"></a><a name="createnewlist_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="increase-variable"></a><a name="increasevariable"></a> 変数を増加させる
変数の値を一定量大きくする

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|変数名|無効|数値||大きくする数値|
|大きくする数値|無効|数値||変数を大きくする数値 (または数値を含む以前に作成された変数)|


##### <a name="variables-produced"></a>生成された変数
このアクションは変数を生成しません


##### <a name="exceptions"></a><a name="increasevariable_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="decrease-variable"></a><a name="decreasevariable"></a> 変数を削減する
変数の値を一定量小さくする

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|変数名|無効|数値||変数を小さくする数値 (または数値を含む以前に作成された変数)|
|小さくする数値|無効|数値||変数を小さくする数値 (または数値を含む以前に作成された変数)|


##### <a name="variables-produced"></a>生成された変数
このアクションは変数を生成しません


##### <a name="exceptions"></a><a name="decreasevariable_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="set-variable"></a><a name="assign"></a> 変数を設定する
新規や既存の変数に値を設定する、新しい変数を作成する、または以前作成した変数を上書きする

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|To|無効|*||変数に割り当てる値です|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|NewVar|*|設定する変数名|


##### <a name="exceptions"></a><a name="assign_onerror"></a> 例外
- このアクションには例外は含まれません

