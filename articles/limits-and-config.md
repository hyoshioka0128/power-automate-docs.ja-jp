---
title: 制限と構成 | Microsoft Docs
description: 制限事項と構成
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/19/2020
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4f1ff6a7171ecb31ef1273fdc7dc273755089d5e
ms.sourcegitcommit: 549224cf13fc761f473c880e8d0d8f2741cc7b0f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "3435066"
---
# <a name="limits-and-configuration-in-power-automate"></a>Power Automate における制限事項と構成

このトピックでは、現時点でのフローに関する制限事項と構成の詳細について説明します。

>[!TIP]
>利用可能なさまざまなプランの詳細については、[価格](https://flow.microsoft.com/pricing) を確認してください。

## <a name="request-limits"></a>要求の制限
1 つの送信要求に対する制限は次のとおりです。

### <a name="timeout"></a>タイムアウト

| 件名 | 制限 |
| --- | --- |
| 同期呼び出しの要求タイムアウト |120 秒 |
| 非同期呼び出しの要求タイムアウト|構成可能。 最大 30 日。 |

### <a name="message-size"></a>メッセージ サイズ

| 件名 | 制限 | メモ​​ |
| --- | --- | --- |
| メッセージ サイズ |100 MB |100 MB を完全にサポートしていない API もあります。 |
| 式の評価の制限 |131,072 文字 |`@concat()`、`@base64()`、`string` は、この制限を超えることはできません。 |

### <a name="retry-policy"></a>再試行ポリシー

| 件名 | 制限 |メモ​​|
| --- | --- | --- |
| 再試行回数 |90 | 既定値は 2 です。 既定値を変更するには、アクションの設定を使用します。 | 
| 再試行の最大遅延 |1 日 |  |
| 再試行の最小遅延 |5 秒 |  |

## <a name="run-duration-and-retention"></a>実行の継続時間とリテンション期間
1 つのフロー実行に対する制限は次のとおりです。

| 件名 | 制限 | メモ​​ |
| --- | --- | --- |
| 実行の継続時間 |30 日 |承認などの保留ステップを含むワークフローが含まれます。 30 日後、すべての保留ステップがタイムアウトになります。 |
| ストレージのリテンション期間 |30 日 |これは、実行の開始時点からです。 |
| 最小繰り返し間隔 |1 分 | |
| 最大繰り返し間隔 |500 日 | |
| 実行履歴の最大リテンション期間 |GDPR の規定に従い 28 日。 | |
|最小延期間隔 - 無料およびプラン 1 ライセンス|5 秒||
|最小延期間隔 - プラン 2 ライセンス|1 秒||

>[!TIP]
>個々のコネクタにも独自の制限がある場合があります。

## <a name="looping-and-debatching-limits"></a>ループおよびバッチ解除の制限
1 つのフロー実行に対する制限は次のとおりです。 日単位の制限については、[要求の制限と割り当て](https://aka.ms/platformlimits) を参照してください。

| 件名 | 制限 | メモ​​ |
| --- | --- | --- |
| 各項目に適用する - Office 365 ライセンスおよび無料ライセンス|5,000 |必要に応じて、フィルター アクションを使って大きい配列をフィルター処理できます。 |
| 各項目に適用 - プラン 1、プラン 2、ユーザーごと、フローごとのライセンス|100,000 |必要に応じて、フィルター アクションを使って大きい配列をフィルター処理できます。 |
| Until 反復 |5,000 | |
| SplitOn 項目 - Office 365 ライセンスおよび無料ライセンス |5,000 ||
| SplitOn 項目 - プラン 1、プラン 2、ユーザーごと、フローごとのライセンス |100,000 ||
| それぞれに適用の並列処理 |50 |既定では、ループは順番に実行されます (基本的に、並列処理は 1 です)。 並列では最大 50 まで構成できます。 |
| 5 分ごとのアクション実行数 – 無料、Office 365、プラン 1 のライセンスと試用版 | 2,000 | 必要に応じて、複数のフローにワークロードを分散することもできます。 |
|5 分ごとのアクション実行数 – 有料プラン 2、ユーザーごと、フローごとのライセンス|100,000|必要に応じて、複数のフローにワークロードを分散することもできます。|
| アクションの同時発信呼び出し – 無料版、Office 365、プラン 1 の各ライセンスと試用版 | ~500 | 必要に応じて、同時要求の数を減らすか、継続時間を短縮します。 |
| アクションの同時発信呼び出し – プラン 2、ユーザーごと、フローごとのライセンス | ~2,500 | 必要に応じて、同時要求の数を減らすか、継続時間を短縮します。 | 

## <a name="throughput-limits"></a>スループットの制限

|件名|制限|メモ​​|
|---|---|---|
|ランタイム エンドポイント - 5 分ごとに許可される読み取り呼び出し回数 – 無料版、Office 365、プラン 1 の各ライセンスと試用版|6,000||
|ランタイム エンドポイント - 5 分ごとに許可される読み取り呼び出し回数 – 有料プラン 2、ユーザーごと、フローごとのライセンス|60,000||
|ランタイム エンドポイント: 5 分ごとの通話呼び出し – 無料版、Office 365、プラン 1 の各ライセンスと試用版|4,500||
|ランタイム エンドポイント: 5 分ごとの Invoke 呼び出し回数 – 有料プラン 2、ユーザーごと、フローごとのライセンス|45,000||
|5 分ごとに許可されるスループットの量 – 無料版、Office 365、プラン 1 の各ライセンスと試用版|600 MB||
|5 分ごとに許可されるスループットの量 – 有料プラン 2、ユーザーごと、フローごとのライセンス|6 GB||
|1 時間ごとの生成が許可されたコンテンツ フローの量 (アクションの入力/出力) - 無料版、Office 365、プラン 1、プラン 2、ユーザーごと、フローごとの各ライセンス|200 GB||


## <a name="definition-limits"></a>定義の制限
1 つのフローに対する制限は次のとおりです。

| 件名 | 制限 | メモ​​ |
| --- | --- | --- |
| ワークフローごとのアクション |500|必要に応じて、入れ子になったワークフローを追加してこの機能を拡張できます。 |
| 許可されるアクションの入れ子の深さ |8 |必要に応じて、入れ子になったワークフローを追加してこの機能を拡張できます。 |
| 式あたりの最大文字 |8,192 | |
| `action`/`trigger` 名の制限 |80 | |
| `description` の長さの制限 |256 | |

## <a name="sharepoint-limits"></a>SharePoint の制限
Microsoft SharePoint で Power Automate と Power Apps の使用をするに当たっては、[制限](https://docs.microsoft.com/connectors/sharepointonline/#limits)があります。

## <a name="ip-address-configuration"></a>IP アドレスの構成
Power Automate  の要求の送信元の IP アドレスは、フローを使用している [環境](environments-overview-admin.md) が置かれている [リージョン](regions-overview.md) によって異なります。 現在、フローのシナリオで使用可能な FQDN は発行されていません。

>[!IMPORTANT]
> フローによる一部の呼び出しは、[ロジック アプリ](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) ドキュメントに記載された IP アドレスから発信される場合があります。 このような呼び出し例としては、HTTP や HTTP + OpenAPI などがあります。

### <a name="logic-apps"></a>Logic Apps
フローからの呼び出しは、Azure Logic App サービスを直接経由します。 このような呼び出し例としては、HTTP や HTTP + OpenAPI などがあります。 そのサービスで使用される IP アドレスについては [Logic Apps ドキュメント](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) を参照してください。

### <a name="connectors"></a>コネクタ
フロー内のコネクタからの呼び出し (たとえば SQL API や SharePoint API) は、以下に示す IP アドレスから送られてきます。

| 地域 | 送信 IP |
| --- | --- |
| アジア太平洋 | 13.75.36.64 - 13.75.36.79、13.67.8.240 - 13.67.8.255、52.175.23.169, 52.187.68.19 |
| オーストラリア  | 13.70.72.192 - 13.70.72.207、13.72.243.10, 13.77.50.240、13.77.50.255, 13.70.136.174 |
| カナダ | 13.71.170.208 - 13.71.170.223、13.71.170.224 - 13.71.170.239、52.237.24.126、40.69.106.240 - 40.69.106.255、52.242.35.152|
| ヨーロッパ | 13.69.227.208 - 13.69.227.223、52.178.150.68、13.69.64.208 - 13.69.64.223、52.174.88.118、137.117.161.181 |
| インド  | 104.211.81.192 - 104.211.81.207、52.172.211.12、40.78.194.240 - 40.78.194.255、13.71.125.22、104.211.146.224 - 104.211.146.239、104.211.189.218 |
| 日本 | 13.78.108.0 - 13.78.108.15、13.71.153.19、40.74.100.224 - 40.74.100.239、104.215.61.248 |
| 南米 | 191.233.203.192 - 191.233.203.207、104.214.19.48 - 104.214.19.63、13.65.86.57、104.41.59.51 |
| アラブ首長国連邦 | 40.120.8.0 - 40.120.8.31、20.37.74.192 - 20.37.74.207、20.45.67.28|
| 英国 | 51.140.148.0 - 51.140.148.15、51.140.80.51、51.140.211.0 - 51.140.211.15、51.141.47.105 |
| 米国 | 13.89.171.80 - 13.89.171.95、52.173.245.164、40.71.11.80 - 40.71.11.95、40.71.249.205、40.70.146.208 - 40.70.146.223、52.232.188.154、52.162.107.160 - 52.162.107.175、52.162.242.161、40.112.243.160 - 40.112.243.175、104.42.122.49|
| プレビュー (米国)  | 13.71.195.32 - 13.71.195.47、52.161.102.22、13.66.140.128 - 13.66.140.143、52.183.78.157 |

たとえば、Azure SQL Database の IP アドレスを承認する場合は、これらのアドレスを使う必要があります。

### <a name="required-services"></a>必要なサービス
次の表に、Power Automate の接続先となるサービスの一覧を示します。 これらのサービスがネットワーク上でブロックされていないことを確認してください。

ドメイン | プロトコル | 使用
--------|  ---------| -----
management.azure.com|https|Azure Resource Manager にアクセスします。
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Active Directory 認証ライブラリ (ADAL) にアクセスします。
graph.microsoft.com </br>graph.windows.net</br>|https|プロファイルの写真などのユーザー情報を取得するために、Azure AD Graph API にアクセスします。
*.azure-apim.net|https|コネクタのランタイムにアクセスします。
*.flow.microsoft.com|https|Power Automate のサイトににアクセスする。
*.powerapps.com|https|Power Apps のサイトににアクセスする。
*.azureedge.net|https|Power Automate CDN にアクセスする。
nps.onyx.azure.net|https|NPS (Net Promoter Score) にアクセスします。
webshell.suite.office.com|https|ヘッダーと検索のための Office にアクセスします。 詳細については、[Office 365 の URL と範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) を参照してください

### <a name="approval-email-delivery"></a>承認メールの送信
承認メールのルーティングに関する詳細については、[承認メールの送信に関する記事](https://go.microsoft.com/fwlink/?linkid=2128304) を参照してください。

### <a name="ui-flows-required-services"></a>UI フローに必要なサービス
次の表に、UI フローのインストールを成功させるためにユーザーのマシンから接続するためのエンドポイント データ要件を示します。

エンドポイントの種類 | ドメイン | プロトコル | 使用
--------| --------|  ---------| -----
世界的なエンドポイント|ocsp.digicert.com<br>ocsp.msocsp.com<br>mscrl.microsoft.com<br>crl3.digicert.com<br>crl4.digicert.com|http|パブリック クラウドの CRL サーバーにアクセスします。
米国政府機関の GCC および GCC High エンドポイント|ocsp.digicert.com<br>crl3.digicert.com<br>crl4.digicert.com|http|米国政府機関クラウドの CRL サーバーにアクセスします。
21Vianet が運用するエンドポイント|crl.digicert.cn<br>ocsp.digicert.cn|http|21Vianet が運用するクラウドの CRL サーバーにアクセスする。
すべてのエンドポイント|msedgedriver.azureedge.net<br>chromedriver.storage.googleapis.com|https|UI Flows WebDriver ダウンローダーにアクセスします。
