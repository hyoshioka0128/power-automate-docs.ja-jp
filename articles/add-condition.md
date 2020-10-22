---
title: フローに条件を追加する | Microsoft Docs
description: 条件が true の場合にのみ、フローが 1 つ以上のタスクの実行を指定します。
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
ms.date: 06/08/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: cb914dc888d11d2e0abf96211898d78015256505
ms.sourcegitcommit: 2971e852bdb76efbe012b9de8df8e7f492063184
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "3900194"
---
# <a name="add-a-condition-to-a-flow"></a>フローに条件を追加する


条件が true の場合にのみ、フローが 1 つ以上のタスクの実行を指定します。 たとえば、特定のキーワードを含むツイートが 10 回以上リツイートされた場合のみ電子メールを受け取るように指定します。

## <a name="prerequisites"></a>前提条件

* テンプレートから[フローを作成する](get-started-logic-template.md) - このチュートリアルでは、例として[こちらのテンプレートを使用します](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/)

## <a name="add-a-condition"></a>条件を追加する

1. [Power Automate](https://flow.microsoft.com) で、**自分のフロー**を選択します。

    まだサイン インしていない場合は、サイン インが求められる場合があります。

1. **自分のフロー** からいずれかのフローを選択し、続いて**その他のコマンド** (3 つの点で表わされています) を選択します。

   ![編集を選択する](./media/add-condition/select-edit.png)

    このチュートリアルでは、Twitter のトリガーと SharePoint のアクションを使用した例を説明します。

1. **編集**を選択します。

1. 最後のアクションの配下にある **新規ステップ** > **条件** を選択します。

1. **条件** カードで、左側ボックスの空の領域を選択します。

    **動的コンテンツ** 一覧が表示されます。

1. **リツイート数** を選択してボックスに追加します。

1. **条件** カード中央のボックスで、**と等しい、またはよりも多い** を選択します。

1. 右側のボックスに **10** を入力します。

    ![パラメーターが設定されているオブジェクト名ボックス](./media/add-condition/specify-condition.png)

    以上で条件の設定が完了しました。以下の手順を完了すると、 **リツイート数**が 10 以上の場合に電子メールが送信されます。

1. 送信条件が**はいの場合**で、**アクションの追加**を選択します。 
1. 検索バーに**電子メールの送信**と入力し、続いて**電子メールの送信 (V2)** を選択します。

   ![検索して電子メールを送信する](./media/add-condition/if-yes-condition.png)

1. **電子メールの送信 (V2)** カードを好みに合わせて構成し、**リツイート数** が 10 より大きい場合にフローが送信するメールの内容を示します。

   また、**リツイート数**が 10 以下の場合に適用する、**いいえの場合**の条件を設定することもできます。

1. フローを保存します。

>[!TIP]
>条件カードの**追加**ボタンで複雑な条件を作成することができます。

![複雑な条件の追加](./media/add-condition/add-complex-condition.png)

利用可能な[式](https://msdn.microsoft.com/library/azure/mt643789.aspx)を身につける。

## <a name="next-steps"></a>次の手順

詳細設定モードで条件に[式を使用する](use-expressions-in-conditions.md)方法について説明します。
