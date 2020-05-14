---
title: オンプレミス データ ゲートウェイ | Microsoft Docs
description: この記事では、Power Automate のオンプレミス データ ゲートウェイの概要をご紹介します。
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2a0e2d3ff9fb39019ef4b8f37a7715229844c388
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297738"
---
# <a name="what-is-an-on-premises-data-gateway"></a>オンプレミス データ ゲートウェイとは


オンプレミス データ ゲートウェイはブリッジとして機能し、オンプレミス データ (クラウド内に存在しないデータ) といくつかの Microsoft クラウド サービスとの間でデータをすばやく安全に転送できます。 これらのクラウド サービスには、Power BI、Power Apps、Power Automate、Azure Analysis Services、Azure Logic Apps が含まれています。 ゲートウェイを使用することにより、組織はオンプレミス ネットワーク上のデータベースやその他のデータソースを維持しながら、そのオンプレミス データをクラウド サービスで安全に使用することができます。

## <a name="how-the-gateway-works"></a>ゲートウェイのしくみ

![ゲートウェイの概要](media/gateway-reference/on-premises-data-gateway.png)

ゲートウェイのしくみの詳細については、「[オンプレミス データ ゲートウェイのアーキテクチャ](/data-integration/gateway/service-gateway-onprem-indepth)」を参照してください。

## <a name="types-of-gateways"></a>ゲートウェイの種類

ゲートウェイには次の 2 種類があり、それぞれ異なるシナリオで使用されます。

- **オンプレミス データ ゲートウェイ**の場合、複数のユーザーが複数のオンプレミスのデータ ソースに接続できます。 単一のゲートウェイ インストールで、サポートされているすべてのサービスでオンプレミス データゲートウェイを使用できます。 このゲートウェイは、複数のユーザーが複数のデータ ソースにアクセスする複雑なシナリオに適しています。

- **オンプレミス データ ゲートウェイ (個人用モード)** の場合、1 人のユーザーがソースに接続できます。他のユーザーとは共有できません。 オンプレミスのデータ ゲートウェイ (個人用モード) は、Power BI でのみ使用できます。 このゲートウェイは、レポートを作成するユーザーが 1 人だけであり、データ ソースを他のユーザーと共有する必要がないシナリオに適しています。

## <a name="use-a-gateway"></a>ゲートウェイの使用

ゲートウェイを使用するための 4 つの主要な手順があります。

1. ローカル コンピューターに[ゲートウェイをダウンロードしてインストール](/data-integration/gateway/service-gateway-install)します。
2. ご利用のファイアウォールやその他のネットワーク要件に基づいてゲートウェイを[構成](/data-integration/gateway/service-gateway-app)します。
3. 他のネットワーク要件も管理および操作できる[ゲートウェイ管理者を追加](/data-integration/gateway/service-gateway-manage)します。
4. エラーが発生した場合にゲートウェイの[トラブルシューティング](/data-integration/gateway/service-gateway-tshoot)を行います。

## <a name="next-steps"></a>次のステップ

- [オンプレミス データ ゲートウェイのインストール](/data-integration/gateway/service-gateway-install)
