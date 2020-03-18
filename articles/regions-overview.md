---
title: Power Automate のリージョンの概要 | Microsoft Docs
description: Power Automate のリージョンに関する質問と回答の概要
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/28/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8470d927204f1ba40f801c806c34ca0c78336555
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193843"
---
# <a name="faq-for-regions-in-power-automate"></a>Power Automate のリージョンに関する FAQ

このドキュメントでは、Power Automate についてよく寄せられる質問のリストを提供します。

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>自分のフローがデプロイされる場所を確認する方法
フローは、[環境](environments-overview-admin.md)をホストする[リージョン](https://azure.microsoft.com/regions/)にデプロイされます。 たとえば、環境がヨーロッパ リージョンで作成されている場合、フローはヨーロッパのデータ センターに保存されます。

管理者は、Power Automate [管理センター](https://admin.flow.microsoft.com)にサインインすると、リージョンを識別できます。 **[環境]** タブには、既存のすべての環境とそのリージョンが一覧表示されます。

![環境を表示する](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>どのリージョンを利用できますか。
* 米国
* ヨーロッパ
* アジア
* オーストラリア
* インド
* 日本
* カナダ
* 南アメリカ
* イギリス
* 米国政府向け (GCC)
* フランス

## <a name="what-features-are-specific-to-a-given-region"></a>リージョン固有の機能
環境は複数の異なるリージョンに作成でき、その地理的な場所にバインドされます。 環境にフローを作成すると、そのフローはその地理的な場所のデータセンターにデプロイされます。 これは、共通データ モデル、フロー、接続、ゲートウェイ、アプリ、カスタム コネクタなど、その環境で作成するすべての項目に適用されます。

最適なパフォーマンスのためには、ユーザーに最も近いリージョンに環境を作成します。 たとえば、ユーザーがヨーロッパにいる場合は、ヨーロッパ リージョンに環境を作成します。 ユーザーが米国にいる場合は、米国リージョンに環境を作成します。

## <a name="gateways"></a>ゲートウェイ
ゲートウェイには次の制限があります。

* インド リージョンでは利用できません。
* 既定の環境でのみサポートされ、カスタム環境ではサポートされていません。

## <a name="is-power-automate-available-in-national-clouds"></a>Power Automate は各国のクラウドで使用できますか?
はい。 [詳細情報](./us-govt.md)

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>各リージョンではどのような送信 IP アドレスが使われますか。
「[制限事項と構成](limits-and-config.md)」を参照してください。

