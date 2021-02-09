---
title: オンプレミスのデータ ゲートウェイを管理する詳細情報 | Microsoft Docs
description: Power Automate でオンプレミス データ ゲートウェイを表示してインストールします。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/13/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a1d01caa7ffa5f3611f7419fd4b3c384e1b89a52
ms.sourcegitcommit: 2971e852bdb76efbe012b9de8df8e7f492063184
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "3900242"
---
# <a name="manage-an-on-premises-data-gateway-in-power-automate"></a>Power Automate でオンプレミス データ ゲートウェイを管理する


オンプレミス データ ゲートウェイをインストールして管理すると、Power Automate を介してさまざまなクラウドベースのアプリをオンプレミスのデータやアプリと安全に統合できます。

ゲートウェイを使用すると、次の接続を介して、オンプレミス データに接続できます。

* Apache Impala
* 作成するカスタム コネクタ
* DB2
* ファイル システム
* HTTP と Azure AD
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* SharePoint
* SQL サーバー
* Teradata (プレビュー)

> [!IMPORTANT]
> Microsoft SharePoint  データ ゲートウェイは、HTTP トラフィックと HTTPS トラフィックの両方をサポートするようになりました。

## <a name="prerequisites"></a>前提条件

* Power Automate の[新規登録](sign-up-sign-in.md)に使用したユーザー名とパスワード
* ゲートウェイの管理者権限。

  インストールするゲートウェイごとに、これらのアクセス許可が既定で存在します。 また、別のゲートウェイの管理者はそのゲートウェイに対して、これらのアクセス許可を付与できます。
* ゲートウェイをサポートするライセンス。 詳細については、「[価格設定のページ](https://flow.microsoft.com/pricing/)」の「接続」セクションを参照してください。

> [!TIP]
> [任意の環境](environments-overview-maker.md) にゲートウェイとオンプレミス接続を作成できます。

## <a name="install-a-gateway"></a>ゲートウェイをインストールする

ゲートウェイをインストールするには、「[オンプレミス データ ゲートウェイをインストールする](/data-integration/gateway/service-gateway-install)」の手順に従います。 _オンプレミス データ ゲートウェイ (個人用モード)_ は Power BI にのみ使用できるため、ゲートウェイを標準モードでインストールします。

## <a name="view-your-gateways"></a>ゲートウェイを表示する

[Power Automate](https://flow.microsoft.com) にサインインして左側のナビゲーション ウィンドウから **データ** > **ゲートウェイ** を選択します。

> [!NOTE]
> Power Apps におけるゲートウェイへのアクセス権限を作成した場合、Power Automate の **ゲートウェイ** 一覧にそのゲートウェイが表示されます。

## <a name="cluster-your-gateways"></a>ゲートウェイをクラスター化する

[オンプレミス データ ゲートウェイ高可用性クラスターのインストール](/data-integration/gateway/service-gateway-high-availability-clusters) を作成して、オンプレミス データ リソースにアクセスする際の単一障害点を回避します。

既定では、Power Automate では、クラスター内のプライマリ ゲートウェイが使用されます。 プライマリ ゲートウェイが使用できない場合は、サービスがクラスターに存在する次のゲートウェイに順次切り替わります。

ゲートウェイ クラスターの設定が完了すると、クラスターに存在するすべてのゲートウェイにトラフィックを分散できます。

次の手順に従ってゲートウェイ全体にトラフィックを分散します。

1. 左側のナビゲーション バーから **データ** を選択します。
1. **ゲートウェイ** を選択します。
1. いずれかのゲートウェイを選択します。
1. **このクラスターに存在するすべてのアクティブなゲートウェイに要求を分散する** を選択します。
1. **適用**を選択して、変更を適用します。

詳細については、[ゲートウェイの概要](gateway-reference.md) を参照してください。

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
