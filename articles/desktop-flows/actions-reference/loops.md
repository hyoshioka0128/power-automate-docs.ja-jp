---
title: ループ | Microsoft Docs
description: ループのアクションについての参考情報
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
ms.openlocfilehash: 4ce19d6e166afea5323d6adb4490c9a2484fa8c9
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711621"
---
# <a name="loops"></a>ループ



ループを終了し、次のアクションやループ後のステートメントでフローを再開します

ループ アクションの使用方法の詳細については、[こちら](../use-loops.md)を参照してください
|<!-- --> |
|-----|
|[ループを抜ける](#break)|
|[For each](#foreach)|
|[Loop](#loop)|
|[ループ条件](#while)|
|[次のループ](#continue)|

### <a name="exit-loop"></a><a name="break"></a> ループを抜ける
ループを終了し、次のアクションやループ後のステートメントでフローを再開します

##### <a name="input-parameters"></a>入力パラメーター
- このアクションには入力は必要ありません

##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="break_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="for-each"></a><a name="foreach"></a> それぞれに対して
リスト、データ テーブル、またはデータ行にあるアイテムを反復処理して、アクションのブロックを繰り返して実行します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|反復処理を行う値|無効|*||反復処理するリスト、データ行、またはデータ テーブルの値を入力します。|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
||*|各イテレーションで現在のアイテム値を保存する値の名前。|


##### <a name="exceptions"></a><a name="foreach_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="loop"></a><a name="loop"></a> ループ
指定された数のアクションのブロックを反復処理します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|開始値|無効|数値||ループ カウンターの開始点を設定します。|
|増分|無効|数値||ループ カウンター変数の増分を設定します。|
|終了|無効|数値||ループ カウンターの終了点を設定します。|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
||*|値から始まる現在のインデックスを格納する値の名前です。 この値は、反復するたびに増分が加算されます。|


##### <a name="exceptions"></a><a name="loop_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="loop-condition"></a><a name="while"></a> ループ条件
指定された条件が真である限り、アクションのブロックを反復処理します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|オペレーター|N/A|次と等しい (=)、次と等しくない (<>)、次よりも大きい (>)、 次より大きいか又は等しい (>=)、次よりも小さい (<)、次より小さいか又は等しい (<=)|と等しい (=)|2 番目のオペランドに対する最初のオペランドの関係を選択します。|
|最初のオペランド|無効|*||2 番目のオペランドと比較する、前のアクションで定義された値の名前、テキスト、数値、または式を入力します。|
|2 番目のオペランド|無効|*||最初のオペランドと比較する、前のアクションで作成された値の名前、テキスト、数値、または式を入力します。|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="while_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="next-loop"></a><a name="continue"></a> 次のループ
ブロックの次のイテレーションを強制的に実行し、間にあるすべてのアクションをスキップします

##### <a name="input-parameters"></a>入力パラメーター
- このアクションには入力は必要ありません

##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="continue_onerror"></a> 例外
- このアクションには例外は含まれません

