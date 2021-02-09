---
title: Excel | Microsoft Docs
description: Excel のアクションについての参考情報
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
ms.openlocfilehash: e2b0871ed56f14607e518028e42a8ede50462a5b
ms.sourcegitcommit: 26d5d2f9d2dd1225f9bea725c13592cb28f33c36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "5073095"
---
# <a name="excel"></a>Excel



Excel 関連の活動を自動化

|<!-- --> |
|-----|
|[Excel マクロの実行](#runmacro)|
|[アクティブな Excel ワークシートの取得](#getactiveworksheet)|
|[すべての Excel ワークシートの取得](#getallworksheets)|
|[Excel ワークシートを削除](#deleteworksheet)|
|[Excel ワークシートの名前を変更](#renameworksheet)|
|[Excel ワークシート内のセルをアクティブ化](#activatecellinexcel)|
|[Excel ワークシート内のセルを選択](#selectcellsfromexcel)|
|[選択したセル範囲を Excel ワークシートから取得](#getselectedcellrange)|
|[Excel ワークシートからセルをコピー](#copycellsfromexcel)|
|[Excel ワークシートにセルを貼り付け](#pastecellstoexcel)|
|[Excel ワークシートに行を挿入](#insertrow)|
|[Excel ワークシートから行を削除](#deleterow)|
|[Excel ワークシートに列を挿入](#insertcolumn)|
|[Excel ワークシートから列を削除](#deletecolumn)|
|[Excel ワークシートから列における最初の空の行を取得](#getfirstfreerowoncolumn)|
|[Excel の起動](#launchexcel)|
|[実行中の Excel に添付](#attach)|
|[Excel ワークシートから読み取り](#readfromexcel)|
|[Excel の保存](#saveexcel)|
|[Excel ワークシートに書き込み](#writetoexcel)|
|[Excel を閉じる](#closeexcel)|
|[アクティブな Excel ワークシートの設定](#setactiveworksheet)|
|[新しいワークシートの追加](#addworksheet)|
|[Excel ワークシートから最初の空の列や行を取得](#getfirstfreecolumnrow)|

## <a name="advanced"></a>詳細
高度な Excel オートメーション アクション
### <a name="run-excel-macro"></a><a name="runmacro"></a> Excel のマクロを実行する
Excel インスタンスのドキュメントで指定されたマクロを実行します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||作業対象の Excel インスタンスです。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|マクロ|無効|テキスト値||実行するマクロです。 テキストは、マクロの名前の後に引数 (任意) を続け、すべてセミコロンで区切ったものになります|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="runmacro_onerror"></a> 例外
|例外|内容|
|-----|-----|
|マクロを実行できませんでした|指定されたマクロの実行時に問題が発生したことを示します|

### <a name="get-active-excel-worksheet"></a><a name="getactiveworksheet"></a> アクティブな Excel ワークシートを取得する
Excel ドキュメントのアクティブなワークシートを取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||作業対象の Excel インスタンスです。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|SheetName|テキスト値|アクティブなワークシートの名前|
|SheetIndex|数値|アクティブなワークシートのインデックス|


##### <a name="exceptions"></a><a name="getactiveworksheet_onerror"></a> 例外
|例外|内容|
|-----|-----|
|アクティブなワークシートを取得できませんでした|アクティブなワークシートを取得するときに問題が発生したことを示します|

### <a name="get-all-excel-worksheets"></a><a name="getallworksheets"></a> すべての Excel ワークシートを取得する
Excel ドキュメントのすべてのワークシート名を取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||Excel のインスタンスを指定します。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|SheetNames|テキスト値の一覧|すべてのワークシートの名前|


##### <a name="exceptions"></a><a name="getallworksheets_onerror"></a> 例外
|例外|内容|
|-----|-----|
|すべてのワークシート名を取得できませんでした|Excel ワークシートの名前を取得するときに問題が発生したことを示します|

### <a name="delete-excel-worksheet"></a><a name="deleteworksheet"></a> Excel ワークシートを削除する
Excel インスタンスから特定のワークシートを削除します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||作業対象の Excel インスタンスです。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|次と共にワークシートを削除|N/A|インデックス、名前|件名|名前またはインデックスでワークシートを検索するかどうか|
|ワークシート インデックス|無効|数値||削除するワークシートのインデックス番号です。 付番は 1 から始まります。最初のワークシートのインデックスが 1、2 番目のワークシートが 2 となります。|
|ワークシート名|無効|テキスト値||削除するワークシートの名前|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="deleteworksheet_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ワークシートが見つかりません|指定された名前のワークシートが見つからなかったことを示します|
|ワークシートを削除できませんでした|指定されたワークシートの削除中に問題が発生したことを示します|

### <a name="rename-excel-worksheet"></a><a name="renameworksheet"></a> Excel ワークシートの名称変更
Excel インスタンスの特定のワークシートの名前を変更します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||Excel のインスタンスを指定します。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|ワークシートの名前を次に変更|N/A|インデックス、名前|件名|名前またはインデックスでワークシートを検索するかどうかを指定|
|ワークシート インデックス|無効|数値||名称変更するワークシートのインデックスです。 付番は 1 から始まります。最初のワークシートのインデックスが 1、2 番目のワークシートが 2 となります。|
|ワークシート名|無効|テキスト値||名前を変更するワークシートの名前|
|ワークシートの新しい名前|無効|テキスト値||ワークシートの新しい名前|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="renameworksheet_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ワークシートが見つかりません|指定された名前のワークシートが見つからなかったことを示します|
|ワークシートの名前を変更できませんでした|指定されたワークシートの名前を変更するときに問題が発生したことを示します|

### <a name="activate-cell-in-excel-worksheet"></a><a name="activatecellinexcel"></a> xcel ワークシートのアクティブなセル
Excel インスタンスのアクティブなワークシート内のセル (列、行、オフセットを指定) をアクティブ化します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||作業対象の Excel インスタンスを指定します。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|アクティブ化します|N/A|絶対指定セル、相対指定セル|絶対位置で指定したセル|現在アクティブな参照セルと実際のアクティブ化セルの間のセル数であるオフセット距離を使って、セルを絶対値と相対値のどちらでアクティブ化するかを選択します|
|Column|無効|テキスト値||セル列の数値または文字|
|通信方向|N/A|左、右、上、下|左へ移動|オフセットの方向を選択します。 現在アクティブなセルの位置に基づいて、アクティブにするセルを探す場所を選択します|
|アクティブなセルからのオフセット|無効|数値||現在アクティブなセルと目的のセルとの間のセル単位の距離です。 付番は 0 から開始します|
|行|無効|数値||セル行の数値です。 付番は 1 から開始します|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="activatecellinexcel_onerror"></a> 例外
|例外|内容|
|-----|-----|
|セルをアクティブ化できませんでした|Excel セルをアクティブ化する際に問題が発生したことを示します|

### <a name="select-cells-in-excel-worksheet"></a><a name="selectcellsfromexcel"></a> Excel ワークシートのセルを選択する
セルの範囲を Excel インスタンスのアクティブなワークシートで選択します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||作業対象の Excel インスタンスです。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|Select|N/A|絶対指定セル、相対指定セル|絶対位置で指定したセル|明示的に指定されたセル範囲を選択するか、現在のアクティブ セルに対して相対的にセル範囲を設定するかを指定|
|X 軸方向|N/A|左、右|左へ移動|X 軸のオフセットの方向です。 現在アクティブになっているセルの位置に基づいて、水平軸上のどこを探すか|
|先頭列|無効|テキスト値||最初の列のインデックスまたは文字|
|X オフセット|無効|数値||X 軸オフセット|
|先頭行|無効|数値||最初の行の数値です。 付番は 1 から開始します|
|最終列|無効|テキスト値||最後の列のインデックスまたは文字|
|Y 軸方向|N/A|上、下|上|Y 軸のオフセットの方向です。 現在アクティブになっているセルの位置に基づいて、縦軸上のどこを探すか|
|最終行|無効|数値||最後の行の数値です。 付番は 1 から開始します|
|Y オフセット|無効|数値||Y 軸オフセット|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="selectcellsfromexcel_onerror"></a> 例外
|例外|内容|
|-----|-----|
|セルを選択できませんでした|指定されたセルの選択中に問題が発生したことを示します|

### <a name="get-selected-cell-range-from-excel-worksheet"></a><a name="getselectedcellrange"></a> Excel ワークシートの選択したセルの範囲を取得する
最初の列、最初の行、最後の列、最後の行で構成される構造内における、選択されたセル範囲を取得

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||作業対象の Excel インスタンスです。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|FirstColumnIndex|数値|範囲の最初の列の数値|
|FirstRowIndex|数値|範囲の最初の行の数値|
|LastColumnIndex|数値|範囲の最後の列の数値|
|LastRowIndex|数値|範囲の最後の行の数値|


##### <a name="exceptions"></a><a name="getselectedcellrange_onerror"></a> 例外
|例外|内容|
|-----|-----|
|選択したセル範囲を取得できませんでした|選択したセル範囲の取得時に問題が発生したことを示します|

### <a name="copy-cells-from-excel-worksheet"></a><a name="copycellsfromexcel"></a> Excel ワークシートからセルをコピーする
セルの範囲を Excel インスタンスのアクティブなワークシートからコピーします

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||作業対象の Excel インスタンスです。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|コピー モード|N/A|単一セルの値、範囲選択したセルの値、選択範囲の値|単一セルの値|単一セル、セルの範囲、現在の選択されているセルのどれをコピーするかを指定|
|先頭列|無効|テキスト値||最初の列のインデックスまたは文字|
|先頭行|無効|数値||最初の行のインデックス|
|最終列|無効|テキスト値||最後の列のインデックスまたは文字|
|最終行|無効|数値||最後の行のインデックス|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="copycellsfromexcel_onerror"></a> 例外
|例外|内容|
|-----|-----|
|セルをコピーできませんでした|Excel ドキュメントからセルをコピーする際に問題が発生したことを示します|

### <a name="paste-cells-to-excel-worksheet"></a><a name="pastecellstoexcel"></a> Excel ワークシートからセルを貼り付ける
セルの範囲を Excel インスタンスのアクティブなワークシートに貼り付けます

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||Excel のインスタンスを指定します。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|貼り付けモード|N/A|指定したセル上、現在アクティブなセル上|指定したセル上|指定したセルまたは現在アクティブなセルに貼り付けるかどうかを指定|
|Column|無効|テキスト値||セル列のインデックスまたは文字|
|行|無効|数値||行番号|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="pastecellstoexcel_onerror"></a> 例外
|例外|内容|
|-----|-----|
|セルを貼り付けることができませんでした|指定されたセルの貼り付け時に問題が発生したことを示します|

### <a name="insert-row-to-excel-worksheet"></a><a name="insertrow"></a> Excel ワークシートに行を挿入する
Excel インスタンスの選択した行の上に行を挿入します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||作業対象の Excel インスタンスです。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|行インデックス|無効|数値||上方向に新しい行を追加する行のインデックスです。 付番は 1 から開始します|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="insertrow_onerror"></a> 例外
|例外|内容|
|-----|-----|
|行が見つかりません|指定されたインデックスの列が見つからなかったことを示します|
|行を挿入できませんでした|指定された Excel インスタンスに行を挿入するときに問題が発生したことを示します|

### <a name="delete-row-from-excel-worksheet"></a><a name="deleterow"></a> Excel ワークシートの行を削除する
Excel インスタンスから選択した行を削除します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||Excel のインスタンスです。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|行の削除|無効|数値||削除する行のインデックス番号です。 付番は 1 から開始します|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="deleterow_onerror"></a> 例外
|例外|内容|
|-----|-----|
|行が見つかりません|指定されたインデックスの列が見つからなかったことを示します|
|行を削除できませんでした|指定された行の削除中に問題が発生したことを示します|

### <a name="insert-column-to-excel-worksheet"></a><a name="insertcolumn"></a> Excel ワークシートに列を挿入する
Excel インスタンスで選択されている列の左側に列を挿入します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||作業対象の Excel インスタンスです。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|Column|無効|テキスト値||列のインデックス番号または文字です。 表示された列の左側に新しい列が表示されます|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="insertcolumn_onerror"></a> 例外
|例外|内容|
|-----|-----|
|列が見つかりません|指定された名前の列が見つからなかったことを示します|
|列を挿入できませんでした|指定された Excel インスタンスに列を挿入するときに問題が発生したことを示します|

### <a name="delete-column-from-excel-worksheet"></a><a name="deletecolumn"></a> Excel ワークシートの列を削除する
Excel インスタンスから選択した列を削除します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||作業対象の Excel インスタンスです。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|列の削除|無効|テキスト値||削除する列のインデックス番号または文字|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="deletecolumn_onerror"></a> 例外
|例外|内容|
|-----|-----|
|列が見つかりません|指定された名前の列が見つからなかったことを示します|
|列を削除できませんでした|指定された列の削除中に問題が発生したことを示します|

### <a name="get-first-free-row-on-column-from-excel-worksheet"></a><a name="getfirstfreerowoncolumn"></a> Excel ワークシートから列の最初の空き行を取得する
アクティブなワークシートの列を指定して、最初の空の行を取得

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||Excel のインスタンスを指定します。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|Column|無効|テキスト値||列を特定するインデックスまたは文字です。 列の付番は 1 から開始します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|FirstFreeRowOnColumn|数値|指定された列の完全に空の最初の行を表す数値|


##### <a name="exceptions"></a><a name="getfirstfreerowoncolumn_onerror"></a> 例外
|例外|内容|
|-----|-----|
|最初の空の行を取得できませんでした|Excel インスタンスの最初の空の行を取得しているときに問題が発生したことを示します|

### <a name="launch-excel"></a><a name="launchexcel"></a>Excel を起動します
新しい Excel インスタンスを起動するか、Excel ドキュメントを開きます

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel の起動|N/A|空白のドキュメントで、以下のドキュメントを開きます|空のドキュメントを使用|新しい Excel ドキュメントを開くか、既存のドキュメントを開くかを指定します|
|ドキュメント パス|無効|ファイル||開く既存の Excel ドキュメントの完全なパス|
|インスタンスを表示する|N/A|ブール値|有効|Excel ウィンドウを表示するかどうかを指定|
|パスワード|有効|暗号化された値||パスワードで保護されている場合は、Excel ドキュメントのパスワード|
|読み取り専用として開く|N/A|ブール値|無効|保存されているドキュメントを読み取り専用モードで開くかどうかを指定|
|アドインとマクロの読み込み|N/A|ブール値|無効|新しい Excel インスタンスにアドインとマクロを読み込むかどうかを指定|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|ExcelInstance|Excel インスタンス|後続の Excel アクションで使用する特定の Excel インスタンスです。 これにより、ユーザーは複数の Excel スプレッドシートのうち、どのシートにアクセスするかを指定することができます|


##### <a name="exceptions"></a><a name="launchexcel_onerror"></a> 例外
|例外|内容|
|-----|-----|
|Excel を起動できませんでした|Excel インスタンスを起動するときに問題が発生したことを示します|
|Excel ドキュメントを開くことができませんでした|指定された Excel ドキュメントを開くときに問題が発生したことを示します|

### <a name="attach-to-running-excel"></a><a name="attach"></a>実行中の Excel に添付する
既に開いている Excel ドキュメントに添付します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ドキュメント名|無効|ファイル||添付先の Excel ドキュメントの名前またはパス|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|ExcelInstance|Excel インスタンス|今後の Excel アクションで使うためにこのアクションが添付された Excel インスタンス|


##### <a name="exceptions"></a><a name="attach_onerror"></a> 例外
|例外|内容|
|-----|-----|
|指定された Excel ドキュメントが見つかりません|指定された Excel ドキュメントが見つからなかったことを示します|
|Excel ドキュメントに添付できませんでした|Excel ドキュメントに添付するときに問題が発生したことを示します|

### <a name="read-from-excel-worksheet"></a><a name="readfromexcel"></a> Excel ワークシートから読み取る
Excel インスタンスのアクティブなワークシートからセルまたはセル範囲の値を読み取ります

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||作業対象の Excel インスタンスです。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|取得|N/A|単一セルの値、範囲選択したセルの値、選択範囲の値|単一セルの値|単一セルの値を取得するか、セル範囲からテーブルを取得するか|
|先頭列|無効|テキスト値||セル列 (単一セルの値) または最初の列を数値または文字として|
|先頭行|無効|数値||セル行 (単一セルの値) または最初の行番号|
|最終列|無効|テキスト値||数値または文字としての最後の列|
|最終行|無効|数値||最後の行番号|
|セルの内容をテキストとして取得|N/A|ブール値|無効|セルの内容を純粋なテキストとして取得するか、最も近い種類 (日付の場合は日時、数字の場合は数値) として取得するかを指定します。|
|範囲の最初の行に列名が含まれています|N/A|ブール値|無効|最初の行を列の名称とするかどうかを指定します。 この場合、名前はテーブルにデータとして読み込まれず、後続のアクションでは列名でデータを検索することができます|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|ExcelData|一般の値|単一セルの値|
|ExcelData|Datatable|セル範囲の値を DataTable として|


##### <a name="exceptions"></a><a name="readfromexcel_onerror"></a> 例外
|例外|内容|
|-----|-----|
|セルの値を読み取れませんでした|指定された Excel セルの値を読み取り中に問題が発生したことを示します|

### <a name="save-excel"></a><a name="saveexcel"></a> Excel の保存
既に起動している Excel インスタンスを保存します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||保存する Excel のインスタンスです。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|保存モード|N/A|ドキュメントの保存、ドキュメントを名前を付けて保存|ドキュメントを保存|このインスタンスのドキュメントを保存する方法|
|ドキュメント形式|N/A|既定 (拡張子に由来)、 Excel ワークブック (.xlsx)、マクロが有効化された Excel ワークブック (.xlsm)、 Excel 97-2003 ワークブック (.xls)、 Web ページ (.htm、 .html)、 Excel テンプレート (.xltx)、マクロが有効化された Excel テンプレート (.xltm)、 Excel 97-2003 テンプレート (.xlt)、 テキスト (.txt)、 ユニコード テキスト (.txt)、Macintosh テキスト (.txt)、 DOS テキスト (.txt)、 XML スプレッドシート (.xml)、 Excel 95 (.xls)、 CSV (.csv)、 DIF (.dif)、 SYLK (.slk)、 Excel アドイン (.xlam)、 Excel 97-2003 アドイン (.xla)、 Strict Open XML ワークブック (.xlsx)、 OpenDocument スプレッドシート (.ods)|既定 (拡張機能から)|ドキュメントを保存する形式|
|ドキュメント パス|無効|ファイル||ドキュメントを保存する完全なパス|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="saveexcel_onerror"></a> 例外
|例外|内容|
|-----|-----|
|Excel ドキュメントを保存できませんでした|Excel ドキュメントを保存するときに問題が発生したことを示します|

### <a name="write-to-excel-worksheet"></a><a name="writetoexcel"></a> Excel ワークシートに書き込む
Excel インスタンスのセルまたはセル範囲に値を書き込みます

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||作業対象の Excel インスタンスです。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|書き込む値|無効|一般の値||テキストの入力、挿入する番号または変数です。 変数にテーブルが含まれている場合、必要に応じて他のセルのデータを上書きして右と下のセルに記入し、リストは下のセルに記入します|
|書き込みモード|N/A|指定したセル上、現在アクティブなセル上|指定したセル上|指定したセルまたは現在アクティブなセルに書き込むかどうか|
|Column|無効|テキスト値||書き込むセルの列番号または文字|
|行|無効|数値||書き込み先のセルの行です。 付番は 1 から始まります。最初のワークシートのインデックスが 1、2 番目のワークシートが 2 となります。|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="writetoexcel_onerror"></a> 例外
|例外|内容|
|-----|-----|
|Excel に値を書き込めませんでした|指定された値を Excel インスタンスに書き込むときに問題が発生したことを示します|

### <a name="close-excel"></a><a name="closeexcel"></a> Excel を閉じる
Excel インスタンスを閉じます

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||閉じる Excel のインスタンスです。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|Excel を閉じる前|N/A|ドキュメントを保存しない、ドキュメントを保存する、名前を付けてドキュメントを保存する|ドキュメントを保存しない|インスタンスを閉じる前にこのインスタンスのドキュメントを保存するかどうかとその方法|
|ドキュメント形式|N/A|既定 (拡張子に由来)、 Excel ワークブック (.xlsx)、マクロが有効化された Excel ワークブック (.xlsm)、 Excel 97-2003 ワークブック (.xls)、 Web ページ (.htm、 .html)、 Excel テンプレート (.xltx)、マクロが有効化された Excel テンプレート (.xltm)、 Excel 97-2003 テンプレート (.xlt)、 テキスト (.txt)、 ユニコード テキスト (.txt)、Macintosh テキスト (.txt)、 DOS テキスト (.txt)、 XML スプレッドシート (.xml)、 Excel 95 (.xls)、 CSV (.csv)、 DIF (.dif)、 SYLK (.slk)、 Excel アドイン (.xlam)、 Excel 97-2003 アドイン (.xla)、 Strict Open XML ワークブック (.xlsx)、 OpenDocument スプレッドシート (.ods)|既定 (拡張機能から)|ドキュメントの形式|
|ドキュメント パス|無効|ファイル||ドキュメントの完全なパス|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="closeexcel_onerror"></a> 例外
|例外|内容|
|-----|-----|
|Excel ドキュメントを保存できませんでした|Excel ドキュメントを保存するときに問題が発生したことを示します|
|Excel インスタンスを閉じることができませんでした|Excel インスタンスを閉じるときに問題が発生したことを示します|

### <a name="set-active-excel-worksheet"></a><a name="setactiveworksheet"></a> アクティブな Excel ワークシートを設定する
Excel インスタンスの特定のワークシートをアクティブ化します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||Excel のインスタンスを指定します。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|次と共にワークシートをアクティブ化|N/A|インデックス、名前|件名|名前またはインデックスでワークシートを検索するかどうかを指定|
|ワークシート インデックス|無効|数値||有効化するワークシートのインデックス番号です。 付番は 1 から始まります。最初のワークシートのインデックスが 1、2 番目のワークシートが 2 となります。|
|ワークシート名|無効|テキスト値||アクティブ化するワークシートの名前|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="setactiveworksheet_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ワークシートが見つかりません|指定された名前のワークシートが見つからなかったことを示します|
|ワークシートをアクティブ化できませんでした|指定されたワークシートをアクティブ化するときに問題が発生したことを示します|

### <a name="add-new-worksheet"></a><a name="addworksheet"></a> 新規ワークシート追加
Excel インスタンスのドキュメントに新しいワークシートを追加します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||Excel のインスタンスを指定します。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|
|新しいワークシート名|無効|テキスト値||新しいワークシートの名前を指定します|
|名前を付けてワークシートを追加|N/A|最初のワークシート、最後のワークシート|最初のワークシート|既存のワークシートの前後に新しい Excel ワークシートを追加するかどうかを指定します|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="addworksheet_onerror"></a> 例外
|例外|内容|
|-----|-----|
|同じ名前のワークシートが既に存在します|同じ名前のワークシートが既に存在するため、ワークシートを追加できなかったことを示します|
|ワークシートを追加できませんでした|ワークシートを追加するときに問題が発生したことを示します|

### <a name="get-first-free-columnrow-from-excel-worksheet"></a><a name="getfirstfreecolumnrow"></a> Excel ワークシートから空いている最初の列/行を取得する
アクティブなワークシートの最初の空き列および/または行を取得します。 これは、すでにデータが入っているワークシートに新しいデータを追加する場合に便利です

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Excel インスタンス|無効|Excel インスタンス||Excel のインスタンスを指定します。 この変数は、起動する Excel のアクションで事前に特定されている必要があります|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|FirstFreeColumn|数値|最初に完全に空になった列の数値です。 たとえば、F 列が最初の空の列の場合は、'6' が格納されます|
|FirstFreeRow|数値|完全に空の最初の行の数値。 たとえば、7 行目が最初の空の行の場合は、'7' が格納されます|


##### <a name="exceptions"></a><a name="getfirstfreecolumnrow_onerror"></a> 例外
|例外|内容|
|-----|-----|
|最初の空の列/行を取得できませんでした|Excel インスタンスの最初の空の列/行を取得しているときに問題が発生したことを示します|

