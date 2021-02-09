---
title: Web | Microsoft Docs
description: Web のアクションに関する参考情報
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
ms.openlocfilehash: f6d574d5881f87792ff299dbb5ff5f3df9df444a
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711609"
---
# <a name="web"></a>Web



Web アプリケーションや Web サービスと直接通信します

Web アクションの使用方法の詳細については、[こちら](../automation-web.md)を参照してください


|<!-- --> |
|-----|
|[Web からダウンロードします](#downloadfromweb)|
|[Web サービスを呼び出します](#invokewebservicebase)|

### <a name="download-from-web"></a><a name="downloadfromweb"></a> Web からダウンロードする
テキストまたはファイルを Web からダウンロードして保存します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|URL|無効|テキスト値||Web ページまたはファイルの URL です|
|メソッド|N/A|GET、POST|取得|Web サイトの情報を取得する方法を指定します。 必要なすべての情報が URL に含まれている場合は GET を使用し、追加情報 (パスワードなど) を入力する場合は POST を使用します|
|POST パラメーター|無効|Datatable||2 つの列を持つデータ テーブルの形式の POST パラメーターです|
|応答を保存します|N/A|テキストを変数に入れる (Webページの場合)、ディスクに保存する (ファイルの場合)|テキストを変数に変換します (Web ページ用)|返されたデータの保存方法を指定します|
|ファイル名|N/A|元のファイル名を保持する (宛先フォルダーのみを指定)、フルパスを指定する (宛先フォルダー + カスタムファイル名)|元のファイル名を維持します (宛先フォルダーのみを指定します)|ダウンロードしたファイルの元のファイル名を保持するか、新しい名前を指定するかを指定します|
|保存先フォルダー|無効|フォルダー||Web サーバーから返されたファイルが保存されるフォルダーです|
|宛先ファイル パス|無効|ファイル||Web サーバーによって返されたファイルの完全なパス (フォルダー名とファイル名) が保存されます|
|接続タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は中止されます|
|リダイレクトに追従します|N/A|ブール値|有効|Web サーバーから別の Web ページまたは Web サイトへのリダイレクトを許可するかどうかを指定します|
|Cookie をクリア|N/A|ブール値|無効|この自動化の間に、類似のアクションで作成されたすべての Cookie をクリアするかどうかを指定します|
|ユーザー エージェント|有効|テキスト値|Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.8.1.21) Gecko/20100312 Firefox/3.6|どのブラウザー ID で見るかを指定します。 一部の Web サーバーは、ブラウザー ID が選択されない限りアクセスを許可しません|
|エンコード|N/A|自動検出、IBM037:IBM EBCDIC (米国-カナダ)、IBM437:OEM 米国、IBM500:IBM EBCDIC (国際)、ASMO-708: アラビア語 (ASMO 708)、DOS-720:アラビア語 (DOS)、ibm737: ギリシャ語 (DOS)、ibm775:Baltic (DOS)、ibm850: 中央ヨーロッパ (DOS)、ibm852: 中央ヨーロッパ (DOS)、IBM855:OEM キリル、ibm857: トルコ語 (DOS)、IBM00858:OEM Multilingual Latin I、IBM860: ポルトガル語 (DOS)、ibm861: アイスランド (DOS)、DOS-862: ヘブライ語 (DOS)、IBM863: フランス語 (カナダ) (DOS)、IBM864: アラビア語 (864)、IBM865: 北欧 (DOS)、cp866: キリル (DOS)、ibm869: ギリシャ語、モダン (DOS)、IBM870:IBM EBCDIC (多言語ラテン2)、windows-874: タイ語 (Windows)、cp875:IBM EBCDIC (ギリシャ語モダン)、shift_jis: 日本語 (Shift-JIS)、gb2312: 中国語簡略化 (GB2312)、ks_c_5601-1987: 韓国語、big5: 繁体字中国語 (Big5)、IBM1026:IBM EBCDIC (トルコ語ラテン語-5)、IBM01047:IBM Latin-1、IBM01140:IBM EBCDIC (米国-カナダ-ユーロ)、IBM01141:IBM EBCDIC (ドイツ-ユーロ)、IBM01142:IBM EBCDIC (デンマーク-ノルウェー-ユーロ)、IBM01143:IBM EBCDIC (フィンランド -スウェーデン-ユーロ)、IBM01144:IBM EBCDIC (イタリア-ユーロ)、IBM01145:IBM EBCDIC (スペイン-ユーロ)、IBM01146:IBM EBCDIC (英国-ユーロ)、IBM01147:IBM EBCDIC (フランス-ユーロ)、IBM01148:IBM EBCDIC (International-Euro)、IBM01149:IBM EBCDIC (Icelandic-Euro)、utf-16:Unicode、utf-16BE:Unicode (Big-Endian)、windows-1250:Central European (Windows)、windows-1251:Cyrillic (Windows)、Windows-1252: 西ヨーロッパ (Windows)、windows-1253:ギリシャ語 (Windows)、windows-1254:トルコ語 (Windows)、windows-1255: ヘブライ語 (Windows)、windows-1256: アラビア語 (Windows)、windows- 1257: バルト語 (Windows)、windows-1258: ベトナム語 (Windows)、Johab: 韓国語 (Johab)、macintosh: 西ヨーロッパ (Mac)、x-mac-Japanese: 日本語 (Mac)、x-mac-chinesetrad: 繁体字中国語 (Mac)、x-mac-korean: 韓国語 (Mac)、x-mac-arabic: アラビア語 (Mac)、x-mac-hebrew: ヘブライ語 (Mac)、x-mac-greek: ギリシャ語 (Mac)、x- mac-cyrillic:Cyrillic (Mac)、x-mac-chinesesimp:Chinese Simplified (Mac)、x-mac-romanian:ルーマニア語 (Mac)、x-mac-ukrainian:ウクライナ語 (Mac)、x-mac-thai: タイ語 (Mac)、x-mac-ce: 中央ヨーロッパ (Mac)、x-mac-icelandic: アイスランド語 (Mac)、x-mac-turkish: トルコ語 (Mac)、x-mac-croatian: クロアチア語 (Mac)、utf-32: Unicode (UTF-32)、utf-32BE:Unicode (UTF-32 ビッグエンディアン)、x-Chinese-CNS: 繁体字中国語 (CNS)、x-cp20001: TCA 台湾、x-Chinese-Eten: 繁体字中国語 (Eten)、x-cp20003:IBM5550 台湾、x-cp20004:TeleText 台湾、x-cp20005:Wang 台湾、x-IA5: 西ヨーロッパ (IA5)、x-IA5-ドイツ語 : ドイツ語 (IA5)、x- IA5-スウェーデン語 : スウェーデン語 (IA5)、x-IA5-ノルウェー語:ノルウェー語 (IA5)、us-ascii:US-ASCII、x-cp20261:T.61、x-cp20269:ISO-6937、IBM273:IBM EBCDIC (ドイツ)、IBM277:IBM EBCDIC (デンマーク-ノルウェー)、IBM278:IBM EBCDIC (フィンランド-スウェーデン)、IBM280:IBM EBCDIC (イタリア)、IBM284:IBM EBCDIC (スペイン)、IBM285:IBM EBCDIC (英国)、IBM290:IBM EBCDIC (日本のカタカナ)、IBM297:IBM EBCDIC (フランス)、IBM420:IBM EBCDIC (アラビア語)、IBM423:IBM EBCDIC (ギリシャ語)、IBM424:IBM EBCDIC (ヘブライ語)、x-EBCDIC-KoreanExtended:IBM EBCDIC (韓国語拡張)、IBM-タイ語:IBM EBCDIC (タイ語)、k oi8-r:Cyrillic (KOI8-R)、IBM871:IBM EBCDIC (アイスランド語)、IBM880:IBM EBCDIC (キリル ロシア語)、IBM905:IBM EBCDIC (トルコ語)、IBM00924:IBM Latin-1、EUC-JP: 日本語 (JIS 0208-1990 および 0212-1990)、x-cp20936: 簡体字中国語 (GB2312-80)、x-cp20949: 韓国語 Wansung、cp1025:IBM EBCDIC (キリル セルビア語 ブルガリア語)、koi8-u: キリル語 (KOI8-U)、iso- 8859-1: 西ヨーロッパ (ISO)、iso-8859-2: 中央ヨーロッパ (ISO)、iso-8859-3: ラテン3 (ISO)、iso-8859-4: バルト海 (ISO)、iso-8859-5: キリル (ISO)、iso-8859-6: アラビア語 (ISO)、iso-8859-7: ギリシャ語 (ISO)、iso-8859-8: ヘブライ語 (ISO-Visual)、iso-8859-9: トルコ語 (ISO)、iso-8859-13: エストニア語 (ISO)、iso-8859-15: ラテン語 9 (ISO)、x-Europa:Europa、iso-8859-8-i: ヘブライ語 (ISO-Logical)、iso-2022- jp: 日本語 (JIS)、csISO2022JP: 日本語 (JIS-1バイトカナを許可)、iso-2022-jp: 日本語 (JIS-1バイトカナを許可-SO / SI)、iso-2022-kr: 韓国語 (ISO)、x-cp50227: 簡体字中国語 (ISO-2022)、euc-jp: 日本語 (EUC)、EUC-CN: 簡体字中国語 (EUC)、euc-kr: 韓国 (EUC)、hz-gb-2312: 簡体字中国語 (HZ)、GB18030: 簡体字中国語 (GB18030)、x-iscii-de:ISCII デーヴァナーガリー、x-iscii-be:ISCII ベンガル語、x-iscii-ta:ISCII タミール語、x-iscii-te:ISCII テルグ語、x-iscii-as:ISCII アッサム語、x-iscii-または : ISCII オリヤー語、x-iscii-ka:ISCII カンナダ語、x-iscii-ma:ISCII マラヤーラム語、x-iscii -gu:ISCII グジャラート語、x-iscii-pa:ISCII パンジャブ語、utf-7:Unicode (UTF-7)、utf-8:Unicode (UTF-8)|自動検出|web ページに使用するエンコード。 自動検出オプションが選択された場合、使用されるエンコードは Web サーバーで指定されます|
|信頼されていない証明書を受け入れます|N/A|ブール値|無効|信頼されていない証明書を受け入れるかどうかを指定します|
|ユーザー資格情報|N/A|ブール値|無効|web サーバーが認証を必要とするかどうかを指定します。 このプロパティは HTTP 認証を参照します (ブラウザーがポップアップ ウィンドウを表示してユーザー名とパスワードを要求する場合)|
|ユーザー名|無効|テキスト値||Web サーバーのユーザー名です|
|パスワード|無効|暗号化された値||Web サーバーのパスワードです|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|DownloadedFile|ファイル|ダウンロードされたファイルです|
|WebPageText|テキスト値|Web ページ テキストです|


##### <a name="exceptions"></a><a name="downloadfromweb_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ディレクトリが存在しません|必要なディレクトリが存在しないことを示します|
|Web からのダウンロード エラーです|Web からのダウンロードで問題が発生したことを示します|

### <a name="invoke-web-service"></a><a name="invokewebservicebase"></a> Web サービスを呼び出します
データを送信して Web サービスを呼び出し、Web サービスから応答を取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|URL|無効|テキスト値||Web サービスの URL です|
|メソッド|N/A|GET、POST、CONNECT、HEAD、PUT、DELETE、OPTIONS、TRACE、PATCH|取得|Web サービスを呼び出すために使用される HTTP メソッドです|
|承認|有効|テキスト値|application/xml|Web サービスの応答で受け入れられるコンテンツ タイプです|
|コンテンツの種類|有効|テキスト値|application/xml|Web サービスに送信される要求のコンテンツ タイプです|
|カスタム ヘッダー|有効|テキスト値||Web サービスに送信される要求に含まれるカスタム ヘッダーです|
|要求本文|有効|テキスト値||Web サービスに送信される要求の本文です|
|応答を保存します|N/A|テキストを変数に入れる (Webページの場合)、ディスクに保存する (ファイルの場合)|テキストを変数に変換します (Web ページ用)|返されたデータの保存方法を指定します|
|ファイル名|N/A|元のファイル名を保持する (宛先フォルダーのみを指定)、フルパスを指定する (宛先フォルダー + カスタムファイル名)|元のファイル名を維持します (宛先フォルダーのみを指定します)|ダウンロードしたファイルの元のファイル名を保持するか、新しい名前を指定するかを指定します|
|保存先フォルダー|無効|フォルダー||Web サービスから返されたファイルが保存されるフォルダーです|
|宛先ファイル パス|無効|ファイル||Web サービスによって返されたファイルの完全なパス (フォルダー名とファイル名) が保存されます|
|接続タイムアウト|有効|数値|30|エージェントがサーバーとの接続が確立するまで待機する時間 (秒) です。この時間を経過すると、接続は中止されます|
|リダイレクトに追従します|N/A|ブール値|有効|Web サーバーから別の Web サービスへのリダイレクトを許可するかどうかを指定します|
|Cookie をクリア|N/A|ブール値|無効|この自動化で、このアクションの前に、類似のアクションで作成されたすべての Cookie をクリアするかどうかを指定します|
|エラー状態で失敗します|N/A|ブール値|無効|呼び出された Web サービスの応答で、エラーを表す応答を、正常な応答であるかのように処理する (すべての例外を非表示にする) か、または関連する例外を発生させるかを指定します|
|要求本文をエンコードします|N/A|ブール値|有効|呼び出す前に、要求本文を URL エンコードするかどうかを指定します|
|ユーザー エージェント|有効|テキスト値|Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.8.1.21) Gecko/20100312 Firefox/3.6|どのブラウザー ID で見るかを指定します。 一部の Web サーバーは、ブラウザー ID が選択されない限りアクセスを許可しません|
|エンコード|N/A|自動検出、IBM037:IBM EBCDIC (米国-カナダ)、IBM437:OEM 米国、IBM500:IBM EBCDIC (国際)、ASMO-708: アラビア語 (ASMO 708)、DOS-720:アラビア語 (DOS)、ibm737: ギリシャ語 (DOS)、ibm775:Baltic (DOS)、ibm850: 中央ヨーロッパ (DOS)、ibm852: 中央ヨーロッパ (DOS)、IBM855:OEM キリル、ibm857: トルコ語 (DOS)、IBM00858:OEM Multilingual Latin I、IBM860: ポルトガル語 (DOS)、ibm861: アイスランド (DOS)、DOS-862: ヘブライ語 (DOS)、IBM863: フランス語 (カナダ) (DOS)、IBM864: アラビア語 (864)、IBM865: 北欧 (DOS)、cp866: キリル (DOS)、ibm869: ギリシャ語、モダン (DOS)、IBM870:IBM EBCDIC (多言語ラテン2)、windows-874: タイ語 (Windows)、cp875:IBM EBCDIC (ギリシャ語モダン)、shift_jis: 日本語 (Shift-JIS)、gb2312: 中国語簡略化 (GB2312)、ks_c_5601-1987: 韓国語、big5: 繁体字中国語 (Big5)、IBM1026:IBM EBCDIC (トルコ語ラテン語-5)、IBM01047:IBM Latin-1、IBM01140:IBM EBCDIC (米国-カナダ-ユーロ)、IBM01141:IBM EBCDIC (ドイツ-ユーロ)、IBM01142:IBM EBCDIC (デンマーク-ノルウェー-ユーロ)、IBM01143:IBM EBCDIC (フィンランド -スウェーデン-ユーロ)、IBM01144:IBM EBCDIC (イタリア-ユーロ)、IBM01145:IBM EBCDIC (スペイン-ユーロ)、IBM01146:IBM EBCDIC (英国-ユーロ)、IBM01147:IBM EBCDIC (フランス-ユーロ)、IBM01148:IBM EBCDIC (International-Euro)、IBM01149:IBM EBCDIC (Icelandic-Euro)、utf-16:Unicode、utf-16BE:Unicode (Big-Endian)、windows-1250:Central European (Windows)、windows-1251:Cyrillic (Windows)、Windows-1252: 西ヨーロッパ (Windows)、windows-1253:ギリシャ語 (Windows)、windows-1254:トルコ語 (Windows)、windows-1255: ヘブライ語 (Windows)、windows-1256: アラビア語 (Windows)、windows- 1257: バルト語 (Windows)、windows-1258: ベトナム語 (Windows)、Johab: 韓国語 (Johab)、macintosh: 西ヨーロッパ (Mac)、x-mac-Japanese: 日本語 (Mac)、x-mac-chinesetrad: 繁体字中国語 (Mac)、x-mac-korean: 韓国語 (Mac)、x-mac-arabic: アラビア語 (Mac)、x-mac-hebrew: ヘブライ語 (Mac)、x-mac-greek: ギリシャ語 (Mac)、x- mac-cyrillic:Cyrillic (Mac)、x-mac-chinesesimp:Chinese Simplified (Mac)、x-mac-romanian:ルーマニア語 (Mac)、x-mac-ukrainian:ウクライナ語 (Mac)、x-mac-thai: タイ語 (Mac)、x-mac-ce: 中央ヨーロッパ (Mac)、x-mac-icelandic: アイスランド語 (Mac)、x-mac-turkish: トルコ語 (Mac)、x-mac-croatian: クロアチア語 (Mac)、utf-32: Unicode (UTF-32)、utf-32BE:Unicode (UTF-32 ビッグエンディアン)、x-Chinese-CNS: 繁体字中国語 (CNS)、x-cp20001: TCA 台湾、x-Chinese-Eten: 繁体字中国語 (Eten)、x-cp20003:IBM5550 台湾、x-cp20004:TeleText 台湾、x-cp20005:Wang 台湾、x-IA5: 西ヨーロッパ (IA5)、x-IA5-ドイツ語 : ドイツ語 (IA5)、x- IA5-スウェーデン語 : スウェーデン語 (IA5)、x-IA5-ノルウェー語:ノルウェー語 (IA5)、us-ascii:US-ASCII、x-cp20261:T.61、x-cp20269:ISO-6937、IBM273:IBM EBCDIC (ドイツ)、IBM277:IBM EBCDIC (デンマーク-ノルウェー)、IBM278:IBM EBCDIC (フィンランド-スウェーデン)、IBM280:IBM EBCDIC (イタリア)、IBM284:IBM EBCDIC (スペイン)、IBM285:IBM EBCDIC (英国)、IBM290:IBM EBCDIC (日本のカタカナ)、IBM297:IBM EBCDIC (フランス)、IBM420:IBM EBCDIC (アラビア語)、IBM423:IBM EBCDIC (ギリシャ語)、IBM424:IBM EBCDIC (ヘブライ語)、x-EBCDIC-KoreanExtended:IBM EBCDIC (韓国語拡張)、IBM-タイ語:IBM EBCDIC (タイ語)、k oi8-r:Cyrillic (KOI8-R)、IBM871:IBM EBCDIC (アイスランド語)、IBM880:IBM EBCDIC (キリル ロシア語)、IBM905:IBM EBCDIC (トルコ語)、IBM00924:IBM Latin-1、EUC-JP: 日本語 (JIS 0208-1990 および 0212-1990)、x-cp20936: 簡体字中国語 (GB2312-80)、x-cp20949: 韓国語 Wansung、cp1025:IBM EBCDIC (キリル セルビア語 ブルガリア語)、koi8-u: キリル語 (KOI8-U)、iso- 8859-1: 西ヨーロッパ (ISO)、iso-8859-2: 中央ヨーロッパ (ISO)、iso-8859-3: ラテン3 (ISO)、iso-8859-4: バルト海 (ISO)、iso-8859-5: キリル (ISO)、iso-8859-6: アラビア語 (ISO)、iso-8859-7: ギリシャ語 (ISO)、iso-8859-8: ヘブライ語 (ISO-Visual)、iso-8859-9: トルコ語 (ISO)、iso-8859-13: エストニア語 (ISO)、iso-8859-15: ラテン語 9 (ISO)、x-Europa:Europa、iso-8859-8-i: ヘブライ語 (ISO-Logical)、iso-2022- jp: 日本語 (JIS)、csISO2022JP: 日本語 (JIS-1バイトカナを許可)、iso-2022-jp: 日本語 (JIS-1バイトカナを許可-SO / SI)、iso-2022-kr: 韓国語 (ISO)、x-cp50227: 簡体字中国語 (ISO-2022)、euc-jp: 日本語 (EUC)、EUC-CN: 簡体字中国語 (EUC)、euc-kr: 韓国 (EUC)、hz-gb-2312: 簡体字中国語 (HZ)、GB18030: 簡体字中国語 (GB18030)、x-iscii-de:ISCII デーヴァナーガリー、x-iscii-be:ISCII ベンガル語、x-iscii-ta:ISCII タミール語、x-iscii-te:ISCII テルグ語、x-iscii-as:ISCII アッサム語、x-iscii-または : ISCII オリヤー語、x-iscii-ka:ISCII カンナダ語、x-iscii-ma:ISCII マラヤーラム語、x-iscii -gu:ISCII グジャラート語、x-iscii-pa:ISCII パンジャブ語、utf-7:Unicode (UTF-7)、utf-8:Unicode (UTF-8)|自動検出|Web サービスの応答に使用するエンコード。 自動検出オプションが選択された場合、使用されるエンコードは Web サービスで指定されます|
|信頼されていない証明書を受け入れます|N/A|ブール値|無効|信頼されていない証明書を受け入れるかどうかを指定します|
|HTTP 認証|N/A|ブール値|無効|web サーバーが認証を必要とするかどうかを指定します。 このプロパティは HTTP 認証を参照します (ブラウザーがポップアップ ウィンドウを表示してユーザー名とパスワードを要求する場合)|
|ユーザー名|無効|テキスト値||Web サーバーのユーザー名です|
|パスワード|無効|暗号化された値||Web サーバーのパスワードです|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|WebServiceResponseHeaders|テキスト値の一覧|応答の HTTP ヘッダーです|
|DownloadedFile|ファイル|ダウンロードされたファイルです|
|WebServiceResponse|テキスト値|Web サービスの応答テキストです|
|StatusCode|数値|返された状態コードです|


##### <a name="exceptions"></a><a name="invokewebservicebase_onerror"></a> 例外
|例外|内容|
|-----|-----|
|Web サービスの呼び出しエラーです|Web サービスの呼び出しで問題が発生したことを示します|
|ディレクトリが存在しません|必要なディレクトリが存在しないことを示します|
|カスタム ヘッダーに無効なヘッダーがあります|一部のカスタム ヘッダーが無効であることを示します|


