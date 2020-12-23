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
ms.openlocfilehash: 37de75125866a7cbf738f26be5e41646fa86a931
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709999"
---
# <a name="remove-a-solution-aware-flow"></a>ソリューション対応フローを削除する

ソリューションからクラウド フローを削除するか、環境からフローを完全に削除することができます。

操作​​|結果
------|-----------
このソリューションから削除|選択したソリューションからフローが削除されますが、環境内には残ります。 後日、環境内にある他のソリューションのフローを使用することができます。
この環境から削除します|フローが削除されます。この環境内では使用できません。

## <a name="remove-a-cloud-flow-from-a-solution"></a>ソリューションからクラウド フローを削除する

1. Power Automate にサインインし、左側のナビゲーション バーから **ソリューション** を選択します。
1. ソリューションから削除するフローを含むソリューションを選択します。

   ![選択されたソリューション内のフローを示すスクリーンショット。](./media/remove-solution-aware-flow/new-flow-inside-solution.png)
   
1. フローに対して **...** (その他のコマンド) を選択し、**削除** を選択してから、**このソリューションから削除** を選択します。

   ![強調表示されたソリューションからフローを削除するオプションを示すスクリーンショット。](./media/remove-solution-aware-flow/delete-flow-from-solution.png)

>[!IMPORTANT]
>クラウド フローを削除すると、**Common Data Service の既定のソリューション** に移動します。ここで、フローを編集または削除したり、別のソリューションに追加したりすることができます。 

## <a name="delete-a-cloud-flow-from-an-environment"></a>環境からクラウド フローを削除する

1. Power Automate にサインインし、左側のナビゲーション バーから **ソリューション** を選択します。
1. 環境から削除するフローを含むソリューションを選択します。

   ![選択した環境から削除するフローを示すスクリーンショット。](./media/remove-solution-aware-flow/new-flow-inside-solution.png)
   
1. フローに対して **...** (その他のコマンド) を選択し、**削除** を選択してから、**この環境から削除** を選択します。

   ![強調表示された環境からフローを削除するオプションを示すスクリーンショット。](./media/remove-solution-aware-flow/delete-flow-from-environment.png)


## <a name="learn-more"></a>詳細情報を見る

- [ソリューションの作成](./overview-solution-flows.md)
- [ソリューションにクラウド フローを作成する](./create-flow-solution.md)
- [ソリューションのエクスポート](./export-flow-solution.md)
- [ソリューションのインポート](./import-flow-solution.md)
- [ソリューション対応フローを編集する](./edit-solution-aware-flow.md)
