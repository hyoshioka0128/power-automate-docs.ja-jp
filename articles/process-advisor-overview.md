---
title: Process Advisor の概要 (プレビュー) | Microsoft Docs
description: Power Automate の Process Advisor 機能の概要。
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
ms.openlocfilehash: 4bbaaca3f1386746d678331cbd319b8e27260d03
ms.sourcegitcommit: cdc567f1760c85fa8030b17a6c158254b92d16bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "4723481"
---
# <a name="overview-of-process-advisor-preview"></a>Process Advisor の概要 (プレビュー)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="what-is-process-advisor"></a>Process Advisor とは何ですか?

Process Advisor は、手動のビジネス タスクを記録および分析します。 非効率性を検出し、最適化と自動化の可能性を示します。 例: 医療機関では、Process Advisor を使用して患者のチェックイン手順を記録できます。 Process Advisor は、チェックイン プロセスを視覚化するプロセス マップを自動的に作成します。 どの活動に最も時間がかかるか、チェックイン プロセスのバリエーションがいくつあるか、どのバリエーションとアクションに最も時間がかかるかを確認できます。 この情報と Process Advisor の強力な機能を使用して改善を推進し、ビジネスに変化をもたらすことができます。

>[!IMPORTANT]
>
>- これはプレビュー機能です。
>- プレビュー機能は運用環境での使用を想定しておらず、機能が制限されている可能性があります。 これらの機能を公式リリースの前に使用できるようにすることで、顧客が一足先にアクセスし、そこからフィードバックを得ることができます。

## <a name="prerequisites"></a>前提条件

Process Advisor を使用する前に、次の前提条件を確認してください。

- Microsoft Dataverse データベースを備えた Power Platform 環境
  - 環境の作成方法については、[Power Platform 管理センターで環境を作成および管理する](/power-platform/admin/create-environment)を参照してください
  - データベースを環境に追加する方法については、[Microsoft Dataverse データベースを追加する](/power-platform/admin/create-database)を参照してください
- [Power Automate](https://powerautomate.microsoft.com/) へのアクセス
- [Power Automate Desktop](/ui-flows/desktop/introduction)
  - UI フローのライセンスを持っていることを確認してください。 試用版ライセンスを開始するには、既定の環境を選択し、flow.microsoft.com/manage/uiflows にアクセスします。 まだライセンスをお持ちでない場合は、試用版ライセンスを開始するように求められます。
