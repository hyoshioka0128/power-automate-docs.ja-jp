---
title: フロー コントロール | Microsoft Docs
description: フロー コントロールを使用したアクションについての参考情報
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
ms.openlocfilehash: 9bf975aef3facff05ab9726c555cc7e565e74e64
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711625"
---
# <a name="flow-control"></a>フロー コントロール



アクションのエラーを処理するブロックの先頭をマークする

|<!-- --> |
|-----|
|[コメント](#comment)|
|[[終了]](#end)|
|[サブフローの終了](#exitfunction)|
|[移動先](#goto)|
|[ラベル](#label)|
|[ブロック エラー発生時](#block)|
|[サブフローの実行](#callfunction)|
|[フローを停止する](#exit)|

### <a name="comment"></a><a name="comment"></a> コメント
ユーザー コメント

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|コメント|有効|テキスト値||ユーザー コメント|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="comment_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="end"></a><a name="end"></a> 終了


##### <a name="input-parameters"></a>入力パラメーター
- このアクションには入力は必要ありません

##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="end_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="exit-subflow"></a><a name="exitfunction"></a> サブフローの終了
現在のサブフローを終了し、呼び出された位置に戻ります

##### <a name="input-parameters"></a>入力パラメーター
- このアクションには入力は必要ありません

##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="exitfunction_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="go-to"></a><a name="goto"></a> 次ににアクセスする
実行フローをラベルで示される別のポイントに転送します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ラベルに移動|無効|テキスト値||フロー内のラベル|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="goto_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="label"></a><a name="label"></a> ラベル
go to ステートメントの移動先として動作します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ラベル名|無効|テキスト値||プログラムのラベル|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="label_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="on-block-error"></a><a name="block"></a> ブロック エラー発生時
アクションのエラーを処理するブロックの先頭をマークする

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|件名|無効|テキスト値||視覚化のためにのみ使用する例外ブロックの名前。|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="block_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="run-subflow"></a><a name="callfunction"></a> サブフローの実行
必要な引数を指定してサブフローを実行する

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|サブフロー名|無効|サブフロー||呼び出すサブフローの名前|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="callfunction_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="stop-flow"></a><a name="exit"></a> フローの停止
フローを終了する

##### <a name="input-parameters"></a>入力パラメーター
- このアクションには入力は必要ありません

##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="exit_onerror"></a> 例外
- このアクションには例外は含まれません

