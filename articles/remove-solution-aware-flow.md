---
title: ソリューション対応フローを削除する方法に関する説明 | Microsoft Docs
description: ソリューションからソリューション対応フローを削除する方法、または環境からそれらを削除する方法について説明します。
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
ms.date: 10/12/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a3bb56c6b145a8ec6923ee274005ecd5cfe49289
ms.sourcegitcommit: a881042f3de3cce8087986174fed53fd26b163f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2020
ms.locfileid: "4365184"
---
# <a name="remove-a-solution-aware-flow"></a>ソリューション対応フローを削除する

ソリューションからフローを削除するか、環境からフローを完全に削除することができます。

|操作​​|結果|
|------|-----------|
|このソリューションから削除|フローは選択したソリューションから削除されますが、環境内に残り、後日環境内の他のソリューションで使用できます。|
|この環境から削除します|フローが削除されます。この環境内では使用できません。|

## <a name="remove-a-flow-from-a-solution"></a>ソリューションからフローを削除する

1. Power Automate にサインインし、左側のナビゲーション バーから **ソリューション** を選択します。
1. 削除するフローを含むソリューションを選択します。
1. フローに対して **その他のコマンド** (...) を選択し、**削除** を選択してから、**このソリューションから削除** を選択します。

>[!IMPORTANT]
>フローを削除すると、**Common Data Service 既定のソリューション** に移動します。ここで、フローを編集または削除したり、別のソリューションに追加したりできます。 

## <a name="delete-a-flow-from-an-environment"></a>環境からフローを削除する

1. Power Automate にサインインし、左側のナビゲーション バーから **ソリューション** を選択します。
1. 環境から削除するフローを含むソリューションを選択します。
1. フローに対して **その他のコマンド** (...) を選択し、**削除** を選択してから、**この環境から削除** を選択します。

## <a name="learn-more"></a>詳細情報を見る

- [ソリューションの作成](./overview-solution-flows.md)
- [ソリューションにフローを作成する](./create-flow-solution.md)
- [ソリューションのエクスポート](./export-flow-solution.md)
- [ソリューションのインポート](./import-flow-solution.md)
- [ソリューション対応フローを編集する](./edit-solution-aware-flow.md)
