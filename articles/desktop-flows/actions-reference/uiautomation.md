---
title: UI のオートメーション | Microsoft Docs
description: UI のオートメーション アクションについての参考情報
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
ms.openlocfilehash: be9ea7193445c5c4e4d8e339225f007b6924a127
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711613"
---
# <a name="ui-automation"></a>UI オートメーション



デスクトップ/Windows アプリケーションを操作する

UI のオートメーション アクションの使用方法の詳細については、[こちら](../desktop-automation.md)を参照してください

|<!-- --> |
|-----|
|[ウィンドウの詳細を取得する](#getwindowdetails)|
|[ウィンドウにある UI 要素の詳細を取得する](#getelementdetails)|
|[ウィンドウにある選択済みチェック ボックスを取得する](#getselectedcheckboxesinwindow)|
|[ウィンドウにある選択済みラジオ ボタンを取得する](#getselectedradiobuttoninwindow)|
|[ウィンドウからデータを抽出する](#extractdatafromwindow)|
|[ウィンドウ内のテキスト フィールドをフォーカス](#focustextfield)|
|[ウィンドウ内のテキスト フィールドに入力する](#populatetextfield)|
|[ウィンドウ内のボタンを押す](#pressbutton)|
|[ウィンドウのラジオ ボタンをオンにする](#selectradiobutton)|
|[ウィンドウのチェック ボックスの状態を設定](#setcheckboxstate)|
|[ウィンドウでドロップ ダウン リストの値を設定する](#setdropdownlistvalueinwindow)|
|[ウィンドウの取得](#getwindowbase)|
|[ウィンドウにフォーカスする](#focuswindowbase)|
|[ウィンドウの状態の設定](#setwindowstatebase)|
|[ウィンドウの表示方法を設定する](#setwindowvisibilitybase)|
|[ウィンドウの移動](#movewindowbase)|
|[ウィンドウのサイズ変更](#resizewindowbase)|
|[ウィンドウを閉じる](#closewindowbase)|
|[デスクトップを使用する](#usedesktop)|
|[ウィンドウでタブを選択する](#selecttab)|
|[ウィンドウの UI 要素をクリックする](#click)|
|[ウィンドウ内のメニュー オプションを選択する](#selectmenuoption)|
|[UI 要素をウィンドウ内にドラッグ アンド ドロップする](#draganddropelement)|
|[ウィンドウ内のツリー ノードを展開/折りたたむ](#expandcollapsetreenode)|

## <a name="data-extraction"></a>データ抽出
単一の値からテーブルまたは複数のカスタム データまで、デスクトップ アプリケーションからデータを抽出します
### <a name="get-details-of-window"></a><a name="getwindowdetails"></a> ウィンドウの詳細を取得する
ウィンドウのタイトルやソース テキストなどのプロパティを取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ウィンドウ|無効|UIControl||詳細を取得するウィンドウ|
|ウィンドウ プロパティ|N/A|ウィンドウ タイトルの取得、ウィンドウ テキストの取得、ウィンドウの場所とサイズの取得、プロセス名の取得|ウィンドウ タイトルを取得する|抽出するウィンドウのプロパティを選択|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|WindowProperty|一般の値|取得するウィンドウの情報|


##### <a name="exceptions"></a><a name="getwindowdetails_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ウィンドウのプロパティを取得できません|ウィンドウ プロパティを取得するときに問題が発生したことを示します|

### <a name="get-details-of-a-ui-element-in-window"></a><a name="getelementdetails"></a> ウィンドウ内の UI 要素の詳細を取得する
ウィンドウにある UI 要素の属性値を取得する

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|UI 要素|無効|UIControl||詳細を取得する UI 要素|
|属性名|有効|テキスト値|独自のテキスト|値を取得する属性|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|AttributeValue|テキスト値|UI 要素のテキストの値|


##### <a name="exceptions"></a><a name="getelementdetails_onerror"></a> 例外
|例外|内容|
|-----|-----|
|UI 要素の属性を取得できません|UI 要素の属性の取得中に発生した問題を示します|

### <a name="get-selected-checkboxes-in-window"></a><a name="getselectedcheckboxesinwindow"></a> ウィンドウ内の選択済みチェック ボックスを取得する
チェック ボックス グループ内のオンになったチェック ボックスの名前、または特定のチェック ボックスの状態を取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|UI 要素|無効|UIControl||チェック ボックスまたはチェック ボックス グループ|
|操作|N/A|グループ内の選択されたチェックボックスの名前を取得する、チェックボックスの状態を取得する|グループ内の選択済みチェック ボックスの名前を取得する|複数のオンになったチェック ボックスの状態を取得するか、1 つのチェック ボックスの状態のみ取得するかを指定|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|IsChecked|ブール値|オンになったチェック ボックスの状態|
|SelectedCheckboxes|テキスト値の一覧|指定されたチェック ボックス グループ内のオンになったチェック ボックスの名前|


##### <a name="exceptions"></a><a name="getselectedcheckboxesinwindow_onerror"></a> 例外
|例外|内容|
|-----|-----|
|チェック ボックスの状態を取得できません|指定したチェック ボックスの状態の取得中に問題が発生したことを示します|

### <a name="get-selected-radio-button-in-window"></a><a name="getselectedradiobuttoninwindow"></a> ウィンドウ内の選択済みラジオ ボタンを取得する
ラジオ ボタン グループ内のオンになったラジオ ボタンの名前、または特定のラジオ ボタンの状態を取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|UI 要素|無効|UIControl||ラジオ ボタンまたはラジオ ボタン グループ|
|操作|N/A|グループ内の選択されたラジオ ボタン名を取得する、ラジオ ボタンの状態を取得する|グループにある選択済みラジオボタンの名前を取得する|ラジオ ボタン グループで選択済みのラジオ ボタン名を取得するか、1 つのラジオ ボタンの状態のみを取得するかを指定する|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|IsSelected|ブール値|オンになったラジオ ボタンの状態|
|SelectedRadiobutton|テキスト値|指定したラジオ グループ内の選択したラジオ ボタン|


##### <a name="exceptions"></a><a name="getselectedradiobuttoninwindow_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ラジオ ボタンの状態を取得できません|指定したラジオ ボタンの状態の取得中に問題が発生したことを示します|

### <a name="extract-data-from-window"></a><a name="extractdatafromwindow"></a> ウィンドウからデータを抽出する
単一の値、リスト、またはテーブルの形式で、ウィンドウの特定の部分からデータを抽出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ウィンドウ|無効|UIControl||データ抽出元ウィンドウ|
|抽出したデータの保存場所|N/A|Excel スプレッドシート、変数|Excel スプレッドシート|抽出されたデータの保存場所を指定します|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|ExcelInstance|Excel インスタンス|抽出されたデータを含む Excel インスタンスです。 このインスタンスは、専用の Excel アクションを使ってスプレッドシートを操作する (または保存して閉じる) ために使用します。|
|DataFromWindow|一般の値|datatable の形式の抽出したデータ|


##### <a name="exceptions"></a><a name="extractdatafromwindow_onerror"></a> 例外
|例外|内容|
|-----|-----|
|抽出に失敗しました|指定されたウィンドウからデータを抽出するときに問題が発生したことを示します|

## <a name="form-filling"></a>フォーム入力
デスクトップ アプリケーションのフォームに入力
### <a name="focus-text-field-in-window"></a><a name="focustextfield"></a> ウィンドウ内のテキスト フィールドをフォーカスする
ウィンドウのテキスト ボックスにフォーカスを設定し、スクロールして表示します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|テキスト フィールド|無効|UIControl||フォーカスするテキスト ボックス|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="focustextfield_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ウィンドウ テキスト ボックスに入力フォーカスを設定できません|指定された Web ページのテキスト フィールドにフォーカスを設定するときに問題が発生したことを示します|

### <a name="populate-text-field-in-window"></a><a name="populatetextfield"></a> ウィンドウ内のテキスト フィールドに入力する
ウィンドウ内のテキスト ボックスに指定されたテキストを入力します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|テキスト ボックス|無効|UIControl||入力するテキスト ボックス|
|入力するテキスト|無効|暗号化された値||テキスト フィールドに入力するテキスト|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="populatetextfield_onerror"></a> 例外
|例外|内容|
|-----|-----|
|テキスト ボックスに書き込めません|指定されたテキスト フィールドへの入力に問題があることを示します|

### <a name="press-button-in-window"></a><a name="pressbutton"></a> ウィンドウ内のボタンを押す
ウィンドウ ボタンを押します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|UI 要素|無効|UIControl||押すボタン|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="pressbutton_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ボタンを押せません|指定されたボタンを押すときに問題が発生したことを示します|

### <a name="select-radio-button-in-window"></a><a name="selectradiobutton"></a> ウィンドウのラジオ ボタンをオンにする
ウィンドウのラジオ ボタンを選択します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ラジオ ボタン|無効|UIControl||選択するラジオ ボタン|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="selectradiobutton_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ラジオ ボタン UI 要素を選択できません|指定したラジオ ボタン UI 要素の選択中に発生した問題を示します|

### <a name="set-checkbox-state-in-window"></a><a name="setcheckboxstate"></a> ウィンドウのチェック ボックスの状態を設定する
ウィンドウ フォームのチェック ボックスをオンまたはオフにします

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|チェックボックス|無効|UIControl||状態を設定するチェック ボックス|
|チェックボックスの状態を以下に設定する|N/A|オン、オフ|チェック済み|チェック ボックスがオンになるかどうかを指定|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="setcheckboxstate_onerror"></a> 例外
|例外|内容|
|-----|-----|
|チェック ボックスの状態を設定できません|指定したチェック ボックスの状態の設定中に問題が発生したことを示します|

### <a name="set-drop-down-list-value-in-window"></a><a name="setdropdownlistvalueinwindow"></a> ウィンドウでドロップ ダウン リストの値を設定する
ウィンドウ フォームのドロップダウン リストで選択されているオプションを設定するかクリアします

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ドロップダウン リスト|無効|UIControl||値を設定するドロップダウン リスト|
|操作|N/A|選択したオプションをクリアする、名前でオプションを選択する、インデックスでオプションを選択する|選択したオプションをクリア|値を名前または順序位置 (1 2 3 ...) で選択するか、ドロップダウン リストの選択された値をクリアするかを指定します|
|オプション インデックス|無効|テキスト値||1 から始まるインデックス (例: 1 3 4) をスペースで区切ったリスト|
|オプション名|無効|テキスト値||ドロップダウン リストで選択する 1 つ以上のオプション (複数ある場合は 1 行に 1 つ)。 複数のオプションは、複数選択リストを操作する場合にのみ意味があります。 リストが単一選択の場合、指定された最初のオプションのみが使用されます。|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="setdropdownlistvalueinwindow_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ドロップダウン リストで指定されたオプションを選択できませんでした|ドロップ ダウン リストで指定されたオプションを選択する際に問題が発生したことを示します|

## <a name="windows"></a>窓
サイズ、状態の表示、フォーカスに関する Windows 操作
### <a name="get-window"></a><a name="getwindowbase"></a> ウィンドウの取得
デスクトップ アプリケーションを自動化するため、実行中のウィンドウを取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ウィンドウの取得|N/A|特定のウィンドウ、前景ウィンドウ|特定のウィンドウ|セレクターまたはフォアグラウンド ウィンドウのどちらを使って検索するかを指定|
|UI 要素|無効|UIControl||取得するウィンドウのセレクター|
|ウィンドウを前面に表示する|N/A|ブール値|無効|取得したときにウィンドウを自動的にフォアグラウンドに表示するかどうかを指定|
|ウィンドウが見つからない場合は失敗する|N/A|ブール値|有効|ウィンドウが表示されるまで無期限に待機するか、設定した時間内にウィンドウが表示されない場合は失敗するかを指定する|
|タイムアウト|無効|数値||タイムアウトまでの待機秒数|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|WindowTitle|テキスト値|フォアグラウンド ウィンドウのタイトル|
|AutomationWindow|ウィンドウ インスタンス|後で UI オートメーション アクションを実行するときに使う特定のウィンドウ インスタンス|


##### <a name="exceptions"></a><a name="getwindowbase_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ウィンドウを取得できません|ウィンドウを取得するときに問題が発生したことを示します|

### <a name="focus-window"></a><a name="focuswindowbase"></a> ウィンドウをフォーカスする
特定のウィンドウをアクティブ化してフォアグラウンドに表示します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ウィンドウの検索モード|N/A|ウィンドウの UI 要素ごと、ウィンドウ インスタンス/ハンドルごと、タイトル/クラスごと|ウィンドウの UI 要素ごと|ウィンドウの検索に UI 要素を使用するか、ウィンドウのタイトル/クラスの組み合わせを使用するかを指定する|
|ウィンドウ|無効|UIControl||ウィンドウ UI 要素|
|ウィンドウ タイトル|有効|テキスト値||ウィンドウ タイトル。 '?' や '*' のワイルドカードを使用できます。|
|ウィンドウ インスタンス|無効|数値||フォーカスするウィンドウのインスタンスまたはハンドル|
|ウィンドウ クラス|有効|テキスト値||同じタイトルのウィンドウが 2 つある場合、ウィンドウ クラスはそれらを区別するのに役立つかもしれません。 この場合、使用するウィンドウのクラスを入力します。|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="focuswindowbase_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ウィンドウが見つかりません|指定したウィンドウが見つからなかったことを示します|
|ウィンドウにフォーカスできません|指定されたウィンドウをフォーカスするときに問題が発生したことを示します|
|非インタラクティブ モードでウィンドウ関連のアクションを実行できません|非インタラクティブ モードでウィンドウに関連するアクションを実行しているときに問題が発生したことを示します|

### <a name="set-window-state"></a><a name="setwindowstatebase"></a> ウィンドウの状態の設定
特定のウィンドウを復元、最大化、または最小化します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ウィンドウの検索モード|N/A|ウィンドウの UI 要素ごと、ウィンドウ インスタンス/ハンドルごと、タイトル/クラスごと|ウィンドウの UI 要素ごと|ウィンドウの検索に UI 要素を使用するか、ウィンドウのタイトル/クラスの組み合わせを使用するかを指定する|
|ウィンドウ|無効|UIControl||ウィンドウ UI 要素|
|ウィンドウ タイトル|有効|テキスト値||ウィンドウ タイトル。 '?' や '*' のワイルドカードを使用できます。|
|ウィンドウ インスタンス|無効|数値||状態を設定するウィンドウのインスタンスまたはハンドル|
|ウィンドウ クラス|有効|テキスト値||同じタイトルのウィンドウが 2 つある場合、ウィンドウ クラスはそれらを区別するのに役立つかもしれません。 この場合、使用するウィンドウのクラスを入力します。|
|ウィンドウの状態|N/A|復元、最大化、最小化|復旧済み|ウィンドウを表示する状態を選択する|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="setwindowstatebase_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ウィンドウが見つかりません|指定したウィンドウが見つからなかったことを示します|
|ウィンドウの状態を設定できません|指定されたウィンドウのウィンドウ状態を設定しているときに問題が発生したことを示します|
|非インタラクティブ モードでウィンドウ関連のアクションを実行できません|非インタラクティブ モードでウィンドウに関連するアクションを実行しているときに問題が発生したことを示します|

### <a name="set-window-visibility"></a><a name="setwindowvisibilitybase"></a> ウィンドウの表示方法を設定する
非表示のウィンドウを表示するか、表示されているウィンドウを非表示にします

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ウィンドウの検索モード|N/A|ウィンドウの UI 要素ごと、ウィンドウ インスタンス/ハンドルごと、タイトル/クラスごと|ウィンドウの UI 要素ごと|ウィンドウの検索に UI 要素を使用するか、ウィンドウのタイトル/クラスの組み合わせを使用するかを指定する|
|ウィンドウ|無効|UIControl||ウィンドウ UI 要素|
|ウィンドウ タイトル|有効|テキスト値||ウィンドウ タイトル。 '?' や '*' のワイルドカードを使用できます。|
|ウィンドウ インスタンス|無効|数値||表示方法を設定するウィンドウのインスタンスまたはハンドル|
|ウィンドウ クラス|有効|テキスト値||同じタイトルのウィンドウが 2 つある場合、ウィンドウ クラスはそれらを区別するのに役立つかもしれません。 この場合、使用するウィンドウのクラスを入力します。|
|表示対象|N/A|表示、非表示|非表示|ウィンドウの表示方法を設定する状態を選択|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="setwindowvisibilitybase_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ウィンドウが見つかりません|指定したウィンドウが見つからなかったことを示します|
|ウィンドウの表示方法を設定できません|指定されたウィンドウの表示方法を設定しているときに問題が発生したことを示します|
|非インタラクティブ モードでウィンドウ関連のアクションを実行できません|非インタラクティブ モードでウィンドウに関連するアクションを実行しているときに問題が発生したことを示します|

### <a name="move-window"></a><a name="movewindowbase"></a> ウィンドウの移動
特定のウィンドウの位置を設定します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ウィンドウの検索モード|N/A|ウィンドウの UI 要素ごと、ウィンドウ インスタンス/ハンドルごと、タイトル/クラスごと|ウィンドウの UI 要素ごと|ウィンドウの検索に UI 要素を使用するか、ウィンドウのタイトル/クラスの組み合わせを使用するかを指定する|
|ウィンドウ|無効|UIControl||ウィンドウ UI 要素|
|ウィンドウ タイトル|有効|テキスト値||ウィンドウ タイトル。 '?' や '*' のワイルドカードを使用できます。|
|ウィンドウ インスタンス|無効|数値||移動するウィンドウのインスタンスまたはハンドルです。|
|ウィンドウ クラス|有効|テキスト値||同じタイトルを持つ 2 つのウィンドウがある場合はウィンドウ クラスによって区別できます。 この場合、使用するウィンドウのクラスを入力します。|
|位置 X|無効|数値||ウィンドウの X 位置|
|位置 Y|無効|数値||ウィンドウの Y 位置|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="movewindowbase_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ウィンドウが見つかりません|指定したウィンドウが見つからなかったことを示します|
|ウィンドウを移動できません|指定されたウィンドウを移動するときに問題が発生したことを示します|
|非インタラクティブ モードでウィンドウ関連のアクションを実行できません|非インタラクティブ モードでウィンドウに関連するアクションを実行しているときに問題が発生したことを示します|

### <a name="resize-window"></a><a name="resizewindowbase"></a> ウィンドウのサイズ変更
特定のウィンドウのサイズを設定します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ウィンドウの検索モード|N/A|ウィンドウの UI 要素ごと、ウィンドウ インスタンス/ハンドルごと、タイトル/クラスごと|ウィンドウの UI 要素ごと|ウィンドウの検索に UI 要素を使用するか、ウィンドウのタイトル/クラスの組み合わせを使用するかを指定する|
|ウィンドウ|無効|UIControl||ウィンドウ UI 要素|
|ウィンドウ タイトル|有効|テキスト値||ウィンドウ タイトル。 '?' や '*' のワイルドカードを使用できます。|
|ウィンドウ インスタンス|無効|数値||サイズ変更するウィンドウのインスタンスまたはハンドル|
|ウィンドウ クラス|有効|テキスト値||同じタイトルのウィンドウが 2 つある場合、ウィンドウ クラスはそれらを区別するのに役立つかもしれません。 この場合、使用するウィンドウのクラスを入力します|
|幅|無効|数値||新しい幅 (ピクセル単位)|
|高さ|無効|数値||新しい高さ (ピクセル単位)|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="resizewindowbase_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ウィンドウが見つかりません|指定したウィンドウが見つからなかったことを示します|
|ウィンドウをサイズ変更できません|指定されたウィンドウをサイズ変更するときに問題が発生したことを示します|
|非インタラクティブ モードでウィンドウ関連のアクションを実行できません|非インタラクティブ モードでウィンドウに関連するアクションを実行しているときに問題が発生したことを示します|

### <a name="close-window"></a><a name="closewindowbase"></a> ウィンドウを閉じる
特定のウィンドウを閉じます

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ウィンドウの検索モード|N/A|ウィンドウの UI 要素ごと、ウィンドウ インスタンス/ハンドルごと、タイトル/クラスごと|ウィンドウの UI 要素ごと|ウィンドウの検索に UI 要素を使用するか、ウィンドウのタイトル/クラスの組み合わせを使用するかを指定する|
|ウィンドウ|無効|UIControl||ウィンドウ UI 要素|
|ウィンドウ タイトル|有効|テキスト値||ウィンドウ タイトル。 '?' や '*' のワイルドカードを使用できます。|
|ウィンドウ インスタンス|無効|数値||閉じるウィンドウのインスタンスまたはハンドル|
|ウィンドウ クラス|有効|テキスト値||同じタイトルのウィンドウが 2 つある場合、ウィンドウ クラスはそれらを区別するのに役立つかもしれません。 この場合、使用するウィンドウのクラスを入力します。|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="closewindowbase_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ウィンドウが見つかりません|指定したウィンドウが見つからなかったことを示します|
|ウィンドウを閉じることができません|指定されたウィンドウを閉じるときに問題が発生したことを示します|
|非インタラクティブ モードでウィンドウ関連のアクションを実行できません|非インタラクティブ モードでウィンドウに関連するアクションを実行しているときに問題が発生したことを示します|

### <a name="use-desktop"></a><a name="usedesktop"></a> デスクトップを使用する
デスクトップとタスク バー関連の操作を実行します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|UI 要素|無効|UIControl||クリックする対象の UI 要素|
|クリックの種類|N/A|左クリック、右クリック、ダブル クリック|左クリック|実行するクリックの種類|
|タスク バーを左クリックしたら新しいアプリケーションを起動します|N/A|ブール値|有効|このパラメーターが 'True' に設定されている場合、'クイック起動' バー (Windows 7 ではタスク バー) のアイコンを左クリックすると、アプリケーションの新しいウィンドウが必ず作成されます。 このオプションのチェックを外すと、実行中のアプリケーションのインスタンスがフォアグラウンドになります。|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="usedesktop_onerror"></a> 例外
|例外|内容|
|-----|-----|
|タスク バー操作に失敗しました|タスク バーの操作に失敗したことを示します|

### <a name="select-tab-in-window"></a><a name="selecttab"></a> ウィンドウでタブを選択する
タブのグループからタブを選択します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|タブ​|無効|UIControl||選択するタブ|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="selecttab_onerror"></a> 例外
|例外|内容|
|-----|-----|
|タブの選択に失敗しました|指定されたタブの選択中に問題が発生したことを示します|

### <a name="click-ui-element-in-window"></a><a name="click"></a> ウィンドウの UI 要素をクリックする
ウィンドウの任意の UI 要素をクリックする

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|UI 要素|無効|UIControl||クリックする UI 要素|
|クリックの種類|N/A|左クリック、右クリック、ダブルクリック、左ボタン下、左ボタン上、右ボタン下、右ボタン上|左クリック|実行するクリックの種類|
|UI 要素に対するマウスの相対位置|N/A|左上隅、中央上部、右上隅、左中央、中央、右中央、左下隅、中央下、右下隅|中段中央|クリックする前にマウスの移動先の UI 要素のセクションを指定する|
|オフセット X|有効|数値|0|マウスの位置を右にオフセットするピクセル数|
|オフセット Y|有効|数値|0|マウスの位置を下にオフセットするピクセル数|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="click_onerror"></a> 例外
|例外|内容|
|-----|-----|
|クリックに失敗しました|クリックに失敗したことを示します|

### <a name="select-menu-option-in-window"></a><a name="selectmenuoption"></a> ウィンドウ内のメニュー オプションを選択する
ウィンドウのメニューのオプションを選択します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|UI 要素|無効|UIControl||選択するメニュー オプション|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="selectmenuoption_onerror"></a> 例外
|例外|内容|
|-----|-----|
|オプションを選択できませんでした|指定されたメニュー オプションの選択中に問題が発生したことを示します|

### <a name="drag-and-drop-ui-element-in-window"></a><a name="draganddropelement"></a> UI 要素をウィンドウ内にドラッグ アンド ドロップする
ウィンドウの UI 要素をドラッグ アンド ドロップする

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ドラッグする UI 要素|無効|UIControl||ドラッグする UI 要素|
|ドロップ先の UI 要素|無効|UIControl||ドロップ先の UI 要素|
|クリックの種類|N/A|左クリック、右クリック|左クリック|UI 要素を目的の場所までドラックする際に、クリックして押したままにするマウス ボタンを指定する|
|マウス ダウン オフセット X|有効|数値|0|ドラッグする UI 要素の指定に使用するマウス ダウン クリックを、このピクセル数右にオフセットする|
|マウス ダウン オフセット Y|有効|数値|0|ドラッグする UI 要素の指定に使用するマウス ダウン クリックを、このピクセル数下にオフセットする|
|ドラッグする UI 要素に対するマウス ダウンの相対位置|N/A|左上隅、中央上部、右上隅、左中央、中央、右中央、左下隅、中央下、右下隅|中段中央|クリックする前にマウスの移動先のドロップ ターゲット UI 要素のセクションを指定する|
|マウス アップ オフセット X|有効|数値|0|ドラッグする UI 要素の指定に使用するマウス アップ クリックを、このピクセル数右にオフセットする|
|マウス アップ オフセット Y|有効|数値|0|ドラッグする UI 要素の指定に使用するマウス アップ クリックを、このピクセル数下にオフセットする|
|ドラッグする UI 要素に対するマウス アップの相対位置|N/A|左上隅、中央上部、右上隅、左中央、中央、右中央、左下隅、中央下、右下隅|中段中央|クリックした後にマウスの移動先のドロップ ターゲット UI 要素のセクションを指定する|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="draganddropelement_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ドラッグする UI 要素が見つかりません|ドラッグする UI 要素が見つからなかったことを示します|
|ドロップ ターゲット UI 要素が見つかりません|ドロップ ターゲット UI 要素が見つからなかったことを示します|
|ドラッグ アンド ドロップに失敗しました|指定した UI 要素のドラッグ アンド ドロップ中に発生した問題を示します|

### <a name="expandcollapse-tree-node-in-window"></a><a name="expandcollapsetreenode"></a> ウィンドウ内のツリー ノードを展開/折りたたむ
ウィンドウ内にあるツリー ビューのノードを展開するか折りたたみます

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|UI 要素|無効|UIControl||展開/折りたたむツリー ノード|
|フォルダー パス|有効|テキスト値||展開するか折りたたむツリー ノードに導く、フォルダー名で構成されるスラッシュ区切りのパス|
|正規表現を使用する|N/A|ブール値|無効|パス内の各フォルダー名を正規表現として解釈するかどうかを指定する|
|操作|N/A|展開/折りたたむ|展開する|ツリー ノードを展開するか折りたたむかを指定します|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="expandcollapsetreenode_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ツリー ノードを指定された状態に設定できません|ツリー ノードを指定された状態に設定しているときに問題が発生したことを示します|

