---
title: Datetime | Microsoft Docs
description: Datetime のアクションに関する参考情報
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
ms.openlocfilehash: 40f210bf2d539603a5f04d8da8944a93f35aa29a
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711602"
---
# <a name="datetime"></a>Datetime



日時を取得し、時間関連の関数を実行します

|<!-- --> |
|-----|
|[加算する日時](#add)|
|[日付の減算](#subtract)|
|[現在の日時を取得します](#getcurrentdatetime)|

### <a name="add-to-datetime"></a><a name="add"></a> datetime に追加する
日時の値に、指定した秒、分、時間、または日数を加算 (または減算) します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|Datetime|無効|Datetime||変更する日時の値|
|加算|無効|数値||追加する数値です。 時間を引くには、この値はマイナスになります。 例えば、ここに -7 日を追加すると、1 週間前に戻ります|
|時間単位|N/A|秒、分、時間、日、月、年|秒|加算する時間の単位|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|ResultedDate|Datetime|新しい、変更された日時の値|


##### <a name="exceptions"></a><a name="add_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="subtract-dates"></a><a name="subtract"></a> 日付の減算
指定された 2 つの日時の時間差を、日、時間、分、秒で求めます

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|元となる日付|無効|Datetime||最初の datetime を減算する datetime です。 これは基準となる日付の時刻となるため、一般的にはこの属性に後の日付/時刻を入れます|
|日付の減算|無効|Datetime||減算する日時|
|差異を次の単位で取得|N/A|秒、分、時間、日|日間|差異を表す時間の単位|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|TimeDifference|数値|時間の差異 (数値)|


##### <a name="exceptions"></a><a name="subtract_onerror"></a> 例外
- このアクションには例外は含まれません
### <a name="get-current-date-and-time"></a><a name="getcurrentdatetime"></a> 現在の日時を取得する
現在の日付または現在の日時を取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|取得|N/A|現在の日付と時間、現在の日付のみ|現在の日時|日時を取得するか、日付だけを取得するかを指定します。 後者を選択した場合、時間値は深夜 (0:00:00) として保存されます|
|タイム ゾーン|N/A|システム タイムゾーン、特定のタイム ゾーン|システム タイム ゾーン|システムのタイム ゾーンを使用するか、またはカスタムのタイム ゾーンを使用するかを指定します|
|国/地域|有効|テキスト値|ヨーロッパ/ブカレスト|UTC タイム ゾーンの国/地域。時間を取得したり、時間の数値を加算したりするために使用します|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|CurrentDateTime|Datetime|現在の日時の値|


##### <a name="exceptions"></a><a name="getcurrentdatetime_onerror"></a> 例外
|例外|内容|
|-----|-----|
|現在の日時を取得できませんでした|現在の日時の取得で問題が発生したことを示します|
|指定された国/地域が見つかりません|指定した国または地域が見つからなかったことを示します|


