---
title: システム | Microsoft Docs
description: システムのアクションに関する参考情報
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
ms.openlocfilehash: 65dfcda646179fb94eb727a6230e593b28e75415
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711616"
---
# <a name="system"></a>System



Windows 環境でさまざまなタスクを実行し、システムから情報を取得します

|<!-- --> |
|-----|
|[アプリケーションの実行](#runapplicationbase)|
|[DOS コマンドの実行](#rundoscommand)|
|[VBScript の実行](#runvbscript)|
|[プロセスを終了する](#terminateprocess)|
|[ドキュメントの印刷](#printdocument)|
|[既定のプリンターを取得](#getdefaultprinter)|
|[既定のプリンターを設定](#setdefaultprinter)|
|[ユーザーをログオフ](#logoffuser)|
|[コンピューターのシャットダウン](#shutdowncomputer)|
|[デスクトップを表示](#showdesktop)|
|[ワークステーションをロック](#lockworkstation)|
|[サウンドの再生](#playsoundbase)|
|[ごみ箱を空にする](#emptyrecyclebin)|
|[スクリーンショットを取得](#takescreenshotbase)|
|[スクリーンセーバーの制御](#controlscreensaver)|
|[Ping](#ping)|
|[環境変数を設定](#setenvironmentvariable)|
|[環境変数を取得](#getenvironmentvariable)|
|[環境変数を削除](#deleteenvironmentvariable)|
|[JavaScript の実行](#runjavascript)|
|[PowerShell スクリプトの実行](#runpowershellscript)|
|[画面の解像度を取得](#getscreenresolution)|
|[画面の解像度を設定](#setscreenresolution)|
|[Python スクリプトの実行](#runpythonscript)|

### <a name="run-application"></a><a name="runapplicationbase"></a> アプリケーションの実行
関連付けられたアプリケーションを実行して、アプリケーションを実行するか、ドキュメントを開きます

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|アプリケーション パス|無効|ファイル||実行可能ファイルの完全なファイル パス|
|コマンド ライン引数|有効|テキスト値||実行可能ファイル名の後に続く引数を追加します。 たとえば、アプリケーションパスに 「notepad.exe」 と入力し、コマンドライン引数に特定のテキスト ファイルを入力します|
|作業フォルダー|有効|フォルダー||作業するフォルダーの完全なパス (該当する場合)。|
|ウィンドウ スタイル|N/A|通常、非表示、最小化、最大化|普通|アプリケーション ウィンドウを開くときの外観とサイズを選択|
|アプリケーション起動後|N/A|ただちに続行する、アプリケーションの読み込みを待機する、アプリケーションの完了を待機する|すぐに続行|次のアクションがすぐに実行されるか、プログラムが読み込みまたは完了するまで待機するか|
|タイムアウト|有効|数値|0|続行を強制するまでの最大待機時間|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|AppProcessId|数値|プロセス ID 出力|
|AppExitCode|数値|アプリケーション終了コード|
|WindowHandle|数値|ウィンドウ ハンドルです。 新しいウィンドウを開くと、ウィンドウ ハンドルの値をキャッチし、この変数に格納します。 ウィンドウ ハンドルは、後のアクションでウィンドウを特定する際に役立ちます|


##### <a name="exceptions"></a><a name="runapplicationbase_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ファイルまたはアプリケーションが見つかりません|指定されたファイルまたはアプリケーションが見つからなかったことを示します|
|アプリケーションまたはファイルへのアクセスが拒否されました|指定されたアプリケーションまたはファイルに対するアクセスが拒否されたことを示します|
|アプリケーションのメイン ウィンドウ ハンドルを取得できません|アプリケーションのメイン ウィンドウ ハンドルの取得中に問題が発生したことを示します|
|アプリケーションを実行できないか、ファイルを開けません|指定されたアプリケーションを実行するか、指定されたファイルを開くときに問題が発生したことを示します|

### <a name="run-dos-command"></a><a name="rundoscommand"></a>DOS コマンドの実行
DOS コマンドまたはコンソール アプリケーションを非表示モードで実行し、完了時にその出力を取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|DOS コマンドまたはアプリケーション|無効|ファイル||DOS コマンドまたはコンソール アプリケーションの名前 (該当する場合は引数あり)|
|作業フォルダー|有効|フォルダー||作業するフォルダーの完全なパス (該当する場合)|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|CommandOutput|テキスト値|DOS コマンドまたはアプリケーションからのテキスト出力|
|CommandErrorOutput|テキスト値|DOS コマンドまたはアプリケーションの実行中に発生したエラー (ある場合) を表すテキスト|
|CommandExitCode|数値|コマンド、またはアプリケーションの終了コードです。 この値は数値です|


##### <a name="exceptions"></a><a name="rundoscommand_onerror"></a> 例外
|例外|内容|
|-----|-----|
|コマンドまたはコンソール アプリケーションを実行できません|指定されたコマンドまたはコンソール アプリケーションの実行中に問題が発生したことを示します|

### <a name="run-vbscript"></a><a name="runvbscript"></a> VBScript の実行
いくつかのカスタム VBScript コードを実行し、その出力を変数に取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|実行する VBScript|有効|テキスト値||実行する VBScript スクリプト コードです。 VBScript の実行前に評価されるため、スクリプト内に変数を含めることができます|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|VBScriptOutput|テキスト値|スクリプトの出力|
|ScriptError|テキスト値|VBScript コードの実行中に発生する可能性のあるエラー|


##### <a name="exceptions"></a><a name="runvbscript_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="terminate-process"></a><a name="terminateprocess"></a> プロセスの終了
実行中のプロセスをすぐに停止します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|プロセスの指定方法|N/A|プロセス ID、プロセス名|プロセス名|終了するプロセスを名前または ID のどちらで指定するかを指定|
|プロセス ID|無効|数値||終了するプロセスの ID|
|プロセス名|無効|テキスト値||終了するプロセスの 名称です。 同じ名前を持つプロセスが複数実行されている場合、すべてのプロセスが終了します|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="terminateprocess_onerror"></a> 例外
|例外|内容|
|-----|-----|
|指定された ID のプロセスが実行されていません|指定された ID のプロセスが実行中でないことを示します|
|プロセスを終了できませんでした。|プロセスの終了時に問題が発生したことを示します|

### <a name="print-document"></a><a name="printdocument"></a> ドキュメントの印刷
既定のプリンターでドキュメントを印刷します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|印刷するドキュメント|無効|ファイル||印刷するドキュメントのパス|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="printdocument_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ドキュメントが見つかりません|指定されたドキュメントが見つからなかったことを示します|
|ドキュメントへのアクセスが拒否されました|指定されたドキュメントへのアクセスが拒否されたことを示します|
|ドキュメントを印刷できません|指定されたドキュメントを印刷するときに問題が発生したことを示します|

### <a name="get-default-printer"></a><a name="getdefaultprinter"></a> 既定のプリンターを取得する
既定のプリンターの名前を取得します

##### <a name="input-parameters"></a>入力パラメーター
- このアクションには入力は必要ありません

##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|PrinterName|テキスト値|既定のプリンターの名前|


##### <a name="exceptions"></a><a name="getdefaultprinter_onerror"></a> 例外
|例外|内容|
|-----|-----|
|既定のプリンターを取得できません|既定のプリンターを取得するときに問題が発生したことを示します|

### <a name="set-default-printer"></a><a name="setdefaultprinter"></a> 既定のプリンターを設定する
プリンターを既定のプリンターとして設定します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|プリンター名|無効|テキスト値||既定値として設定するプリンターの名前|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="setdefaultprinter_onerror"></a> 例外
|例外|内容|
|-----|-----|
|既定のプリンターを設定できません|既定のプリンターを設定するときに問題が発生したことを示します|

### <a name="log-off-user"></a><a name="logoffuser"></a> ユーザーをログオフする
現在のユーザーをログオフします

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ログオフを強制|N/A|ブール値|無効|保存されていないファイルがあるかどうかやプログラムが閉じるかどうかに関係なく、ユーザー アカウントのログオフを強制するかどうかを指定します|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="logoffuser_onerror"></a> 例外
|例外|内容|
|-----|-----|
|非インタラクティブ モードでユーザーをログオフできません|非インタラクティブ モードでのユーザーのログオフ中に問題が発生したことを示します|
|現在のユーザーをログオフできません|現在のユーザーのログオフ時に問題が発生したことを示します|

### <a name="shutdown-computer"></a><a name="shutdowncomputer"></a> コンピューターのシャットダウン
コンピューターをシャットダウンします

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|実行するアクション|N/A|シャットダウン、再起動、一時停止、休止状態|シャットダウン|コンピューターが実行するシャットダウン オプションを指定します|
|強制|N/A|ブール値|無効|保存されていないファイルがあるかどうかやプログラムが閉じるかどうかに関係なく、コンピューターのシャットダウンを強制するかどうかを指定します|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="shutdowncomputer_onerror"></a> 例外
|例外|内容|
|-----|-----|
|コンピューターをシャットダウンできません|コンピューターのシャットダウン時に問題が発生したことを示します|

### <a name="show-desktop"></a><a name="showdesktop"></a> デスクトップを表示する
デスクトップを表示します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|操作|N/A|すべてのウィンドウを最小化 (デスクトップを表示)、すべてのウィンドウを復元 (デスクトップの表示解除)|すべてのウィンドウを最小化 (デスクトップを表示)|すべてのウィンドウを最小化してデスクトップを表示するか、すべてのウィンドウを復元して元の状態に戻すかを指定|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="showdesktop_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="lock-workstation"></a><a name="lockworkstation"></a> ワークステーションをロックする
ワークステーションの表示をロックして、無断使用から保護します

##### <a name="input-parameters"></a>入力パラメーター
- このアクションには入力は必要ありません

##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="lockworkstation_onerror"></a> 例外
|例外|内容|
|-----|-----|
|コンピューターを非インタラクティブ モードでロックできません|非インタラクティブ モードでのコンピューターのロック中に問題が発生したことを示します|
|コンピューターをロックできません|非インタラクティブ モードでのコンピューターのロック中に問題が発生したことを示します|

### <a name="play-sound"></a><a name="playsoundbase"></a> サウンドの再生
システム サウンドまたは wav ファイルを再生します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|サウンドの再生元|N/A|システム、WAV ファイル|System|再生するサウンドの種類|
|再生するサウンド|N/A|アスタリスク、ビープ音、感嘆符、ハンド、質問|アスタリスク|再生する特定のサウンド|
|再生するファイル|無効|ファイル||再生する特定の WAV ファイルの完全なパス|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="playsoundbase_onerror"></a> 例外
|例外|内容|
|-----|-----|
|サウンド ファイルが見つかりません|サウンド ファイルが見つからなかったことを示します|
|サウンド ファイルが無効です|無効なサウンド ファイルを示します|

### <a name="empty-recycle-bin"></a><a name="emptyrecyclebin"></a> ごみ箱を空にする
Windows のごみ箱からすべてのファイルを削除します

##### <a name="input-parameters"></a>入力パラメーター
- このアクションには入力は必要ありません

##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="emptyrecyclebin_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="take-screenshot"></a><a name="takescreenshotbase"></a> スクリーンショットを取得する
フォアグラウンド ウィンドウまたは指定された画面のスクリーンショットを取得して、画像をファイルまたはクリップボードに保存します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|キャプチャ|N/A|すべての画面、プライマリ画面、選択画面、フォアグラウンド ウィンドウ|すべての画面|キャプチャする領域|
|キャプチャする画面|無効|数値||キャプチャする画面を指定|
|スクリーンショットの保存先|N/A|クリップボード、ファイル|クリップボード|スクリーンショットの保存先の場所|
|画像ファイル|無効|ファイル||キャプチャした画像を保存するファイル名の完全なパス|
|画像の形式|N/A|BMP、EMF、EXIF、GIF、JPG、PNG、TIFF、WMF|BMP|保存する画像ファイルの形式|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="takescreenshotbase_onerror"></a> 例外
|例外|内容|
|-----|-----|
|スクリーンショットを取得できませんでした。|スクリーンショットの取得で問題が発生したことを示します|
|スクリーンショットをファイルに保存できませんでした|スクリーンショットをファイルに保存するときに問題が発生したことを示します|
|スクリーンショットをクリップボードに設定できませんでした|スクリーンショットをクリップボードに設定するときに問題が発生したことを示します|
|指定された画面を取得できませんでした|指定された画面の取得時に問題が発生したことを示します|

### <a name="control-screen-saver"></a><a name="controlscreensaver"></a> スクリーンセーバーの制御
スクリーンセーバーを有効化、無効化、開始、または停止します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|スクリーンセーバーの操作|N/A|有効化、無効化、開始、停止|有効にする​​|スクリーンセーバーの機能|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="controlscreensaver_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="ping"></a><a name="ping"></a> Ping
リモート コンピューターにネットワーク経由でアクセスできるかどうかを判断するメッセージを送信します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ホスト名|無効|テキスト値||リモート コンピューターの名前または IP アドレス|
|タイムアウト|有効|数値|5000|ping 応答メッセージを待機する最大時間 (ミリ秒)|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|PingResult|テキスト値|ping メッセージの状態 (成功または失敗)|
|RoundTripTime|数値|ping の完了にかかった時間 (ミリ秒)|


##### <a name="exceptions"></a><a name="ping_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ping アクションを完了できません|ping アクションの実行中に問題が発生したことを示します|

### <a name="set-environment-variable"></a><a name="setenvironmentvariable"></a> 環境変数を設定する
環境変数を特定の値に設定します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|環境変数名|無効|テキスト値||環境変数の名前|
|新しい環境変数の値|無効|テキスト値||環境変数に設定する値|
|型|N/A|ユーザー、システム|ユーザー |環境変数の種類|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="setenvironmentvariable_onerror"></a> 例外
|例外|内容|
|-----|-----|
|環境変数の値の設定中に問題が発生したことを示します|環境変数の値の設定中に問題が発生したことを示します|
|アクセス許可が不十分です|ユーザーにこのアクションを実行するための十分なアクセス許可がないことを示します|

### <a name="get-environment-variable"></a><a name="getenvironmentvariable"></a> 環境変数を取得する
環境変数の値を取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|環境変数名|無効|テキスト値||値を取得する環境変数の名前|
|スコープ内でのみ変数を検索|N/A|ブール値|無効|特定のスコープでのみ変数を検索するかどうかを指定|
|範囲|N/A|ユーザー、システム|ユーザー |環境変数の取得元のスコープ|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|EnvironmentVariableValue|テキスト値|環境変数の値|


##### <a name="exceptions"></a><a name="getenvironmentvariable_onerror"></a> 例外
|例外|内容|
|-----|-----|
|環境変数が存在しません|指定された環境変数が存在しないことを示します|
|アクセス許可が不十分です|ユーザーにこのアクションを実行するための十分なアクセス許可がないことを示します|

### <a name="delete-environment-variable"></a><a name="deleteenvironmentvariable"></a> 環境変数を削除する
指定したスコープから環境変数を削除します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|環境変数名|無効|テキスト値||削除する環境変数の名前|
|型|N/A|ユーザー、システム|ユーザー |削除する環境変数の種類|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="deleteenvironmentvariable_onerror"></a> 例外
|例外|内容|
|-----|-----|
|環境変数を削除できませんでした|環境変数の削除中に問題が発生したことを示します|
|アクセス許可が不十分です|ユーザーにこのアクションを実行するための十分なアクセス許可がないことを示します|

### <a name="run-javascript"></a><a name="runjavascript"></a> JavaScript の実行
いくつかのカスタム JavaScript コードを実行し、その出力を変数に取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|実行する JavaScript|有効|テキスト値||実行する JavaScript スクリプトのコードです。 JavaScript の実行前に評価されるため、スクリプト内に変数を含めることができます|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|JavascriptOutput|テキスト値|スクリプトの出力|
|ScriptError|テキスト値|JavaScript コードの実行中に発生する可能性のあるエラー|


##### <a name="exceptions"></a><a name="runjavascript_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="run-powershell-script"></a><a name="runpowershellscript"></a> PowerShell スクリプトの実行
いくつかのカスタム PowerShell スクリプトを実行し、その出力を変数に取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|実行する PowerShell コード|有効|テキスト値||実行する PowerShell スクリプトのコードです。 PowerShell コードの実行前に評価されるため、スクリプト内に変数を含めることができます|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|PowershellOutput|テキスト値|スクリプトの出力|
|ScriptError|テキスト値|PowerShell コードの実行中に発生する可能性のあるエラー|


##### <a name="exceptions"></a><a name="runpowershellscript_onerror"></a> 例外
|例外|内容|
|-----|-----|
|PowerShell スクリプトを実行できませんでした|指定された PowerShell スクリプトの実行中に問題が発生したことを示します|

### <a name="get-screen-resolution"></a><a name="getscreenresolution"></a> 画面の解像度を取得する
選択したモニターの幅、高さ、ビット数、周波数を取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|モニター番号|無効|数値||解像度を取得するモニターの番号|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|MonitorWidth|数値|モニターの幅|
|MonitorHeight|数値|モニターの高さ|
|MonitorBitCount|数値|モニターのビット数|
|MonitorFrequency|数値|モニターの周波数|


##### <a name="exceptions"></a><a name="getscreenresolution_onerror"></a> 例外
|例外|内容|
|-----|-----|
|画面の解像度を取得できませんでした|画面の解像度の取得時に問題が発生したことを示します|

### <a name="set-screen-resolution"></a><a name="setscreenresolution"></a> 画面の解像度を設定する
選択したモニターの幅、高さ、ビット数、周波数を設定します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|モニター番号|無効|数値||解像度を設定するモニターの番号|
|モニターの幅|無効|数値||モニターの幅を設定する値|
|モニターの高さ|無効|数値||モニターの高さを設定する値|
|モニターのビット数|無効|数値||モニターのビット数を設定する値|
|モニターの周波数|無効|数値||モニターの周波数を設定する値|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="setscreenresolution_onerror"></a> 例外
|例外|内容|
|-----|-----|
|画面の解像度を設定できませんでした|画面の解像度の設定時に問題が発生したことを示します|

### <a name="run-python-script"></a><a name="runpythonscript"></a> Python スクリプトの実行
Python 2 スクリプト コードを実行し、出力を取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|実行する Python スクリプト|無効|テキスト値||実行する Python スクリプト コード|
|モジュール フォルダー パス|有効|フォルダーの一覧||外部 Python モジュールが存在するフォルダーのパス|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|PythonScriptOutput|テキスト値|スクリプトの出力|
|ScriptError|テキスト値|Python スクリプト コードの実行中に発生する可能性のあるエラー|


##### <a name="exceptions"></a><a name="runpythonscript_onerror"></a> 例外
|例外|内容|
|-----|-----|
|Python スクリプトを実行できませんでした|指定された Python スクリプトの実行中に問題が発生したことを示します|
|ディレクトリが見つかりません|ディレクトリが見つからなかったことを示します|


