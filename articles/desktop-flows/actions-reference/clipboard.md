---
title: クリップボード | Microsoft Docs
description: クリップボード アクションについての参考情報
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
ms.openlocfilehash: 4624cd6516571cc3b0529c30d37bb1544e5fa46b
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711633"
---
# <a name="clipboard"></a>クリップボード



クリップボードのデータを設定または取得

|<!-- --> |
|-----|
|[クリップボード テキストを取得](#gettext)|
|[クリップボード テキストを設定](#settext)|
|[クリップボードの内容をクリア](#clear)|

### <a name="get-clipboard-text"></a><a name="gettext"></a> クリップボード テキストの取得
クリップボード テキストを取得します

##### <a name="input-parameters"></a>入力パラメーター
- このアクションには入力は必要ありません

##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|ClipboardText|テキスト値|クリップボードに保存されているテキスト|


##### <a name="exceptions"></a><a name="gettext_onerror"></a> 例外
|例外|内容|
|-----|-----|
|クリップボードの内容を取得できません|クリップボードの内容の取得中に問題が発生したことを示します|

### <a name="set-clipboard-text"></a><a name="settext"></a> クリップボード テキストの設定
クリップボード テキストを設定します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|クリップボード テキスト|無効|テキスト値||クリップボードに設定するテキスト|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="settext_onerror"></a> 例外
|例外|内容|
|-----|-----|
|クリップボードの内容を設定できません|クリップボードの内容の設定中に問題が発生したことを示します|

### <a name="clear-clipboard-contents"></a><a name="clear"></a> クリップボードの内容をクリアする
クリップボードの内容をクリアします

##### <a name="input-parameters"></a>入力パラメーター
- このアクションには入力は必要ありません

##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="clear_onerror"></a> 例外
- このアクションには例外は含まれません

