---
title: セキュリティとプライバシー (プレビュー) | Microsoft Docs
description: Process Advisor のセキュリティとプライバシー。
services: ''
suite: flow
documentationcenter: na
author: nijemcevic
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2020
ms.author: tatn
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ed03da2dcd5575b41c002d969687d38c650dd99f
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711666"
---
# <a name="security-and-privacy-preview"></a>セキュリティとプライバシー (プレビュー)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="security"></a>セキュリティ

Process Advisor は環境セキュリティと Microsoft Dataverse セキュリティ ロールと特権に依存して、Power Automate の機能へのアクセスを許可します。 詳細情報: [Power Platform セキュリティの概要](/power-platform/admin/wp-security)

Dataverse では、いくつかの特権が既定で設定されます。 これにより、システム管理者が追加の操作を行うことなく、組み込みのセキュリティ ロールで Process Advisor を使用できるようになります。 具体的には次のとおりです。

- 環境作成者は、Process Advisor を使用して、プロセスを作成および共有できます。
- 管理者とシステム カスタマイザーは、環境で作成されたすべてのプロセスにアクセスできます。

これらのセキュリティ ロールには、Dataverse の Process Advisor エンティティに対する特権が備わっています。 カスタム セキュリティ ロールは、次のアクセス許可を持っている場合、Process Advisor でプロセスを作成できます。

- ユーザーおよびユーザー設定テーブル (ビジネス管理タブ) の組織の読み取りアクセス許可
- エンティティ、フィールド、および関連付けテーブルに対する組織の読み取りアクセス許可 (カスタマイズ タブ)
- ユーザーがプロセス テーブルでアクセス許可を作成、読み取り、書き込み、削除、追加、追加先、割り当て、共有する (カスタマイズ タブ)
- ユーザーが PM 推測タスク、PM 記録、およびワークフロー バイナリ テーブルでアクセス許可を作成、読み取り、書き込み、削除、追加、追加先、割り当て、共有する (カスタマイズ タブ)

## <a name="privacy"></a>プライバシー​

プロセスとその記録を共有することは、Process Advisor で豊富な分析とインサイトを作成するために不可欠です。 ユーザーは、記録を追加してプロセスに貢献するよう招かれています。 Power Automate Desktop を使用してプロセスを記録し、Process Advisor にインポートします。 プロセスの記録でキャプチャされた情報のほとんどは、プロセス活動の理解に不可欠ですが、一部のステップには機密情報が含まれている場合があります。 ただし、記録内の個人を特定する情報 (PII) または機密情報を変更および削除することはできます。
Power Automate Desktop で、ユーザーは次のことができます。

- 機密のステップを削除するか、入力データ情報を変更する。
- 機密情報や PII の記録を避けるために、記録を一時停止して再開する。

記録が Process Advisor にインポートされた後でも、次の手順を実行して機密情報を削除できます。

- ステップ名や説明の名前を変更する。
- スクリーンショットを削除する。
