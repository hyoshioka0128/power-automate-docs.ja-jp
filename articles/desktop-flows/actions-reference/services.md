---
title: サービス | Microsoft Docs
description: サービスを使用したアクションについての参考情報
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
ms.openlocfilehash: 599d287bca6c63d9daea895d9f60bae71f6d430b
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711617"
---
# <a name="services"></a>サービス 



ワークステーションにインストールされているサービスを制御します

|<!-- --> |
|-----|
|[サービスを開始](#start)|
|[サービスを停止](#stop)|
|[サービスを一時停止](#pause)|
|[サービスを再開](#resume)|

### <a name="start-service"></a><a name="start"></a> サービスを開始する
停止している Windows サービスを開始します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|開始するサービス|無効|テキスト値||開始するサービスの名前|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="start_onerror"></a> 例外
|例外|内容|
|-----|-----|
|サービスが見つかりません|サービスが見つからないことを示します|
|サービスが既に実行されています|サービスが既に実行されていることを示します|
|サービスを開始できません|サービスの開始に問題があることを示します|

### <a name="stop-service"></a><a name="stop"></a> サービスを停止する
実行中の Windows サービスを停止します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|停止するサービス|無効|テキスト値||停止するサービスの名前|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="stop_onerror"></a> 例外
|例外|内容|
|-----|-----|
|サービスが見つかりません|サービスが見つからないことを示します|
|サービスが実行されていません|サービスが実行されていないことを示します|
|サービスを停止できません|サービスの停止に問題があることを示します|

### <a name="pause-service"></a><a name="pause"></a> サービス を一時停止する
実行中の Windows サービスを一時停止します

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|一時停止するサービス|無効|テキスト値||一時停止するサービスの名前|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="pause_onerror"></a> 例外
|例外|内容|
|-----|-----|
|サービスが見つかりません|サービスが見つからないことを示します|
|サービスが実行されていません|サービスが実行されていないことを示します|
|サービスを一時停止できません|サービスの一時停止に問題があることを示します|

### <a name="resume-service"></a><a name="resume"></a> サービスを再開する
一時停止した Windows サービスを再開

##### <a name="input-parameters"></a>入力パラメーター
|引数|省略可能|承認|既定|内容|
|-----|-----|-----|-----|-----|
|再開するサービス|無効|テキスト値||再開するサービスの名前|


##### <a name="variables-produced"></a>生成された変数
- このアクションは変数を生成しません

##### <a name="exceptions"></a><a name="resume_onerror"></a> 例外
|例外|内容|
|-----|-----|
|サービスが見つかりません|サービスが見つからないことを示します|
|サービスが実行されていません|サービスが実行されていないことを示します|
|サービスを再開できません|サービスの再開に問題があることを示します|


