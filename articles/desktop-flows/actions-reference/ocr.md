---
title: OCR | Microsoft Docs
description: OCR を使用したアクションについての参考情報
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
ms.openlocfilehash: 42508dbcc1de5aca0388c25fc5eca8f0552a1376
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711620"
---
# <a name="ocr"></a>OCR



OCR 関連の活動を実行するために OCR エンジンを開始

|<!-- --> |
|-----|
|[Tesseract OCR エンジンを作成](#createtesseractocrenginebase)|
|[MODI OCR エンジンを作成](#createmodiengine)|
|[OCR を使ってテキストを抽出](#extracttextwithocr)|

### <a name="create-tesseract-ocr-engine"></a><a name="createtesseractocrenginebase"></a>Tesseract OCR エンジンを作成
Tesseract OCR エンジンを作成

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|他の言語を使う|N/A|ブール値|無効|選択肢で指定されていない言語を使うかどうかを指定します|
|Tesseract 言語|N/A|英語、ドイツ語、スペイン語、フランス語、イタリア語|English|Tesseract エンジンにより検出される画像のテキストの言語|
|言語の省略形|無効|テキスト値||使用する言語の Tesseract 言語コードです。 たとえば、データが 「eng.traineddata」 の場合、フィールドに 「eng」 と入力します|
|言語データ パス: |無効|フォルダー||指定された言語の Tesseract のデータを含むフォルダーのパス|
|画像の幅の乗数|有効|数値|1|画像の幅の乗数|
|画像の高さの乗数|有効|数値|1|画像の高さの乗数|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|OCREngine|OCREngineObject|後の OCR アクションで使う OCR エンジン|


##### <a name="exceptions"></a><a name="createtesseractocrenginebase_onerror"></a> 例外
|例外|内容|
|-----|-----|
|OCR エンジンを作成できません|OCR エンジンの作成中にエラーが発生したことを示します|
|データ パス フォルダーが存在しません|言語データの指定されたフォルダーが存在しないことを示します|

### <a name="create-modi-ocr-engine"></a><a name="createmodiengine"></a>MODI OCR エンジンを作成
MODI OCR エンジンを作成

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|MODI 言語|N/A|中国語 (簡体字)、中国語 (繁体字)、チェコ語、デンマーク語、オランダ語、英語、フィンランド語、フランス語、ドイツ語、ギリシャ語、ハンガリー語、イタリア語、日本語、韓国語、ノルウェー語、ポーランド語、ポルトガル語、ロシア語、スペイン語、スウェーデン語、トルコ語|English|MODI エンジンにより検出される画像のテキストの言語|
|画像の幅の乗数|有効|数値|1|画像の幅の乗数|
|画像の高さの乗数|有効|数値|1|画像の高さの乗数|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|OCREngine|OCREngineObject|後の OCR アクションで使う OCR エンジン|


##### <a name="exceptions"></a><a name="createmodiengine_onerror"></a> 例外
|例外|内容|
|-----|-----|
|OCR エンジンを作成できません|OCR エンジンの作成中にエラーが発生したことを示します|

### <a name="extract-text-with-ocr"></a><a name="extracttextwithocr"></a>OCR を使ってテキストを抽出
指定された OCR エンジンを使って指定されたソースからテキストを抽出

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|OCR エンジン|無効|OCREngineObject||OCR 操作に使うエンジン|
|OCR ソース|N/A|スクリーン、前景ウィンドウ、ディスク上のイメージ|Screen|OCR 操作を実行する画像のソース|
|画像ファイル パス|無効|ファイル||OCR 操作を実行する画像のパス|
|検索モード|N/A|特定のソース全体、特定のサブ領域のみ、イメージを基準としたサブ領域|指定されたすべてのソース|OCR 操作に選択したモード|
|Image|無効|イメージの一覧||指定した画像に対するサブ領域の相対位置にスキャンを絞り込むために使う画像|
|許容値|有効|数値|10|最初に選択した画像と比較して、画像がどれだけ異なるかを指定します|
|X1|有効|数値||スキャンを絞り込むサブ領域の開始 X 座標|
|X2|有効|数値||スキャンを絞り込むサブ領域の終了 X 座標|
|Y1|有効|数値||スキャンを絞り込むサブ領域の開始 Y 座標|
|Y2|有効|数値||スキャンを絞り込むサブ領域の終了 Y 座標|
|画像が表示されるまで待機する|N/A|ブール値|無効|画面やフォアグラウンド ウィンドウに画像が表示されるのを待機するかどうか|
|タイムアウト|有効|数値|0|アクションが失敗するまで操作の完了を待機する時間を指定します|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|OcrText|テキスト値|テキスト抽出後の結果|


##### <a name="exceptions"></a><a name="extracttextwithocr_onerror"></a> 例外
|例外|内容|
|-----|-----|
|OCR を使ってテキストを抽出できません|指定されたソースから OCR を使ってテキストを抽出しているときにエラーが発生したことを示します|
|画像ファイルが見つかりません|指定されたパスにファイルが存在しないことを示します|
|ランドマーク画像が見つかりません |ランドマーク画像が存在しないことを示します|
|OCR エンジンが利用できません|OCR エンジンが利用できないことを示します|
|非インタラクティブ モードでは画面からテキストを取得できません|非インタラクティブ モードの場合に、画面からテキストを取得できないことを示します|


