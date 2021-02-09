---
title: データ型のプロパティ | Microsoft Docs
description: データ型のプロパティ
author: georgiostrantzas
ms.service: flow
ms.topic: article
ms.date: 09/22/2020
ms.author: getrantz
ms.reviewer: ''
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 256803aeacbdce6af9f1988e13ed6b0418baad6f
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711660"
---
# <a name="variables-datatype-properties"></a>変数のデータ型のプロパティ



一部の組み込みデータ型には、変数に格納されている値に関連付けられたプロパティがあります。 

プロパティは、日付の曜日など、変数に格納されている情報の一部や、リストのサイズのように変数を記述する追加属性を含んでる場合があります。

これらのプロパティの値には、次の表記法を使用して直接アクセスできます: **%VariableName.PropertyName%**。

たとえば、**ファイル** というファイルのリストがある場合、次の式を使用して、保存されているファイルの数を取得できます: **%Files.Count%**

![ファイルデータ型の Count 変数プロパティです。](media\datatype-properties\files-count.png)

プロパティを持つデータ型は、以下のリストで表示されます。

## <a name="texts"></a>テキスト

|プロパティ  |内容                                                                             |
|----------|----------------------------------------------------------------------------------------|
|長さ    |保存されたテキストの長さ (文字数) です。                                            |
|isEmpty   |このプロパティは、変数が空の場合は真、一部の文字が含まれている場合は偽です。 |
|ToUpper   |大文字で記述された変数のテキストです。                              |
|ToLower   |小文字で記述された変数のテキストです。                              |
|トリミング   |開始点と終点に白抜きで書かれた変数のテキストです。   |

## <a name="dates"></a>日付

|プロパティ  |内容                                               |
|----------|----------------------------------------------------------|
|年      |datetime 値の年の部分です。                      |
|月     |datetime 値の月の部分です。                     |
|曜日       |datetime 値の日の部分です。                       |
|DayOfWeek |日の名前です (日曜、月曜など)。                |
|DayOfYear |datetime 値の年の日の部分です (1-365/6)。 |
|時間      |datetime 値の時の部分です。                      |
|分    |datetime 値の分の部分です。                    |
|秒    |datetime 値の秒の部分です。                   |

## <a name="lists"></a>リスト

|プロパティ  |内容                              |
|----------|-----------------------------------------|
|カウント     |リストに格納されている項目の数です。|

## <a name="files"></a>ファイル

| プロパティ            |内容                                                                  |
|---------------------|-----------------------------------------------------------------------------|
|Fullname             |ファイルのフルパスです。                                                   |
|RootPath             |ファイルのルート パスです: 例 **C:\\**。                             |
|ディレクトリ            |ファイルが格納されているディレクトリです。                                      |
|件名                 |拡張子を含むファイル名です。                               |
|NameWithoutExtension |拡張子のないファイル名です。                                  |
|拡張            |ファイルの拡張子です。                                                   |
|サイズ                 |ファイルのサイズをバイト単位で指定します。                                               |
|CreationTime         |ファイルが作成された日付です。                                          |
|LastAccessed         |ファイルに最後にアクセスした日付です。                                    |
|LastModified         |ファイルを最後に修正した日付です。                                    |
|非表示             |このプロパティは、ファイルが非表示の場合は真、ファイルが表示されている場合は偽です。 |
|IsSystem             |このプロパティは、ファイルがシステム ファイルの場合真、そうでない場合は偽です。     |
|IsReadOnly           |このプロパティは、ファイルが読み取り専用の場合は真、そうでない場合は偽となります。         |
|IsArchive            |このプロパティは、ファイルがアーカイブの場合は真、そうでない場合は偽となります。        |
|存在する               |このプロパティは、ファイルが存在する場合は真、ファイルが存在しない場合は偽となります。 |
|isEmpty              |このプロパティは、ファイルが空の場合は真、ファイルが空でない場合は偽となります。 |

## <a name="folders"></a>フォルダー

|プロパティ     |内容                                                                      |
|-------------|---------------------------------------------------------------------------------|
|Fullname     |フォルダーのフルパスです。                                                     |
|RootPath     |フォルダーのルート パスです: 例 **C:\\**。                              | 
|上位       |フォルダの親ディレクトリです。                                              |
|件名         |フォルダーの名前。                                                          |
|CreationTime |フォルダーが作成された日付です。                                            |
|LastModified |フォルダーを最後に修正した日付です。                                      |
|非表示     |このプロパティは、フォルダーが非表示の場合は真、フォルダーが表示されている場合は偽です。 |
|存在する       |このプロパティは、フォルダーが存在する場合は真、フォルダーが存在しない場合は偽となります。 |
|isEmpty      |このプロパティは、フォルダーが空の場合は真、フォルダーが空でない場合は偽となります。 |
|FilesCount   |フォルダー内のファイル数です。                                               |
|FoldersCount |フォルダー内のフォルダの数です。                                             |

## <a name="mail-messages"></a>メール メッセージ

|プロパティ    |内容                                                                                                |
|------------|-----------------------------------------------------------------------------------------------------------|
|MailFolder  |メールメッセージが取得される名前のフォルダーです。                                                       |
|Uid         |メッセージの一意識別子。                                                                      | 
|From        |メールメッセージの送信者です。                                                                           |
|To          |メッセージの受信者を含む値のリストです。                                                 |
|CC          |メッセージの追加受信者を含む値のリストです (カーボン コピー)。                           |
|日        |メッセージが送信された日時です。                                                           |
|名前     |メッセージの件名です。                                                                                |
|本体        |メッセージの本文です。 本文はプレーンテキストまたは HTML 形式にすることができます。                                    |
|BodyText    |前のプロパティに HTML が含まれている場合、このプロパティにはプレーンテキスト形式のメッセージ本文が含まれます。 |
|Attachments |メール メッセージの保存された添付ファイルを表すファイルのリストです (存在する場合)。                        |

## <a name="exchange-connection"></a>Exchange 接続

|プロパティ                |内容                         |
|------------------------|------------------------------------|
|ServerAddress           |Exchange サーバー のアドレスです。 |

## <a name="exchange-mail-messages"></a>Exchange メール メッセージ

|プロパティ    |内容                                                                                                |
|------------|-----------------------------------------------------------------------------------------------------------|
|MailFolder  |メールメッセージが取得される名前のフォルダーです。                                                       |
|ItemId      |メッセージの一意識別子。                                                                      | 
|From        |メールメッセージの送信者です。                                                                           |
|To          |メッセージの受信者を含む値のリストです。                                                 |
|CC          |メッセージの追加受信者を含む値のリストです (カーボン コピー)。                           |
|日        |メッセージが送信された日時です。                                                           |
|名前     |メッセージの件名です。                                                                                |
|本体        |メッセージの本文です。 本文はプレーンテキストまたは HTML 形式にすることができます。                                    |
|BodyText    |前のプロパティに HTML が含まれている場合、このプロパティにはプレーンテキスト形式のメッセージ本文が含まれます。 |
|Attachments |メール メッセージの保存された添付ファイルを表すファイルのリストです (存在する場合)。                        |

## <a name="outlook-mail-messages"></a>Outlook メール メッセージ

|プロパティ    |内容                                                                                                |
|------------|-----------------------------------------------------------------------------------------------------------|
|MailFolder  |メールメッセージが取得される名前のフォルダーです。                                                       |
|EntryId     |メッセージの一意識別子。                                                                      | 
|From        |メールメッセージの送信者です。                                                                           |
|To          |メッセージの受信者を含む値のリストです。                                                 |
|CC          |メッセージの追加受信者を含む値のリストです (カーボン コピー)。                           |
|Bcc         |メッセージの追加受信者を含む値のリストです (ブラインド カーボン コピー)。     
|日        |メッセージが送信された日時です。                                                           |
|名前     |メッセージの件名です。                                                                                |
|本体        |メッセージの本文です。 本文はプレーンテキストまたは HTML 形式にすることができます。                                    |
|BodyText    |前のプロパティに HTML が含まれている場合、このプロパティにはプレーンテキスト形式のメッセージ本文が含まれます。 |
|Attachments |メール メッセージの保存された添付ファイルを表すファイルのリストです (存在する場合)。                        |

## <a name="ftp-files"></a>FTP ファイル

|プロパティ             |内容                                               |
|---------------------|----------------------------------------------------------|
|Fullname             |ファイルのフルパスです。                                |
|ディレクトリ            |FTP サーバー上のファイルが保存されているディレクトリです。 | 
|件名                 |拡張子を含むファイル名です。            |
|NameWithoutExtension |拡張子のないファイル名です。       |
|拡張            |ファイルの拡張子です。                                |
|サイズ                 |ファイルのサイズをバイト単位で指定します。                            |
|LastModified         |ファイルを最後に修正した日付です。                 |

## <a name="ftp-folders"></a>FTP フォルダー

|プロパティ     |内容                                 |
|-------------|--------------------------------------------|
|Fullname     |フォルダーのフルパスです。                |
|上位       |フォルダの親ディレクトリです。         | 
|件名         |フォルダーの名前。                     |
|LastModified |フォルダーを最後に修正した日付です。 |

## <a name="ftp-connection"></a>FTP 接続

|プロパティ         |内容                                   |
|-----------------|----------------------------------------------|
|ホスト             |FTP 接続のホストの種類です。               |
|SecurityProtocol |接続で使用されるセキュリティ プロトコルです。 |

## <a name="datatables"></a>データ テーブル

|プロパティ  |内容                                                                           |
|----------|--------------------------------------------------------------------------------------|
|RowsCount |データ テーブルの行数です。                                                 |
|列   |データ テーブルの列の名前を含むリストです。                      | 
|IsEmpty   |このプロパティは、データ テーブルが空の場合は真、要素が含まれている場合は偽です。 | 

## <a name="datarows"></a>Datarows

|プロパティ     |内容                                                      |
|-------------|-----------------------------------------------------------------|
|ColumnsCount |データ行が保持する列の数です。                   |
|ColumnsNames |データ行のヘッダーを含むリストです。                 |

## <a name="web-browser-instance"></a>Web ブラウザー インスタンス

|プロパティ                |内容                                                                |
|------------------------|---------------------------------------------------------------------------|
|DisplayRectangleX       |X 軸内のウィンドウの左上隅の位置を表わします。           |
|DisplayRectangleY       |Y 軸内のウィンドウの左上隅の位置を表わします。           |
|Handle                  |ブラウザ インスタンスのハンドルです。                                        |
|HtmlDialogs             |現在のページのダイアログが存在する場合は、それが含まれます。                   |
|IsAlive                 |このプロパティは、ブラウザウィンドウがアクティブな場合は真、非アクティブな場合は偽となります。 | 

## <a name="window-instance"></a>ウィンドウ インスタンス

|プロパティ                |内容                                                                |
|------------------------|---------------------------------------------------------------------------|
|Handle                  |ウィンドウ インスタンスのハンドルです。                                         |

## <a name="excel-instance"></a>Excel インスタンス

|プロパティ                |内容                                                                |
|------------------------|---------------------------------------------------------------------------|
|Handle                  |Excel インスタンスのハンドルです。                                          |

## <a name="sql-connection"></a>SQL 接続

|プロパティ                |内容                                                                   |
|------------------------|------------------------------------------------------------------------------|
|ConnectionString        |データベース接続に使用される接続文字列です。                       |
|IsClosed                |このプロパティは、ブラウザ ウィンドウが閉じている場合は真、開いている場合は偽となります。 |

## <a name="cmd-session"></a>CMD セッション

|プロパティ   |内容                                                                   |
|-----------|------------------------------------------------------------------------------|
|IsAlive    |このプロパティは、CMD セッションがアクティブな場合は真、非アクティブな場合は偽となります。       |
|ProcessId  |プロセスの一意の識別子です。                                         |

## <a name="terminal-session"></a>ターミナル セッション

|プロパティ     |内容                                                                       |
|-------------|----------------------------------------------------------------------------------|
|IsTerminated |このプロパティは、ターミナル セッションが終了している場合は真、終了していない場合は偽となります。 |

## <a name="xml-node"></a>XML ノード

|プロパティ   |内容                          |
|-----------|-------------------------------------|
|子   |XML ノードの子です。        |
|InnerText  |XML ノードの内部テキストです。      |
|InnerXML   |XML ノードの内部 XML です。 |
|件名       |XML ドキュメントの名前です。        |
|OuterXML   |XML ノードの外部 XML です。       |
|上位     |XML ノードの親です。          |
|値      |XML ノードの値です。           |


## <a name="active-directory-entry"></a>Active Directory エントリ

|プロパティ   |内容                                       |
|-----------|--------------------------------------------------|
|LdapPath   |Active Directory 接続の LDAP パスです。 |

## <a name="group-info"></a>グループ情報

|プロパティ    |内容                                 |
|------------|--------------------------------------------|
|内容 |グループの説明です。               |
|表示名 |グループの表示名。              |
|メンバー     |グループのメンバーを含むリストです。 |
|件名        |グループの名前。                      |

## <a name="user-info"></a>ユーザー情報

|プロパティ        |内容                   |
|----------------|------------------------------|
|市            |ユーザーの市区町村です。         |
|会社         |ユーザーの会社です。      |
|国         |ユーザーの国です。      |
|部署      |ユーザーの部署です。   |
|電子メール           |ユーザーのメールです。        |
|拡張       |ユーザーの内線番号です。    |
|FirstName       |ユーザーの名です。   |
|イニシャル        |ユーザーのイニシャルです。     |
|LastName        |ユーザーの姓です。    |
|PostalCode      |ユーザーの郵便番号です。  |
|完了状態           |ユーザーの都道府県です。        |
|StreetAddress   |ユーザーの住所です。      |
|TelephoneNumber |ユーザーの電話番号です。 |
|敬称           |ユーザーの役職です。        |

## <a name="ebs-snapshot"></a>EBS スナップショット

|プロパティ            |内容                                                                                     |
|--------------------|------------------------------------------------------------------------------------------------|
|DataEncryptionKeyId |データ暗号化キーの ID です。                                                              |
|内容         |スナップショットの説明です。                                                                |
|暗号化           |スナップショットが暗号化されている場合、このプロパティは真です。                                             |
|KmsKeyId            |暗号化に使用する AWS鍵管理サービスの顧客マスター キーの識別子です。 |
|OwnerAlias          |所有者の別名です。                                                                         |
|所有者 ID             |所有者の ID です。                                                                            |
|進捗状況            |スナップショットの進捗です。                                                                   |
|SnapshotId          |スナップショットの ID です。                                                                         |
|StartTime           |スナップショットの開始時間です。                                                                 |
|完了状態               |スナップショットの状態です。                                                                      |
|StateMessage        |スナップショットの状態メッセージです。                                                              |
|タグ                |スナップショットのタグです。                                                                       |
|VolumeId            |ボリューム ID です。                                                                                  |
|VolumeSize          |ボリュームのサイズです。                                                                         |

## <a name="ebs-volume"></a>EBS ボリューム

|プロパティ            |内容                                                                                     |
|--------------------|------------------------------------------------------------------------------------------------|
|Attachments         |巻の添付ファイルです。                                                                  |
|AvailabilityZone    |ボリュームの可用性ゾーンです。                                                            |
|CreateTime          |このボリュームの作成時間です。                                                               |
|暗号化           |ボリュームが暗号化されている場合、このプロパティは真です。                                               |
|FastRestored        |このプロパティは、高速リストアが有効な場合に真 になります。                                           |
|Iops                |ボリュームの最大 IOPS です。                                                                     |
|KmsKeyId            |暗号化に使用する AWS鍵管理サービスの顧客マスター キーの識別子です。 |
|MultiAttachEnabled  |このプロパティは、複数添付が有効な場合に真 になります。                                           |
|OutpostArn          |Outpost の Amazon Resource Name (ARN) です。                                                  |
|サイズ                |ボリュームのサイズです。                                                                         |
|SnapshotId          |スナップショットの ID です。                                                                         |
|完了状態               |ボリュームの状態です。                                                                        |
|タグ                |ボリュームのタグです。                                                                         |
|VolumeId            |ボリュームの ID です。                                                                           |
|VolumeType          |ボリュームの種類。                                                                         |

## <a name="azure-managed-disk"></a>Azure マネージド ディスク

|プロパティ                   |内容                                                         |
|---------------------------|--------------------------------------------------------------------|
|AvailabilityZones          |ディスクの可用性ゾーンです。                                 |
|構成              |ディスクの構成です。                                      |
|暗号化                  |ディスクが暗号化されている場合、このプロパティは真となります。                     |
|IopsSLimit                 |ディスクの最大 IOPS です。                                           |
|IsAttachedToVirtualMachine |このプロパティは、ディスクが仮想マシンに接続されている場合に真となります。 |
|OperationSystem            |ディスクにインストールされているオペレーティングシステムです。                         |
|SizeInGB                   |ディスクのサイズ (GB) です。                                         |
|完了状態                      |このディスクの状態です。                                             |
|ThroughputLimit            |ディスクのスループット制限です。                                   |
|TimeCreated                |ディスクの作成時間です。                                      |
|型                       |ディスクの種類です。                                               |
|VirtualMachine             |ディスクがアタッチされている仮想マシンです。                   |
|リソース グループ              |ディスクのリソース グループです。                                     |
|ID                         |ディスクの ID です。                                                 |
|場所                   |ディスクの場所です。                                           |
|件名                       |ディスクの名前です。                                             |
|SubscriptionId             |ディスクのサブスクリプション ID です。                                    |
|タグ                       |ディスクのタグです。                                               |

## <a name="azure-resource-group"></a>Azure リソース グループ

|プロパティ          |内容                                   |
|------------------|----------------------------------------------|
|ProvisioningState |リソース グループのプロビジョニングの状態です。 |
|ID                |リソース グループの ID です。                 |
|場所          |リソース グループの場所です。          |
|件名              |リソース グループの名前。               |
|SubscriptionId    |リソース グループのサブスクリプション ID です。    |
|タグ              |リソース グループのタグです。               |

## <a name="azure-snapshot"></a>Azure スナップショット

|プロパティ            |内容                                |
|-------------------|--------------------------------------------|
|CreationSourceId   |スナップショットの作成ソース ID です。     |
|CreationSourceType |スナップショットの作成ソースの種類です。   |
|OperationSystem    |スナップショット上のこのオペレーティング システムです。 |
|SizeInGB           |スナップショットのサイズ (GB) です。             |
|StorageAccountType |スナップショットこのストレージ アカウント タイプです。  |
|TimeCreated        |スナップショットの作成時間です。          |
|リソース グループ      |スナップショットのリソース グループです。         |
|ID                 |スナップショットのこの ID です。                    |
|場所           |スナップショットの場所です。               |
|件名               |スナップショットの名前です。                   |
|SubscriptionId     |スナップショットのサブスクリプション ID です。        |
|タグ               |スナップショットのタグです。                   |

