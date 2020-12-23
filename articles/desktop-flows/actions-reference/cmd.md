---
title: CMD セッション | Microsoft Docs
description: CMD セッションについての参考情報
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
ms.openlocfilehash: 7432ab644c34cb9ae77bde7f6b462b10a4803d40
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711634"
---
# <a name="cmd-session"></a>CMD セッション



CMD セッションを自動化

|<!-- --> |
|-----|
|[CMD セッションを開く](#open)|
|[CMD セッションから読み取る](#readfromcmdsession)|
|[CMD セッションに書き込む](#write)|
|[CMD セッションでテキストを待機します](#waitfortext)|
|[CMD セッションの終了](#close)|

### <a name="open-cmd-session"></a><a name="open"></a>CMD セッションを開く
新しい CMD セッションを開く

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|作業フォルダー|有効|フォルダー||CMD セッションを開始するフォルダーの完全なパス (該当する場合)|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|CmdSession|CMD セッション|後の CMD アクションで使う CMD セッション|


##### <a name="exceptions"></a><a name="open_onerror"></a> 例外
|例外|内容|
|-----|-----|
|コマンド セッションを開始できません|CMD セッションの開始で問題が発生したことを示します|
|作業ディレクトリが存在しません|作業ディレクトリを特定しようとしたときにエラーが発生したことを示します|

### <a name="read-from-cmd-session"></a><a name="readfromcmdsession"></a>CMD セッションから読み取る
CMD セッションの出力を読み取ります

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|CMD セッション|無効|CMD セッション||既に開いている CMD セッション|
|出力とエラーを分ける|N/A|ブール値|無効|標準出力と標準エラーを別々の変数に格納するか、または結合して 1 つにするかを指定します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|CmdOutput|テキスト値|CMD セッションの標準出力|
|CmdError|テキスト値|CMD セッションの標準エラー|


##### <a name="exceptions"></a><a name="readfromcmdsession_onerror"></a> 例外
|例外|内容|
|-----|-----|
|CMD セッションが閉じています|指定された CMD セッションが閉じていることを示します|

### <a name="write-to-cmd-session"></a><a name="write"></a>CMD セッションに書き込む
開いている CMD セッションでコマンドを実行します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|CMD セッション|無効|CMD セッション||既に開いている CMD セッション変数|
|command|無効|テキスト値||実行するコマンドの名前|
|コマンド後に <Enter> を送信|N/A|ブール値|有効|コマンド後に <Enter> を送信するかどうかを指定します|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="write_onerror"></a> 例外
|例外|内容|
|-----|-----|
|CMD セッションに書き込めません|CMD セッションへの書き込みエラーを示します|
|CMD セッションが閉じています|指定された CMD セッションが閉じていることを示します|

### <a name="wait-for-text-on-cmd-session"></a><a name="waitfortext"></a>CMD セッションでテキストを待機します
既に開いている CMD セッションで特定のテキストを待機します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|CMD セッション|無効|CMD セッション||開いている CMD セッション変数|
|待機するテキスト|無効|テキスト値||標準出力または標準エラーに表示されるのを待機するテキストまたは正規表現|
|正規表現|N/A|ブール値|無効|通常のテキストではなく正規表現を待機するかどうかを指定します|
|大文字小文字を区別しない|N/A|ブール値|有効|テキストの大文字と小文字を区別せずに、待機するテキストを標準出力または標準エラーと一致させるかどうかを指定します|
|タイムアウト|有効|数値|0|テキストが表示されるまで無期限に待機するか、設定した時間内にテキストが表示されない場合は失敗するかを指定します|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="waitfortext_onerror"></a> 例外
|例外|内容|
|-----|-----|
|CMD セッションが閉じています|指定された CMD セッションが閉じていることを示します|
|テキストの待機中にタイムアウトが発生しました|テキストがコマンド セッションに表示される前に指定されたタイムアウト期間が経過したことを示します|

### <a name="close-cmd-session"></a><a name="close"></a>CMD セッションの終了
既に開いている CMD セッションを閉じる

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|CMD セッション|無効|CMD セッション||CMD セッションを閉じます。 オープンな CMD セッション アクションでこの変数を指定します|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="close_onerror"></a> 例外
- このアクションには例外は含まれません

