---
title: Power Automate GDPRデータ対象者の検出要求 | Microsoft Docs
description: Power Automate を使用して GDPRデータ対象者の検出要求に対応する方法を説明します。
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 12179fc266b89acf90c52b4d516c9ff8716168d2
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709591"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-power-automate"></a>Power Automate の GDPRデータ対象者の検出要求に対応する


DSR への応答の最初のステップは、要求の主体である個人データを見つけることです。 この最初のステップは、DSR の要求を承諾または拒絶するための組織の要件を DSR が満たしているかどうかを判断するのに役立ちます。 たとえば、問題の個人データを特定および確認した後で、その要求が組織の要件を満たしていないと判断すると、他のユーザーの権利と自由に悪い影響を与える可能性があります。

以下は、特定のユーザーの個人データを含む Power Automate リソースの種類一覧です。

|**個人データを含むリソース**|**目的**|
|-----|-----|
|システムによって生成されたログ|システムイベントと履歴をキャプチャする遠隔的な測定。|
|実行履歴|過去 28 日間の各フローの実行の履歴です。 このデータには、開始時刻、終了時刻、状態、およびフローのすべての入力/出力情報が含まれています。 [詳細情報](https://flow.microsoft.com/blog/download-history-recurrence/)|
|アクティビティ フィード| 実行状態、エラー、通知など、フロー アクティビティの要約を提供します。|
|ユーザーのジョブ|ユーザーには表示されず、フロー実行のため、ユーザーに代わって実行されるシステム ジョブです。|
|フロー|クラウド フローに対して存在するワークフロー ロジックです。 [詳細情報](https://docs.microsoft.com/flow/get-started-logic-flow)|
|フロー アクセス許可|フローは、他のユーザーと共有したり、他のユーザーに再割り当てしたりできます。 アクセス許可リストはすべてのフローに存在します。 [詳細情報](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|ユーザーの詳細|ユーザーが見ることはできない、フローの実行をサポートする詳細情報です。|
|接続|コネクタにより使用され、API、システム、データベースなどへの接続に許可されます。 [詳細情報](https://docs.microsoft.com/flow/add-manage-connections)|
|接続のアクセス許可|特定の接続のアクセス許可です。 [詳細情報](https://docs.microsoft.com/flow/add-manage-connections)|
|カスタム コネクタ|カスタム システムまたはサードパーティ システムに接続できる、ユーザーが作成して公開したカスタム コネクタです。 [詳細情報](https://docs.microsoft.com/connectors/custom-connectors/)|
|カスタム コネクタのアクセス許可|カスタム コネクタのアクセス許可リストです。 [詳細情報](https://docs.microsoft.com/connectors/custom-connectors/share)|
|ゲートウェイ|ゲートウェイはオンプレミスのデータ サービスであり、ユーザーはそれをインストールすることで、Power Automate とクラウド内に存在しないデータ ソースの間でデータをすばやく安全に転送できます。 [詳細情報](https://docs.microsoft.com/flow/gateway-manage)|
|ゲートウェイのアクセス許可|ゲートウェイは、組織内でユーザーと共有できます。 [詳細情報](https://go.microsoft.com/fwlink/?linkid=872249)|
