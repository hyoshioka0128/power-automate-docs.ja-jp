---
title: 認識 | Microsoft Docs
description: 認識アクションについての参考情報
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
ms.openlocfilehash: c5845e96434c3e0d97c3739bebc93ace24acec17
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711606"
---
# <a name="cognitive"></a>コグニティブ



Google、Microsoft、または IBM のサービスを使用して、認識操作を実行します

|<!-- --> |
|-----|
|[感情を分析します](#analyzesentimentgoogle)|
|[エンティティ分析](#analyzeentitiesgoogle)|
|[構文を解析します](#analyzesyntaxgoogle)|
|[ラベル検出](#labeldetectiongoogle)|
|[ランドマーク検出](#landmarkdetectiongoogle)|
|[テキスト検出](#textdetectiongoogle)|
|[ロゴ検出](#logodetectiongoogle)|
|[画像プロパティの検出](#imagepropertiesdetectiongoogle)|
|[セーフ サーチ検出](#safesearchdetectiongoogle)|
|[ドキュメントを変換](#convertdocumentibm)|
|[翻訳](#translateibm)|
|[言語を特定します](#identifylanguage)|
|[トーンを分析します](#analyzetoneibm)|
|[画像を分類します](#classifyimageibm)|
|[スペル チェック](#spellcheck)|
|[画像を分析します](#analyzeimagemicrosoft)|
|[画像を記述します](#describeimagemicrosoft)|
|[OCR](#ocrmicrosoft)|
|[画像をタグ付けします](#tagimagemicrosoft)|
|[言語の検出](#detectlanguage)|
|[キー フレーズ](#keyphrases)|
|[センチメント](#sentiment)|

## <a name="google"></a>Google
Google のコグニティブ アクション
## <a name="natural-language"></a>自然言語
テキストの構造と意味を明らかにします
### <a name="analyze-sentiment"></a><a name="analyzesentimentgoogle"></a> 感情分析
「センチメント分析」という名前の Google Cloud Natural Language サービスを呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|API キー|無効|テキスト値||この API 呼び出しに使用する Google Cloud API キーです|
|ドキュメントの種類|N/A|プレーンテキスト、HTML|プレーン テキスト|送信するドキュメントの種類です|
|ドキュメントを提供します|N/A|ファイルから、GCS から|ファイルから|ドキュメントをフル パスで提供するか、Google Cloud Storage URI で提供するかを指定します|
|ファイル パス|無効|ファイル||送信するドキュメントの完全なパス (フォルダー名とファイル名) です|
|GCS コンテンツ URI|無効|テキスト値||Google Cloud Storage にある画像の URI です|
|言語|有効|テキスト値||テキストの言語です|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="analyzesentimentgoogle_onerror"></a> 例外
|例外|内容|
|-----|-----|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|

### <a name="analyze-entities"></a><a name="analyzeentitiesgoogle"></a> エンティティ分析
「エンティティ分析」という名前の Google Cloud Natural Language サービスを呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|API キー|無効|テキスト値||この API 呼び出しに使用する Google Cloud API キーです|
|ドキュメントの種類|N/A|プレーンテキスト、HTML|プレーン テキスト|送信するドキュメントの種類です|
|ファイルを提供します|N/A|ファイルから、GCS から|ファイルから|ドキュメントをフル パスで提供するか、Google Cloud Storage URI で提供するかを指定します|
|ファイル パス|無効|ファイル||送信するドキュメントの完全なパス (フォルダー名とファイル名) です|
|GCS URL|無効|テキスト値||Google Cloud Storage にあるドキュメントの URI です|
|言語|有効|テキスト値||テキストの言語です|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="analyzeentitiesgoogle_onerror"></a> 例外
|例外|内容|
|-----|-----|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|

### <a name="analyze-syntax"></a><a name="analyzesyntaxgoogle"></a> 構文分析
「構文解析」という名前の Google Cloud Natural Language サービスを呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|API キー|無効|テキスト値||この API 呼び出しに使用する Google Cloud API キーです|
|ドキュメントの種類|N/A|プレーンテキスト、HTML|プレーン テキスト|送信するドキュメントの種類です|
|ドキュメントを提供します|N/A|ファイルから、GCS から|ファイルから|ドキュメントをフル パスで提供するか、Google Cloud Storage URI で提供するかを指定します|
|ファイル パス|無効|ファイル||送信するドキュメントの完全なパス (フォルダー名とファイル名) です|
|GCS コンテンツ URI|無効|テキスト値||Google Cloud Storage にある画像の URI です|
|言語|有効|テキスト値||テキストの言語です|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="analyzesyntaxgoogle_onerror"></a> 例外
|例外|内容|
|-----|-----|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|

## <a name="vision"></a>ビジョン
画像にラベルを割り当て、事前に定義されたカテゴリに分類します。 物体検知、顔、印刷テキストや手書きテキストの読み取り
### <a name="label-detection"></a><a name="labeldetectiongoogle"></a> ラベルの検出
「ラベル検出」という名前の Google Cloud Vision サービスを呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|API キー|無効|テキスト値||この API 呼び出しに使用する Google Cloud API キーです|
|画像を提供します|N/A|ファイルから、GCS から|ファイルから|画像をフル パスで提供するか、Google Cloud Storage URI で提供するかを指定します|
|画像ファイル|無効|ファイル||送信する画像ファイルの完全なパス (フォルダー名とファイル名) です|
|GCS 画像 URI|無効|テキスト値||Google Cloud Storage にある画像の URI です|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="labeldetectiongoogle_onerror"></a> 例外
|例外|内容|
|-----|-----|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|

### <a name="landmark-detection"></a><a name="landmarkdetectiongoogle"></a> ランドマークの検出
「ランドマーク検出」という名前の Google Cloud Vision サービスを呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|API キー|無効|テキスト値||この API 呼び出しに使用する Google Cloud API キーです|
|画像を提供します|N/A|ファイルから、GCS から|ファイルから|画像をフル パスで提供するか、Google Cloud Storage URI で提供するかを指定します|
|画像ファイル パス|無効|ファイル||送信する画像ファイルの完全なパス (フォルダー名とファイル名) です|
|GCS 画像 URI|無効|テキスト値||Google Cloud Storage にある画像の URI です|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="landmarkdetectiongoogle_onerror"></a> 例外
|例外|内容|
|-----|-----|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|

### <a name="text-detection"></a><a name="textdetectiongoogle"></a>テキストの検出
「テキスト検出」という名前の Google Cloud Vision サービスを呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|API キー|無効|テキスト値||この API 呼び出しに使用する Google Cloud API キーです|
|画像を提供します|N/A|ファイルから、GCS から|ファイルから|画像をフル パスで提供するか、Google Cloud Storage URI で提供するかを指定します|
|画像ファイル|無効|ファイル||送信する画像ファイルの完全なパス (フォルダー名とファイル名) です|
|GCS 画像 URI|無効|テキスト値||Google Cloud Storage にある画像の URI です|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="textdetectiongoogle_onerror"></a> 例外
|例外|内容|
|-----|-----|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|

### <a name="logo-detection"></a><a name="logodetectiongoogle"></a>ロゴの検出
「ロゴ検出」という名前の Google Cloud Vision サービスを呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|API キー|無効|テキスト値||この API 呼び出しに使用する Google Cloud API キーです|
|画像を提供します|N/A|ファイルから、GCS から|ファイルから|画像をフル パスで提供するか、Google Cloud Storage URI で提供するかを指定します|
|画像ファイル|無効|ファイル||送信する画像ファイルの完全なパス (フォルダー名とファイル名) です|
|GCS 画像 URI|無効|テキスト値||Google Cloud Storage にある画像の URI です|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="logodetectiongoogle_onerror"></a> 例外
|例外|内容|
|-----|-----|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|

### <a name="image-properties-detection"></a><a name="imagepropertiesdetectiongoogle"></a> イメージプロパティの検出
「画像プロパティの検出」という名前の Google Cloud Vision サービスを呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|API キー|無効|テキスト値||この API 呼び出しに使用する Google Cloud API キーです|
|画像を提供します|N/A|ファイルから、GCS から|ファイルから|画像をフル パスで提供するか、Google Cloud Storage URI で提供するかを指定します|
|画像ファイル|無効|ファイル||送信する画像ファイルの完全なパス (フォルダー名とファイル名) です|
|GCS 画像 URI|無効|テキスト値||Google Cloud Storage にある画像の URI です|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="imagepropertiesdetectiongoogle_onerror"></a> 例外
|例外|内容|
|-----|-----|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|

### <a name="safe-search-detection"></a><a name="safesearchdetectiongoogle"></a> セーフ サーチの検出
「セーフ サーチ検出」という名前の Google Cloud Vision サービスを呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|API キー|無効|テキスト値||この API 呼び出しに使用する Google Cloud API キーです|
|画像を提供します|N/A|ファイルから、GCS から|ファイルから|画像をフル パスで提供するか、Google Cloud Storage URI で提供するかを指定します|
|画像ファイル|無効|ファイル||送信する画像ファイルの完全なパス (フォルダー名とファイル名) です|
|GCS 画像 URI|無効|テキスト値||Google Cloud Storage にある画像の URI です|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="safesearchdetectiongoogle_onerror"></a> 例外
|例外|内容|
|-----|-----|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|

## <a name="ibm"></a>IBM
IBM のコグニティブ アクション
## <a name="document-conversion"></a>文書変換
ファックス、電子メール、PDF などの構造化されていないドキュメントを、EDI やその他の構造化されたフォーマットに変換します
### <a name="convert-document"></a><a name="convertdocumentibm"></a>ドキュメントの変換
「文書変換」という名前の IBM サービスを呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ユーザー名|無効|テキスト値||この呼び出しに使用するユーザー名です|
|パスワード|無効|暗号化された値||この呼び出しに使用するパスワードです|
|バージョン日付|無効|テキスト値||使用する API のリリース日です|
|ファイル パス|無効|ファイル||分析するファイルのパスです|
|MIME タイプ|N/A|text/html、text/xhtml+xml、application/pdf、application/msword、application/vnd.openxmlformats-officedocument.wordprocessingml.document|text/html|ファイルの MIME の種類です|
|変換のターゲット|N/A|回答ユニット、標準化 HTML、標準化テキスト|回答単位|変換の出力形式です|
|回答単位|有効|テキスト値||見出しレベル (コンマ区切り文字列) です|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 呼び出しの結果です|
|StatusCode|数値|API 呼び出しの状態コードです|


##### <a name="exceptions"></a><a name="convertdocumentibm_onerror"></a> 例外
|例外|内容|
|-----|-----|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|

## <a name="language-translator"></a>言語翻訳機能
ドキュメント、アプリ、Web ページを翻訳します
### <a name="translate"></a><a name="translateibm"></a> 翻訳
「翻訳」という名前の IBM サービスを呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|API キー|無効|テキスト値||この呼び出しに使用する API キーです|
|バージョン日付|無効|テキスト値||使用する API のリリース日です|
|サービス エンドポイントの場所です|N/A|米国南部、米国東部、ヨーロッパ、オーストラリア、日本、英国、韓国|米国東部|アカウントのサービス ロケーション。 リソース セクションの IBM 管理から参照できます|
|インスタンス ID|無効|テキスト値||サービスのインスタンス ID です。|
|翻訳モード|N/A|モデル ID、ソースとターゲット|モデル ID|この呼び出しに使用するモードを指定します|
|モデル ID|無効|テキスト値||テキストの翻訳に使用される翻訳モデルの一意のモデル ID です|
|ソース|無効|テキスト値||テキストのソース言語です|
|ターゲット|無効|テキスト値||翻訳のターゲット言語 (2 文字または 5 文字の言語コード) です|
|テキスト|無効|テキスト値の一覧||送信するテキスト、または個別に翻訳する単語の一覧です|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 呼び出しの結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="translateibm_onerror"></a> 例外
|例外|内容|
|-----|-----|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|

### <a name="identify-language"></a><a name="identifylanguage"></a> 言語の認識
「言語の認識」という名前のIBMサービスを呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|API キー|無効|テキスト値||この呼び出しに使用する API キーです|
|バージョン日付|無効|テキスト値||使用する API のリリース日です|
|サービス エンドポイントの場所です|N/A|米国南部、米国東部、ヨーロッパ、オーストラリア、日本、英国、韓国|米国東部|アカウントのサービス ロケーション。 リソース セクションの IBM 管理から参照できます|
|インスタンス ID|無効|テキスト値||サービスのインスタンス ID です。|
|テキスト|無効|テキスト値||分析するテキストです|
|コンテンツの種類|有効|テキスト値|text/plain|要求された値の形式です|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 呼び出しの結果です|
|StatusCode|数値|API 呼び出しの状態コードです|


##### <a name="exceptions"></a><a name="identifylanguage_onerror"></a> 例外
|例外|内容|
|-----|-----|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|

## <a name="tone-analyzer"></a>トーン分析機能
記述テキストの感情や言葉のトーンを検出します
### <a name="analyze-tone"></a><a name="analyzetoneibm"></a> トーンの分析
「トーン分析」という名前の IBM サービスを呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|API キー|無効|テキスト値||この呼び出しに使用する API キーです|
|バージョン日付|無効|テキスト値||使用する API のリリース日です|
|サービス エンドポイントの場所です|N/A|米国南部、米国東部、ヨーロッパ、オーストラリア、日本、英国、韓国|米国東部|アカウントのサービス ロケーション。 リソース セクションの IBM 管理から参照できます|
|インスタンス ID|無効|テキスト値||サービスのインスタンス ID です。|
|テキストを提供します|N/A|テキストから、ファイルから|テキストから|分析するテキストの提供方法を指定します|
|テキスト|無効|テキスト値||分析するテキストです|
|ファイル パス|無効|ファイル||分析するファイルのパスです|
|コンテンツの種類|N/A|text/plain、text/html、application/json|text/plain|送信されるテキストのコンテンツ タイプです|
|トーン|有効|テキスト値||結果をフィルター処理するトーンです (省略可能)。|
|文|有効|テキスト値||文の分析を削除するかどうかを指定します|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 呼び出しの結果です|
|StatusCode|数値|API 呼び出しの状態コードです|


##### <a name="exceptions"></a><a name="analyzetoneibm_onerror"></a> 例外
|例外|内容|
|-----|-----|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|

## <a name="visual-recognition"></a>視覚認識
視覚的コンテンツから意味を検出します。 シーン、オブジェクト、その他のコンテンツのイメージを分析する
### <a name="classify-image"></a><a name="classifyimageibm"></a> イメージの分類
「画像分類」という名前の IBM サービスを呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|API キー|無効|テキスト値||この呼び出しに使用する API キーです|
|バージョン日付|無効|テキスト値||使用する API のリリース日です|
|サービス エンドポイントの場所です|N/A|米国南部、ヨーロッパ、韓国|米国南部|アカウントのサービス ロケーション。 リソース セクションの IBM 管理から参照できます|
|インスタンス ID|無効|テキスト値||サービスのインスタンス ID です。|
|画像を提供します|N/A|ファイルから、GCS から|ファイルから|画像の提供方法を指定します|
|画像ファイル パス|無効|ファイル||分析する画像のパスです|
|画像の URL|無効|テキスト値||分析する画像の URL です|
|所有者|有効|テキスト値|me|分類子です。コンマ区切りリストとして使用します|
|分類子 ID|有効|テキスト値|既定|分類子 ID です。コンマ区切りリストとして使用します|
|しきい値|有効|テキスト値||クラスが応答に表示される最小スコアです。浮動小数点値で指定します|
|言語|有効|テキスト値||出力の言語です|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 呼び出しの結果です|
|StatusCode|数値|API 呼び出しの状態コードです|


##### <a name="exceptions"></a><a name="classifyimageibm_onerror"></a> 例外
|例外|内容|
|-----|-----|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|

## <a name="microsoft"></a>Microsoft
Microsoft のコグニティブ アクション
## <a name="bing-spell-check"></a>Bing Spell Check
スペル エラーを修正したり、名前、ブランド名、俗語の違いを認識したり、同音異義語を理解したりします
### <a name="spell-check"></a><a name="spellcheck"></a> スペル チェック
「Bing Spell Check」という名前の Microsoft Cognitive Services を呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|サブスクリプション キー|無効|テキスト値||この API 呼び出しに使用するサブスクリプション キーです|
|テキスト|無効|テキスト値の一覧||送信するテキストまたはテキストのリストです|
|モード|有効|テキスト値||スペル チェック モードを指定します|
|Mkt|有効|テキスト値||プルーフ モードは、次の言語コードのみに対応しています: en-us、es-es、pt-br。 スペル モードでは、すべての言語コードに対応しています|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="spellcheck_onerror"></a> 例外
|例外|内容|
|-----|-----|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|

## <a name="computer-vision"></a>Computer Vision
画像を分析し、データを抽出します 
### <a name="analyze-image"></a><a name="analyzeimagemicrosoft"></a> イメージの分析
「Analyze Image」という名前の Microsoft Cognitive Services を呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|サーバーの場所|N/A|米国西部、米国西部 2、米国東部、米国東部 2、米国中西部、米国中南部、西ヨーロッパ、北ヨーロッパ、東南アジア、東アジア、オーストラリア東部、ブラジル南部、カナダ中部、 インド中部、英国南部、東日本|米国西部|この API 呼び出しに使用するサーバーの場所です|
|サブスクリプション キー|無効|テキスト値||この API 呼び出しに使用するサブスクリプション キーです|
|画像を提供します|N/A|ファイルから、GCS から|ファイルから|画像をフル パスで提供するか、URL アドレスで提供するかを指定します|
|画像ファイル|無効|ファイル||送信する画像ファイルの完全なパス (フォルダー名とファイル名) です|
|画像の URL|無効|テキスト値||画像の URL アドレスです|
|ビジュアル機能|有効|テキスト値||戻す視覚的特徴の種類を示すテキスト値です。 複数の値は、コンマで区切る必要があります。 例: categories, tags, description|
|詳細情報|有効|テキスト値||戻すドメイン固有の詳細を示すテキスト値です。 複数の値は、コンマで区切る必要があります|
|言語|有効|テキスト値||戻す言語を示すテキスト値です。 サービスは、指定された言語で認識結果を返します|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="analyzeimagemicrosoft_onerror"></a> 例外
|例外|内容|
|-----|-----|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|

### <a name="describe-image"></a><a name="describeimagemicrosoft"></a> イメージの説明
「Describe Image」という名前の Microsoft Cognitive Services を呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|サーバーの場所|N/A|米国西部、米国西部 2、米国東部、米国東部 2、米国中西部、米国中南部、西ヨーロッパ、北ヨーロッパ、東南アジア、東アジア、オーストラリア東部、ブラジル南部、カナダ中部、 インド中部、英国南部、東日本|米国西部|この API 呼び出しに使用するサーバーの場所です|
|サブスクリプション キー|無効|テキスト値||この API 呼び出しに使用するサブスクリプション キーです|
|画像を提供します|N/A|ファイルから、GCS から|ファイルから|画像をフル パスで提供するか、URL アドレスで提供するかを指定します|
|画像ファイル|無効|ファイル||送信する画像ファイルの完全なパス (フォルダー名とファイル名) です|
|画像の URL|無効|テキスト値||画像の URL アドレスです|
|候補の最大数|有効|テキスト値||戻される説明候補の最大数です。 既定値は 1 です|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="describeimagemicrosoft_onerror"></a> 例外
|例外|内容|
|-----|-----|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|

### <a name="ocr"></a><a name="ocrmicrosoft"></a> OCR
「OCR」という名前の Microsoft Cognitive Services を呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|サーバーの場所|N/A|米国西部、米国西部 2、米国東部、米国東部 2、米国中西部、米国中南部、西ヨーロッパ、北ヨーロッパ、東南アジア、東アジア、オーストラリア東部、ブラジル南部、カナダ中部、 インド中部、英国南部、東日本|米国西部|この API 呼び出しに使用するサーバーの場所です|
|サブスクリプション キー|無効|テキスト値||この API 呼び出しに使用するサブスクリプション キーです|
|画像を提供します|N/A|ファイルから、GCS から|ファイルから|画像をフル パスで提供するか、URL アドレスで提供するかを指定します|
|画像ファイル|無効|ファイル||送信する画像ファイルの完全なパス (フォルダー名とファイル名) です|
|画像の URL|無効|テキスト値||画像の URL アドレスです|
|言語|有効|テキスト値||画像内で検出するテキストの BCP-47 言語コードです|
|向きを検出します|有効|テキスト値||画像のテキストの向きを検出するかどうかを指定します|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="ocrmicrosoft_onerror"></a> 例外
|例外|内容|
|-----|-----|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|

### <a name="tag-image"></a><a name="tagimagemicrosoft"></a> イメージをタグ付けする
「Tag Image」という名前の Microsoft Cognitive Services を呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|サーバーの場所|N/A|米国西部、米国西部 2、米国東部、米国東部 2、米国中西部、米国中南部、西ヨーロッパ、北ヨーロッパ、東南アジア、東アジア、オーストラリア東部、ブラジル南部、カナダ中部、 インド中部、英国南部、東日本|米国西部|この API 呼び出しに使用するサーバーの場所です|
|サブスクリプション キー|無効|テキスト値||この API 呼び出しに使用するサブスクリプション キーです|
|画像を提供します|N/A|ファイルから、GCS から|ファイルから|画像をフル パスで提供するか、URL アドレスで提供するかを指定します|
|画像ファイル|無効|ファイル||送信する画像ファイルの完全なパス (フォルダー名とファイル名) です|
|画像の URL|無効|テキスト値||画像の URL アドレスです|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="tagimagemicrosoft_onerror"></a> 例外
|例外|内容|
|-----|-----|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|

## <a name="text-analytics"></a>テキスト分析
テキストから、センチメント、キー語句、固有名詞、言語を検出します
### <a name="detect-language"></a><a name="detectlanguage"></a> 言語の検出
「テキスト分析 - 言語の自動検出」という名前の Microsoft Cognitive Services を呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|サーバーの場所|N/A|米国西部、米国西部 2、米国東部、米国東部 2、米国中西部、米国中南部、西ヨーロッパ、北ヨーロッパ、東南アジア、東アジア、オーストラリア東部、ブラジル南部、カナダ中部、 インド中部、英国南部、東日本|米国西部|この API 呼び出しに使用するサーバーの場所です|
|サブスクリプション キー|無効|テキスト値||この API 呼び出しに使用するサブスクリプション キーです|
|テキスト|無効|テキスト値||分析するテキストです|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="detectlanguage_onerror"></a> 例外
|例外|内容|
|-----|-----|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|

### <a name="key-phrases"></a><a name="keyphrases"></a> キー フレーズ
「テキスト分析 - キー語句」という名前の Microsoft Cognitive Services を呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|サーバーの場所|N/A|米国西部、米国西部 2、米国東部、米国東部 2、米国中西部、米国中南部、西ヨーロッパ、北ヨーロッパ、東南アジア、東アジア、オーストラリア東部、ブラジル南部、カナダ中部、 インド中部、英国南部、東日本|米国西部|この API 呼び出しに使用するサーバーの場所です|
|サブスクリプション キー|無効|テキスト値||この API 呼び出しに使用するサブスクリプション キーです|
|テキスト|無効|テキスト値の一覧||分析するテキストまたはテキストのリストです|
|言語|有効|テキスト値||テキストの言語です|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="keyphrases_onerror"></a> 例外
|例外|内容|
|-----|-----|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|

### <a name="sentiment"></a><a name="sentiment"></a> センチメント
「テキスト分析 - センチメント」という名前の Microsoft Cognitive Services を呼び出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|サーバーの場所|N/A|米国西部、米国西部 2、米国東部、米国東部 2、米国中西部、米国中南部、西ヨーロッパ、北ヨーロッパ、東南アジア、東アジア、オーストラリア東部、ブラジル南部、カナダ中部、 インド中部、英国南部、東日本|米国西部|この API 呼び出しに使用するサーバーの場所です|
|サブスクリプション キー|無効|テキスト値||この API 呼び出しに使用するサブスクリプション キーです|
|テキスト|無効|テキスト値の一覧||テキスト|
|言語|有効|テキスト値||テキストの言語を示す 2 文字 (ISO 639-1 表現)|
|タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は失敗します|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|JSONResponse|カスタム オブジェクト|API 応答の結果です|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="sentiment_onerror"></a> 例外
|例外|内容|
|-----|-----|
|要求がタイムアウトしました|要求の実行中にタイムアウトが発生したことを示します|
|Cognitive Services を呼び出すことができませんでした|Cognitive Services の呼び出し中に問題が発生したことを示します|


