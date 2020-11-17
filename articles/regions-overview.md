---
title: Power Automate のリージョンの概要 | Microsoft Docs
description: Power Automate のリージョンに関する質問と回答の概要
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2020
ms.author: hamenon
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f7bc45f7ff7d6ebdb263cf1124cf8b266d28f2e4
ms.sourcegitcommit: 7a3df04b817ecf8ad99ca7bb551804fe83b0861d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2020
ms.locfileid: "4109932"
---
# <a name="power-automate-regions-overview"></a>Power Automate リージョンの概要

Power Automate ではフローを Power Platform 環境に作成します。 これらの環境は、Power Platform 環境を保存するデータセンターの所在地に対応するリージョンに固有です。

つまり、フローは [Power Platform 環境](environments-overview-admin.md) をホストする [データセンター リージョン](https://azure.microsoft.com/regions/) に展開されます。

## <a name="more-information-about-power-platform-regions"></a>Power Platform リージョンに関する詳細情報

[Power Platform リージョンの概要](/power-platform/admin/regions-overview)

[Azure の地域](https://azure.microsoft.com/global-infrastructure/geographies/)

## <a name="region-mappings-for-power-automate-and-gateways"></a>Power Automate とゲートウェイのリージョン マッピング

ゲートウェイがインストールされているリージョンは、Power Automate リージョンにマップする必要があります。 地理的な境界を越えることはサポートされていません。 

マッピング情報を次に示します:

Power Platform 地域|ゲートウェイ リージョン
-----|-----
米国 (プレビューを含む)|米国中部、米国東部 2、米国東部、米国中北部、米国中南部、米国西部 2、米国中西部、米国西部
アジア|東アジア、東南アジア
オーストラリア|オーストラリア東部、オーストラリア南東部
カナダ|カナダ中部、カナダ東部
欧州|北ヨーロッパ、西ヨーロッパ
フランス|フランス中部、フランス南部
ドイツ|ドイツ中西部、ドイツ北
インド|インド中部、インド南部、インド西部
日本|東日本、西日本
南アメリカ|ブラジル南部
イギリス|英国南部、英国西部

## <a name="frequently-asked-questions"></a>よくあるご質問

### <a name="what-region-should-i-use"></a>使用するリージョンはどれですか?

顧客に最も近いリージョンに存在する環境にフローを作成することを推奨します。 環境をホストするデータセンターが情報を利用するユーザーの近くに存在すると、パフォーマンスの向上が見込まれます。

### <a name="how-can-i-find-out-the-region-where-my-flow-is-deployed"></a>フローを展開したリージョンを確認する方法は?

管理者は Power Platform [管理センター](https://admin.powerplatform.microsoft.com/) にサインインしてリージョンを確認できます。 **環境** タブには、既存のすべての環境とそのリージョンが一覧表示されます。

### <a name="is-power-automate-available-in-national-clouds"></a>Power Automate は国内クラウドで利用できますか?

はい。 [詳細情報](./us-govt.md)

### <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>各リージョンではどのような送信 IP アドレスが使われますか?

[制限事項と構成](limits-and-config.md) を参照してください。
