---
title: Active Directory | Microsoft Docs
description: Active Directory のアクションについての参考情報
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
ms.openlocfilehash: 8d0310313c3dd77da96ca47ba345f121d8e50a57
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711637"
---
# <a name="active-directory"></a>Active Directory



Active Directory サーバーに接続して操作を実行します

|<!-- --> |
|-----|
|[グループの作成](#creategroup)|
|[グループ情報の取得](#getgroupinfo)|
|[グループのメンバーを取得](#getgroupmembers)|
|[グループの変更](#modifygroupaction)|
|[オブジェクトの作成](#createobject)|
|[オブジェクトを削除](#deleteobject)|
|[オブジェクトを移動](#moveobject)|
|[オブジェクトを名前変更](#renameobject)|
|[ユーザーの作成](#createuser)|
|[ユーザー情報を取得](#getuserinfo)|
|[ユーザーを変更](#modifyuseraction)|
|[ユーザーをロック解除](#unlockuser)|
|[ユーザー情報を更新](#updateuserinfo)|
|[サーバーに接続](#connecttoserveraction)|
|[接続を閉じる](#closeconnection)|

## <a name="group"></a>グループ
Active Directory サーバー内のグループに関する情報を作成、変更、取得します
### <a name="create-group"></a><a name="creategroup"></a> グループの作成
Active Directory 内にグループを作成します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|親ディレクトリ エントリ|無効|Active Directory エントリ||Active Directory サーバーの親エントリ|
|グループ名|無効|テキスト値||新たに作成されるグループの名前|
|場所|有効|テキスト値||グループが作成される場所|
|内容|有効|テキスト値||グループの説明|
|グループ スコープ|N/A|ローカル、グローバル、ユニバーサル|グローバル|Active Directory 内のグループのスコープ|
|グループの種類|N/A|セキュリティ、配送|セキュリティ|グループの種類|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="creategroup_onerror"></a> 例外
|例外|内容|
|-----|-----|
|認証エラー|ユーザーの認証に関するエラーを示します|
|無効な操作|無効な操作エラーを示します|
|サーバーが動作していません|Active Directory サーバーが動作していないことを示します|
|許可されていないアクセス|認証エラーが発生したことを示します|
|Active Directory エントリが見つかりません|指定された Active Directory エントリが Active Directory サーバー上で見つからないことを示します|
|オブジェクトが既に存在する|指定した名前のオブジェクトが Active Directory に既に存在していることを示します|
|Active Directory エラー|一般 Active Directory エラー|

### <a name="get-group-info"></a><a name="getgroupinfo"></a> グループ情報の取得
Active Directory サーバーからグループに関する情報を取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|親ディレクトリ エントリ|無効|Active Directory エントリ||Active Directory サーバーの親エントリ|
|識別名|無効|テキスト値||Active Directory エントリの識別名|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|GroupInfo|グループ情報|グループの情報|


##### <a name="exceptions"></a><a name="getgroupinfo_onerror"></a> 例外
|例外|内容|
|-----|-----|
|認証エラー|ユーザーの認証に関するエラーを示します|
|無効な操作|無効な操作エラーを示します|
|サーバーが動作していません|Active Directory サーバーが動作していないことを示します|
|許可されていないアクセス|認証エラーが発生したことを示します|
|Active Directory エントリが見つかりません|指定された Active Directory エントリが Active Directory サーバー上で見つからないことを示します|
|オブジェクトがサーバーに存在しません|オブジェクトが Active Directory サーバーに存在しないことを示します|
|Active Directory エラー|一般 Active Directory エラー|

### <a name="get-group-members"></a><a name="getgroupmembers"></a> グループメンバーの取得
Active Directory 内のグループのメンバーを取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|親ディレクトリ エントリ|無効|Active Directory エントリ||Active Directory サーバーの親エントリ|
|識別名|無効|テキスト値||Active Directory エントリの識別名|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|GroupMembers|グループのメンバーのリスト|グループのメンバーを保持する変数|


##### <a name="exceptions"></a><a name="getgroupmembers_onerror"></a> 例外
|例外|内容|
|-----|-----|
|認証エラー|ユーザーの認証に関するエラーを示します|
|無効な操作|無効な操作エラーを示します|
|サーバーが動作していません|Active Directory サーバーが動作していないことを示します|
|許可されていないアクセス|認証エラーが発生したことを示します|
|Active Directory エントリが見つかりません|指定された Active Directory エントリが Active Directory サーバー上で見つからないことを示します|
|オブジェクトがサーバーに存在しません|オブジェクトが Active Directory サーバーに存在しないことを示します|
|Active Directory エラー|一般 Active Directory エラー|

### <a name="modify-group"></a><a name="modifygroupaction"></a>グループの修正
Active Directory 内のグループを変更します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|親ディレクトリ エントリ|無効|Active Directory エントリ||Active Directory サーバーの親エントリ|
|識別名|無効|テキスト値||Active Directory エントリの識別名|
|操作|N/A|グループの名前変更、グループの削除、ユーザーの追加、ユーザーの削除|グループの名前変更|実行する操作を選択|
|新しい名前|無効|テキスト値||グループの新しい名前|
|ユーザー識別名|無効|テキスト値||ユーザーの識別名を指定|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="modifygroupaction_onerror"></a> 例外
|例外|内容|
|-----|-----|
|認証エラー|ユーザーの認証に関するエラーを示します|
|無効な操作|無効な操作エラーを示します|
|サーバーが動作していません|Active Directory サーバーが動作していないことを示します|
|許可されていないアクセス|認証エラーが発生したことを示します|
|Active Directory エントリが見つかりません|指定された Active Directory エントリが Active Directory サーバー上で見つからないことを示します|
|オブジェクトがサーバーに存在しません|オブジェクトが Active Directory サーバーに存在しないことを示します|
|オブジェクトが既に存在する|指定した名前のオブジェクトが Active Directory に既に存在していることを示します|
|Active Directory エラー|一般 Active Directory エラー|

## <a name="object"></a>オブジェクト
Active Directory サーバーでオブジェクトを作成または操作します
### <a name="create-object"></a><a name="createobject"></a> オブジェクトの作成
Active Directory 内にオブジェクトを作成します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|親ディレクトリ エントリ|無効|Active Directory エントリ||Active Directory サーバーの親エントリ|
|場所|有効|テキスト値||グループが作成される場所|
|オブジェクトの種類|N/A|コンピューター、組織単位|コンピューター|オブジェクトの種類|
|オブジェクト名|無効|テキスト値||新たに作成されるオブジェクトの名前|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="createobject_onerror"></a> 例外
|例外|内容|
|-----|-----|
|認証エラー|ユーザーの認証に関するエラーを示します|
|無効な操作|無効な操作エラーを示します|
|サーバーが動作していません|Active Directory サーバーが動作していないことを示します|
|許可されていないアクセス|認証エラーが発生したことを示します|
|Active Directory エントリが見つかりません|指定された Active Directory エントリが Active Directory サーバー上で見つからないことを示します|
|オブジェクトが既に存在する|指定した名前のオブジェクトが Active Directory に既に存在していることを示します|
|無効な属性構文|指定された属性が無効であることを示します|
|Active Directory エラー|一般 Active Directory エラー|

### <a name="delete-object"></a><a name="deleteobject"></a> オブジェクトの作成
Active Directory 内のオブジェクトを削除します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|親ディレクトリ エントリ|無効|Active Directory エントリ||Active Directory サーバーの親エントリ|
|識別名|無効|テキスト値||Active Directory エントリの識別名|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="deleteobject_onerror"></a> 例外
|例外|内容|
|-----|-----|
|認証エラー|ユーザーの認証に関するエラーを示します|
|無効な操作|無効な操作エラーを示します|
|サーバーが動作していません|Active Directory サーバーが動作していないことを示します|
|許可されていないアクセス|認証エラーが発生したことを示します|
|Active Directory エントリが見つかりません|指定された Active Directory エントリが Active Directory サーバー上で見つからないことを示します|
|オブジェクトがサーバーに存在しません|オブジェクトが Active Directory サーバーに存在しないことを示します|
|Active Directory エラー|一般 Active Directory エラー|

### <a name="move-object"></a><a name="moveobject"></a> オブジェクトの移動
Active Directory 内のオブジェクトを移動します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|親ディレクトリ エントリ|無効|Active Directory エントリ||Active Directory サーバーの親エントリ|
|識別名|無効|テキスト値||Active Directory エントリの識別名|
|移動先の場所|無効|テキスト値||オブジェクトの移動先となる場所|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="moveobject_onerror"></a> 例外
|例外|内容|
|-----|-----|
|認証エラー|ユーザーの認証に関するエラーを示します|
|無効な操作|無効な操作エラーを示します|
|サーバーが動作していません|Active Directory サーバーが動作していないことを示します|
|許可されていないアクセス|認証エラーが発生したことを示します|
|Active Directory エントリが見つかりません|指定された Active Directory エントリが Active Directory サーバー上で見つからないことを示します|
|オブジェクトがサーバーに存在しません|オブジェクトが Active Directory サーバーに存在しないことを示します|
|Active Directory エラー|一般 Active Directory エラー|
|場所は空にできません|Active Directory オブジェクトの場所が空であることを示します|

### <a name="rename-object"></a><a name="renameobject"></a> オブジェクトの名称変更
Active Directory 内のオブジェクトの名前を変更します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|親ディレクトリ エントリ|無効|Active Directory エントリ||Active Directory サーバーの親エントリ|
|識別名|無効|テキスト値||Active Directory エントリの識別名|
|新しい名前|無効|テキスト値||グループの新しい名前を入力します|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="renameobject_onerror"></a> 例外
|例外|内容|
|-----|-----|
|認証エラー|ユーザーの認証に関するエラーを示します|
|無効な操作|無効な操作エラーを示します|
|サーバーが動作していません|Active Directory サーバーが動作していないことを示します|
|許可されていないアクセス|認証エラーが発生したことを示します|
|Active Directory エントリが見つかりません|指定された Active Directory エントリが Active Directory サーバー上で見つからないことを示します|
|オブジェクトがサーバーに存在しません|オブジェクトが Active Directory サーバーに存在しないことを示します|
|オブジェクトが既に存在する|指定した名前のオブジェクトが Active Directory に既に存在していることを示します|
|Active Directory エラー|一般 Active Directory エラー|

## <a name="user"></a>ユーザー 
Active Directory サーバー内のユーザーに関する情報を作成、変更、取得します
### <a name="create-user"></a><a name="createuser"></a> ユーザーの作成
Active Directory 内にユーザーを作成します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|親ディレクトリ エントリ|無効|Active Directory エントリ||Active Directory サーバーの親エントリ|
|場所|有効|テキスト値||グループが作成される場所|
|名|無効|テキスト値||ユーザーの名|
|イニシャル|有効|テキスト値||ユーザーのイニシャル|
|姓|有効|テキスト値||ユーザーの姓|
|ユーザー名|無効|テキスト値||ユーザーのユーザー名|
|パスワード|無効|暗号化された値||ユーザーのパスワード|
|パスワードの有効期限なし|N/A|ブール値|無効|ユーザーのパスワードに有効期限を設定するかどうかを指定します|
|無効にするアカウント|N/A|ブール値|無効|アカウントを無効にするかどうかを指定します|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="createuser_onerror"></a> 例外
|例外|内容|
|-----|-----|
|認証エラー|ユーザーの認証に関するエラーを示します|
|無効な操作|無効な操作エラーを示します|
|サーバーが動作していません|Active Directory サーバーが動作していないことを示します|
|許可されていないアクセス|認証エラーが発生したことを示します|
|Active Directory エントリが見つかりません|指定された Active Directory エントリが Active Directory サーバー上で見つからないことを示します|
|オブジェクトが既に存在する|指定した名前のオブジェクトが Active Directory に既に存在していることを示します|
|パスワードの設定や更新ができませんでした|ユーザーのパスワードの設定または更新時に問題が発生したことを示します|
|Active Directory エラー|一般 Active Directory エラー|

### <a name="get-user-info"></a><a name="getuserinfo"></a> グループ ユーザーの取得
Active Directory 内のユーザー情報を取得します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|親ディレクトリ エントリ|無効|Active Directory エントリ||Active Directory サーバーの親エントリ|
|識別名|無効|テキスト値||Active Directory エントリの識別名|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|ユーザー情報|ユーザー情報|ユーザーの情報|


##### <a name="exceptions"></a><a name="getuserinfo_onerror"></a> 例外
|例外|内容|
|-----|-----|
|認証エラー|ユーザーの認証に関するエラーを示します|
|無効な操作|無効な操作エラーを示します|
|サーバーが動作していません|Active Directory サーバーが動作していないことを示します|
|許可されていないアクセス|認証エラーが発生したことを示します|
|Active Directory エントリが見つかりません|指定された Active Directory エントリが Active Directory サーバー上で見つからないことを示します|
|オブジェクトがサーバーに存在しません|オブジェクトが Active Directory サーバーに存在しないことを示します|
|Active Directory エラー|一般 Active Directory エラー|

### <a name="modify-user"></a><a name="modifyuseraction"></a>ユーザーの修正
Active Directory 内のユーザーを変更します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|親ディレクトリ エントリ|無効|Active Directory エントリ||Active Directory サーバーの親エントリ|
|識別名|無効|テキスト値||Active Directory エントリの識別名|
|操作|N/A|ユーザーの有効化/無効化、ユーザー名の変更、ユーザーの削除、パスワードのリセット|ユーザーを有効化/無効化|実行する操作を選択|
|ユーザーを有効化|N/A|ブール値|無効|ユーザーを有効または無効にします|
|新しい名前|無効|テキスト値||グループの新しい名前を入力します|
|新しいパスワード|無効|暗号化された値||グループの新しいパスワードを入力します|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="modifyuseraction_onerror"></a> 例外
|例外|内容|
|-----|-----|
|認証エラー|ユーザーの認証に関するエラーを示します|
|無効な操作|無効な操作エラーを示します|
|サーバーが動作していません|Active Directory サーバーが動作していないことを示します|
|許可されていないアクセス|認証エラーが発生したことを示します|
|Active Directory エントリが見つかりません|指定された Active Directory エントリが Active Directory サーバー上で見つからないことを示します|
|オブジェクトがサーバーに存在しません|オブジェクトが Active Directory サーバーに存在しないことを示します|
|オブジェクトが既に存在する|指定した名前のオブジェクトが Active Directory に既に存在していることを示します|
|無効な属性構文|指定された属性が無効であることを示します|
|Active Directory エラー|一般 Active Directory エラー|
|パスワードの設定や更新ができませんでした|ユーザーのパスワードの設定または更新時に問題が発生したことを示します|

### <a name="unlock-user"></a><a name="unlockuser"></a> ユーザーのロックの解除
Active Directory ユーザーをロック解除します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|親ディレクトリ エントリ|無効|Active Directory エントリ||Active Directory サーバーの親エントリ|
|識別名|無効|テキスト値||Active Directory エントリの識別名|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="unlockuser_onerror"></a> 例外
|例外|内容|
|-----|-----|
|認証エラー|ユーザーの認証に関するエラーを示します|
|無効な操作|無効な操作エラーを示します|
|サーバーが動作していません|Active Directory サーバーが動作していないことを示します|
|許可されていないアクセス|認証エラーが発生したことを示します|
|Active Directory エントリが見つかりません|指定された Active Directory エントリが Active Directory サーバー上で見つからないことを示します|
|オブジェクトがサーバーに存在しません|オブジェクトが Active Directory サーバーに存在しないことを示します|
|Active Directory エラー|一般 Active Directory エラー|

### <a name="update-user-info"></a><a name="updateuserinfo"></a> ユーザー情報の更新
Active Directory 内のユーザー情報を更新します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|親ディレクトリ エントリ|無効|Active Directory エントリ||Active Directory サーバーの親エントリ|
|識別名|無効|テキスト値||Active Directory エントリの識別名|
|表示名です|有効|テキスト値||ユーザーの表示名|
|名|有効|テキスト値||ユーザーの名|
|イニシャル|有効|テキスト値||ユーザーのイニシャル|
|姓|有効|テキスト値||ユーザーの姓|
|敬称|有効|テキスト値||ユーザーの役職|
|ユーザーのメール アドレス|有効|テキスト値||ユーザーのメール アドレス|
|ユーザーの会社|有効|テキスト値||ユーザーの会社|
|電話番号|有効|テキスト値||ユーザーの電話番号|
|拡張|有効|テキスト値||ユーザーの内線番号|
|市|有効|テキスト値||ユーザーの市区町村|
|郵便番号|有効|テキスト値||ユーザーの郵便番号|
|完了状態|有効|テキスト値||ユーザーの都道府県|
|国|N/A|アフガニスタン、オーランド諸島、アルバニア、アルジェリア、アメリカ領サモア、アンドラ、アンゴラ、アングィラ、南極、アンティグア・バーブーダ、アルゼンチン、アルメニア、アルバ、オーストラリア、オーストリア、アゼルバイジャン、バハマ、バーレーン、バングラデシュ、バルバドス、ベラルーシ、ベルギー、ベリーズ、ベナン、バミューダ、ブータン、ボリビア多国籍、ボネール、ボスニア・ヘルツェゴビナ、ボツワナ、ブーベ島、ブラジル、イギリス領インド洋地域の状態、ブルネイ・ダルサラーム、ブルガリア、ブルキナファソ、ブルンジ、カーボベルデ、カンボジア、カメルーン、カナダ、ケイマン諸島、中央アフリカ共和国、チャド、チリ、中国、クリスマス島、ココス諸島、コロンビア、コモロ、コンゴ、コンゴ民主共和国、クック諸島、コスタリカ、コートジボワール、クロアチア、キューバ、キュラソー、キプロス、チェコ共和国、デンマーク、ジブチ、ドミニカ、ドミニカ共和国、エクアドル、エジプト、エルサルバドル、赤道ギニア、エリトリア、エストニア、エチオピア、フォークランド諸島 (マルビナス)、フェロー諸島、フィジー、フィンランド、フランス、フランス領ギアナ、フランス領ポリネシア、フランス南方領土、ガボン、ガンビア、グルジア、ドイツ、ガーナ、ジブラルタル、ギリシャ、グリーンランド、グレナダ、グアドループ、グアム、グアテマラ、ガーンジー、ギニア、ギニアビサウ、ガイアナ、ハイチ、ハード島とマクドナルド諸島、聖地、ホンジュラス、香港特別行政区、ハンガリー、アイスランド、インド、インドネシア、イラン・イスラム共和国、イラク、アイルランド、マン島、イスラエル、イタリア、ジャマイカ、日本、ジャージー、ヨルダン、カザフスタン、ケニア、キリバス、朝鮮民主主義人民共和国、大韓民国、クウェート、キルギス、ラオス人民民主共和国、ラトビア、レバノン、レソト、リベリア、リビア、リヒテンシュタイン リトアニア、ルクセンブルク、マカオ、北マケドニア、マダガスカル、マラウイ、マレーシア、モルディブ、マリ、マルタ、マーシャル諸島、マルティニーク、モーリタニア、モーリシャス、マヨット、メキシコ、ミクロネシア、モルドバ、モナコ、モンゴル、モンテネグロ、モンセラト、モロッコ、モザンビーク、ミャンマー、ナミビア、ナウル、ネパール、オランダ、ニューカレドニア、ニュージーランド、ニカラグア、ニジェール、ナイジェリア、ニウエ、ノーフォーク島、北マリアナ諸島、ノルウェー、オマーン、パキスタン、パラオ、パレスチナ、パナマ、パプアニューギニア、パラグアイ、ペルー、フィリピン、ピトケアン、ポーランド、ポルトガル、プエルトリコ、カタール、レユニオン、ルーマニア、ロシア、ルワンダ、セント・バルテルミー、セント・ヘレナ、セントクリストファー・ネイビス、セントルシア、セント・マーチン (フランス領)、サンピエール・ミクロン、セントビンセント・グレナディーン、サモア、サンマリノ、サントメ・プリンシペ、サウジアラビア、セネガル、セルビア、セーシェル、シエラレオネ、シンガポール、シント・マーチン島 (オランダ領)、スロバキア、スロベニア、ソロモン諸島、ソマリア、南アフリカ、南ジョージアと南サンドイッチ諸島、南スーダン、スペイン、スリランカ、スーダン、スリナム、スバールバルドとヤンマイエン、スワジランド、スウェーデン、スイス、シリア・アラブ共和国、台湾、タジキスタン、タンザニア、タイ、東ティモール、トーゴ、トケラウ、トンガ、トリニダード・トバゴ、チュニジア、トルコ、トルクメニスタン、タークス・カイコス諸島、ツバル、ウガンダ、ウクライナ、アラブ首長国連邦、イギリス、北アイルランド、アメリカ合衆国、合衆国領有小離島、ウルグアイ、ウズベキスタン、バヌアツ、ベネズエラ・ボリバル共和国、ベトナム、英領バージン諸島、米領バージン諸島、ワリス・フツナ、イエメン、ザンビア、ジンバブエ、なし|いいえ​​|ユーザーの国 (2 文字コード) (ISO 3166-1 alpha-2)|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="updateuserinfo_onerror"></a> 例外
|例外|内容|
|-----|-----|
|認証エラー|ユーザーの認証に関するエラーを示します|
|無効な操作|無効な操作エラーを示します|
|サーバーが動作していません|Active Directory サーバーが動作していないことを示します|
|許可されていないアクセス|認証エラーが発生したことを示します|
|Active Directory エントリが見つかりません|指定された Active Directory エントリが Active Directory サーバー上で見つからないことを示します|
|オブジェクトがサーバーに存在しません|オブジェクトが Active Directory サーバーに存在しないことを示します|
|パスワードの設定や更新ができませんでした|ユーザーのパスワードの設定または更新時に問題が発生したことを示します|
|Active Directory エラー|一般 Active Directory エラー|

### <a name="connect-to-server"></a><a name="connecttoserveraction"></a> サーバーに接続する
Active Directory サーバーに接続します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|LDAP パス|無効|テキスト値||Active Directory サーバーの LDAP パス|
|認証を使う|N/A|ブール値|無効|サーバーへの接続に認証が必要かどうかを指定します|
|ユーザー名|無効|テキスト値||ユーザーのユーザー名|
|パスワード|無効|暗号化された値||ユーザーのパスワード|
|認証タイプ|N/A|なし、セキュア、暗号化、Secure sockets layer、読み取り専用サーバー、匿名、ファーストバインド、サイン、シーリング、委任、サーバー バインド|セキュリティ保護|使用する認証の種類を指定|


##### <a name="variables-produced"></a>作成された変数
|引数|型|内容|
|-----|-----|-----|
|ParentDirectoryEntry|Active Directory エントリ|今後の Active Directory アクションで使う Active Directory エントリの親|


##### <a name="exceptions"></a><a name="connecttoserveraction_onerror"></a> 例外
|例外|内容|
|-----|-----|
|認証エラー|ユーザーの認証に関するエラーを示します|
|許可されていないアクセス|認証エラーが発生したことを示します|
|サーバーが動作していません|Active Directory サーバーが動作していないことを示します|
|無効な操作|無効な操作エラーを示します|
|Active Directory エラー|一般 Active Directory エラー|

### <a name="close-connection"></a><a name="closeconnection"></a> 接続を閉じる
Active Directory サーバーとの接続を閉じます

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|親ディレクトリ エントリ|無効|Active Directory エントリ||Active Directory サーバーの親エントリ|


##### <a name="variables-produced"></a>作成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="closeconnection_onerror"></a> 例外
- このアクションには例外は含まれません

