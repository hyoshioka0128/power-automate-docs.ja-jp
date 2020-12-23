---
title: XML | Microsoft Docs
description: XML を使用したアクションについての参考情報
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
ms.openlocfilehash: b8ee36b718c6459dc32a42a0e3d883f3fa4793d7
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711608"
---
# <a name="xml"></a>XML



XML ファイルを管理して操作します

|<!-- --> |
|-----|
|[ファイルから XML を読み取ります](#readfromfile)|
|[XML をファイルに書き込みます](#writexmltofile)|
|[XPath 式を実行します](#executexpathquery)|
|[XML 要素の属性を取得します](#getxmlelementattribute)|
|[XML 要素の属性を設定します](#setelementattribute)|
|[XML 要素の属性を削除します](#removeelementattribute)|
|[XML 要素の値を取得します](#getxmlelementvalue)|
|[XML 要素の値を設定します](#setelementvalue)|
|[XML 要素を挿入します](#insertelement)|
|[XML 要素を削除します](#removeelement)|

### <a name="read-xml-from-file"></a><a name="readfromfile"></a>ファイルから XML を読み取ります
XML ファイルの内容を変数に読み込みます

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ファイル パス:|無効|ファイル||読み取る XML ドキュメントを含むファイル|
|エンコード:|N/A|既定、ANSI、Unicode、Unicode (ビッグエンディアン)、UTF-8|既定|指定されたファイルに使用するエンコード|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|XmlDocument|XML ノード|XML ドキュメントを読み取って保持する変数|


##### <a name="exceptions"></a><a name="readfromfile_onerror"></a> 例外
|例外|内容|
|-----|-----|
|ディレクトリが見つかりません|ディレクトリが存在しないことを示します|
|ファイルが見つかりません|ファイルが存在しないことを示します|
|ファイルを読み取れませんでした|ファイルの読み取りで問題が発生したことを示します|
|ファイルに有効な XML ドキュメントが含まれていません|ファイルに有効な XML ドキュメントが含まれていないことを示します|

### <a name="write-xml-to-file"></a><a name="writexmltofile"></a>XML をファイルに書き込みます
XML ノード変数の内容をファイルに書き込みます

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|ファイル パス:|無効|ファイル||XML ドキュメントを書き込むファイルです|
|書き込む XML:|無効|テキスト値||ファイルに書き込む XML ノードまたはドキュメントです|
|エンコード:|N/A|既定、ANSI、Unicode、Unicode (ビッグエンディアン)、UTF-8|既定|指定されたファイルに使用するエンコード|
|XML を書式設定します:|N/A|ブール値|有効|XML を書式設定するかどうかを指定します|
|各レベルでのインデント数:|有効|数値|2|XML の各レベルでインデントするスペースの数を指定します|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="writexmltofile_onerror"></a> 例外
|例外|内容|
|-----|-----|
|無効なディレクトリが指定されました|指定されたディレクトリが無効であることを示します|
|ファイルに XML を書き込めませんでした|XML をファイルに書き込むときに問題が発生したことを示します|

### <a name="execute-xpath-expression"></a><a name="executexpathquery"></a> XPath 式を実行する
指定された XPath クエリに基づいて、XML ドキュメントから値を抽出します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|解析する XML ドキュメント:|無効|テキスト値||テキストとしての XML、または以前に定義された変数 (解析する XML ドキュメントを含む)|
|XPath クエリ:|無効|テキスト値||XML ドキュメントに対して実行する XPath 式です|
|最初の値のみ取得します:|N/A|ブール値|無効|単一の値 (最初の値のみ) を取得するか、指定された XPath 式に一致するすべての値を取得するかを指定します|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|XPathResult|XML ノード|抽出されたノード (XML ノード)|
|XPathResults|XML ノードの一覧|抽出されたノード (XML ノードの一覧)|


##### <a name="exceptions"></a><a name="executexpathquery_onerror"></a> 例外
|例外|内容|
|-----|-----|
|無効な XML ドキュメントが指定されました|指定された XML ドキュメントが無効であることを示します|
|無効な XPath 式が指定されました|指定された XPath 式が無効であることを示します|

### <a name="get-xml-element-attribute"></a><a name="getxmlelementattribute"></a>XML 要素の属性を取得します
XML 要素の属性値を取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|XML ドキュメント:|無効|XML ノード||属性を取得する XML ドキュメントまたは XML 要素です|
|XPath クエリ|有効|テキスト値||サブ要素を検索してその属性を取得する XPath 式です|
|属性名:|無効|テキスト値||値を取得する属性の名前|
|次として値を取得します:|N/A|テキスト値、数値、Datetime 値、ブール値|テキスト値|属性値のデータの種類を指定します|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|XmlAttributeValue|ブール値|XML 属性の取得された値です|
|XmlAttributeValue|Datetime|XML 属性の取得された値です|
|XmlAttributeValue|数値|XML 属性の取得された値です|
|XmlAttributeValue|テキスト値|XML 属性の取得された値です|


##### <a name="exceptions"></a><a name="getxmlelementattribute_onerror"></a> 例外
|例外|内容|
|-----|-----|
|無効な XPath 式が指定されました|指定された XPath 式が無効であることを示します|
|XPath 式は要素を返しません|XPath 式が要素を返さないことを示します|
|要素に属性が見つかりません|要素に属性が存在しないことを示します|
|属性値を要求されたデータ型に変換できませんでした|属性値を要求されたデータ型に変換するときに問題が発生したことを示します|

### <a name="set-xml-element-attribute"></a><a name="setelementattribute"></a>XML 要素の属性を設定します
XML 要素の属性値を設定します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|XML ドキュメント:|無効|XML ノード||属性を設定する XML ドキュメントまたは XML 要素です|
|XPath クエリ:|有効|テキスト値||サブ要素を検索してその属性を設定する XPath 式です|
|属性名:|無効|テキスト値||値を設定する属性名です|
|属性値:|無効|テキスト値||属性の新しい値です|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="setelementattribute_onerror"></a> 例外
|例外|内容|
|-----|-----|
|無効な XPath 式が指定されました|指定された XPath 式が無効であることを示します|
|XPath 式は要素を返しません|XPath 式が要素を返さないことを示します|
|XML 属性を設定できませんでした|XML 属性の設定中に問題が発生したことを示します|

### <a name="remove-xml-element-attribute"></a><a name="removeelementattribute"></a>XML 要素の属性を削除します
XML 要素から属性を削除します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|XML ドキュメント:|無効|XML ノード||属性を削除する XML ドキュメントまたは XML 要素です|
|XPath クエリ:|有効|テキスト値||サブ要素を検索してその属性を削除する XPath 式です|
|属性名:|無効|テキスト値||削除する属性名です|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="removeelementattribute_onerror"></a> 例外
|例外|内容|
|-----|-----|
|無効な XPath 式が指定されました|指定された XPath 式が無効であることを示します|
|XPath 式は要素を返しません|XPath 式が要素を返さないことを示します|
|要素に属性が見つかりません|要素に属性が存在しないことを示します|
|XML 属性を削除できませんでした|XML 属性の削除中に問題が発生したことを示します|

### <a name="get-xml-element-value"></a><a name="getxmlelementvalue"></a>XML 要素の値を取得します
XML 要素の値を取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|XML ドキュメント:|無効|XML ノード||値を取得する XML ドキュメントまたは XML 要素です|
|XPath クエリ:|有効|テキスト値||サブ要素を検索してその値を取得する XPath 式です|
|次として値を取得します:|N/A|テキスト値、数値、Datetime 値、ブール値|テキスト値|XML 要素の値のデータの種類を指定します|


##### <a name="variables-produced"></a>生成された変数
|引数|型|内容|
|-----|-----|-----|
|XmlElementValue|ブール値|XML 要素の値です|
|XmlElementValue|Datetime|XML 要素の値です|
|XmlElementValue|数値|XML 要素の値です|
|XmlElementValue|テキスト値|XML 要素の値です|


##### <a name="exceptions"></a><a name="getxmlelementvalue_onerror"></a> 例外
|例外|内容|
|-----|-----|
|無効な XPath 式が指定されました|指定された XPath 式が無効であることを示します|
|XPath 式は要素を返しません|XPath 式が要素を返さないことを示します|
|要素の値を要求されたデータ型に変換できませんでした|要素の値を要求されたデータ型に変換するときに問題が発生したことを示します|

### <a name="set-xml-element-value"></a><a name="setelementvalue"></a>XML 要素の値を設定します
XML 要素の値を設定します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|XML ドキュメント:|無効|XML ノード||値を取得する XML ドキュメントまたは XML 要素です|
|XPath クエリ:|有効|テキスト値||サブ要素を検索してその値を取得する XPath 式です|
|XML 要素の値:|無効|テキスト値||XML 要素の新しい値です|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="setelementvalue_onerror"></a> 例外
|例外|内容|
|-----|-----|
|無効な XPath 式が指定されました|指定された XPath 式が無効であることを示します|
|XPath 式は要素を返しません|XPath 式が要素を返さないことを示します|
|要素の値を設定できませんでした|要素の値の設定で問題が発生したことを示します|

### <a name="insert-xml-element"></a><a name="insertelement"></a>XML 要素を挿入します
新しい XML 要素を XML ドキュメントに挿入します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|XML ドキュメント:|無効|XML ノード||新しい XML 要素を挿入する XML ドキュメント|
|XPath クエリ:|無効|テキスト値||親 XML 要素を検索して新しい要素をそこに挿入する、XPath 式です|
|挿入する XML 要素:|無効|XML ノード||XML ドキュメントに挿入する新しい XML 要素|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="insertelement_onerror"></a> 例外
|例外|内容|
|-----|-----|
|無効な XPath 式が指定されました|指定された XPath 式が無効であることを示します|
|XPath 式は要素を返しません|XPath 式が要素を返さないことを示します|
|XML 要素を挿入できませんでした。|XML 要素の挿入で問題が発生したことを示します|

### <a name="remove-xml-element"></a><a name="removeelement"></a>XML 要素を削除します
XML ドキュメントから 1 つまたは複数の XML 要素を削除します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|XML ドキュメント:|無効|XML ノード||削除する XML 要素が含まれている XML ドキュメント|
|XPath クエリ:|無効|テキスト値||削除する要素を検索する XPath 式です|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="removeelement_onerror"></a> 例外
|例外|内容|
|-----|-----|
|無効な XPath 式が指定されました|指定された XPath 式が無効であることを示します|
|XML 要素を削除できませんでした。|XML 要素の削除中に問題が発生したことを示します|


