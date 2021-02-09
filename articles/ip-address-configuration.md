---
title: IP アドレスの構成 | Microsoft Docs
description: IP アドレスの構成
services: ''
suite: flow
documentationcenter: na
author: masisley
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/29/2020
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2e95f459b3185968640564a5946dcb55f56aebd0
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4708703"
---
# <a name="ip-address-configuration"></a>IP アドレスの構成
Power Automate  の要求の送信元の IP アドレスは、フローを使用している [環境](environments-overview-admin.md) が置かれている [リージョン](regions-overview.md) によって異なります。 現在、フローのシナリオで使用可能な FQDN は発行されていません。

>[!IMPORTANT]
> クラウド フローによる一部の呼び出しは、[ロジック アプリ](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses)に関するドキュメントに記載された IP アドレスから発信される場合があります。 このような呼び出し例としては、HTTP や HTTP + OpenAPI などがあります。

## <a name="logic-apps"></a>Logic Apps
クラウド フローからの呼び出しは、Azure Logic App サービスを直接通過します。 このような呼び出し例としては、HTTP や HTTP + Open API などがあります。 そのサービスで使用される IP アドレスについては [Logic Apps ドキュメント](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) を参照してください。

## <a name="connectors"></a>コネクタ
クラウド フロー内のコネクタからの呼び出し (たとえば SQL API や SharePoint API) は、以下に示す IP アドレスから送られてきます。

| 地域 | 送信 IP |
| --- | --- |
| アジア太平洋 | 13.75.36.64 - 13.75.36.79、13.67.8.240 - 13.67.8.255、52.175.23.169, 52.187.68.19 |
| オーストラリア  | 13.70.72.192 - 13.70.72.207、13.72.243.10, 13.77.50.240、13.77.50.255, 13.70.136.174 |
| カナダ | 13.71.170.208 - 13.71.170.223、13.71.170.224 - 13.71.170.239、52.237.24.126、40.69.106.240 - 40.69.106.255、52.242.35.152 |
| ヨーロッパ | 13.69.227.208 - 13.69.227.223、52.178.150.68、13.69.64.208 - 13.69.64.223、52.174.88.118、137.117.161.181 |
| ドイツ | 51.116.60.192、51.116.158.97、51.116.158.96、51.116.211.212、および 51.116.236.78 |
| インド  | 104.211.81.192 - 104.211.81.207、52.172.211.12、40.78.194.240 - 40.78.194.255、13.71.125.22、104.211.146.224 - 104.211.146.239、104.211.189.218 |
| 日本 | 13.78.108.0 - 13.78.108.15、13.71.153.19、40.74.100.224 - 40.74.100.239、104.215.61.248 |
| 南米 | 191.233.203.192 - 191.233.203.207、104.214.19.48 - 104.214.19.63、13.65.86.57、104.41.59.51 |
| アラブ首長国連邦 | 40.120.8.0 - 40.120.8.31、20.37.74.192 - 20.37.74.207、20.45.67.28 |
| 英国 | 51.140.148.0 - 51.140.148.15、51.140.80.51、51.140.211.0 - 51.140.211.15、51.141.47.105 |
| 米国 | 13.89.171.80 - 13.89.171.95、52.173.245.164、40.71.11.80 - 40.71.11.95、40.71.249.205、40.70.146.208 - 40.70.146.223、52.232.188.154、52.162.107.160 - 52.162.107.175、52.162.242.161、40.112.243.160 - 40.112.243.175、104.42.122.49 |
| プレビュー (米国)  | 13.71.195.32 - 13.71.195.47、52.161.102.22、13.66.140.128 - 13.66.140.143、52.183.78.157 |

たとえば、Azure SQL Database の IP アドレスを承認する場合は、これらのアドレスを使う必要があります。

## <a name="required-services"></a>必要なサービス
次の表に、Power Automate の接続先となるサービスの一覧を示します。 これらのサービスがネットワーク上でブロックされていないことを確認してください。

| ドメイン | プロトコル | 使用 |
| --------|  ---------| ---- |
| management.azure.com | https | Azure Resource Manager にアクセスします。 |
| login.microsoft.com<br />login.windows.net<br />login.microsoftonline.com<br />secure.aadcdn.microsoftonline-p.com | https | Active Directory 認証ライブラリ (ADAL) にアクセスします。 |
| graph.microsoft.com <br />graph.windows.net<br /> | https | プロファイルの写真などのユーザー情報を取得するために、Azure AD Graph API にアクセスします。 |
| *.azure-apim.net | https | コネクタのランタイムにアクセスします。 |
| *.flow.microsoft.com | https | Power Automate のサイトににアクセスする。 |
| *.powerapps.com | https | Power Apps のサイトににアクセスする。 |
| *.azureedge.net | https | Power Automate CDN にアクセスする。 |
| nps.onyx.azure.net | https | NPS (Net Promoter Score) にアクセスします。 |
| webshell.suite.office.com | https | ヘッダーと検索のための Office にアクセスします。 詳細については、[Office 365 の URL と範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online)を参照してください。 |

## <a name="approval-email-delivery"></a>承認メールの送信
承認メールのルーティングに関する詳細については、[承認メールの送信に関する記事](https://go.microsoft.com/fwlink/?linkid=2128304) を参照してください。

## <a name="ui-flows-required-services"></a>UI フローに必要なサービス
次の表に、UI フローのインストールと実行を成功させるためのユーザーのコンピューターからの接続に関するエンドポイント データ要件を示します。

| エンドポイントの種類 | ドメイン | プロトコル | 使用 |
| ------------- | ------- |  -------- | ---- |
| 世界的なエンドポイント|ocsp.digicert.com<br>ocsp.msocsp.com<br>mscrl.microsoft.com<br>crl3.digicert.com<br>crl4.digicert.com | http | パブリック クラウドの CRL サーバーにアクセスします。 |
| 米国政府機関の GCC および GCC High エンドポイント|ocsp.digicert.com<br>crl3.digicert.com<br>crl4.digicert.com | http | 米国政府機関クラウドの CRL サーバーにアクセスします。 |
| 21Vianet 運用エンドポイント|crl.digicert.cn<br>ocsp.digicert.cn | http | 21Vianet 運用クラウドの CRL サーバーにアクセスします。 |
| すべてのエンドポイント|msedgedriver.azureedge.net<br>chromedriver.storage.googleapis.com | https | UI Flows WebDriver ダウンローダーにアクセスします。 |
