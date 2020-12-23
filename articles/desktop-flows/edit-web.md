---
title: Selenium IDE のフローを編集する方法 | Microsoft Docs
description: Selenium IDE のフローを編集する方法について説明します。
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: bd849da1fa787d1e4f3dfb9c9a75b17ae9849231
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711655"
---
# <a name="edit-selenium-ide-flows"></a>Selenium IDE のフローを編集する

Selenium IDE のフローでは [Microsoft Edge (バージョン 80 またはそれ以降)](https://www.microsoft.com/edge/) または Google Chrome で実行する web サイトを自動化できます。 [Web UI フローの作成後](create-web.md)は、編集が必要となる場合があります。 このドキュメントに記載の手順に従って、Selenium IDE のフローを編集する方法を理解します。

## <a name="edit-in-selenium-ide"></a>Selenium IDE の編集

Selenium IDE を使用して、ご利用の Selenium IDE のフローを編集します。

>[!NOTE]
>Selenium IDE の編集は、Advanced ユーザーや開発者が行うことを意図しています。

スクリプトの編集については、[Selenium のコマンド](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/)を参照してください。

Selenium IDE では、ユーザー インターフェイス要素をターゲットにする際に、異なるセレクターと既定のセレクターを提案します。 また、提案されたセレクターいずれも適切でない場合は、新しいセレクターを定義することもできます。 これは通常、Web サイトの HTML 構造が非常に動的な場合に発生します。

Selenium IDE が特定したセレクターの例を紹介します:

![想定されるセレクター](../media/edit-web/possible-selectors.png "想定されるセレクター")

## <a name="accessing-a-property-of-an-object-variable-or-item-of-an-array-variable"></a>オブジェクト変数や配列変数の項目のプロパティにアクセスする

この高度な機能を使用すると、\${foo.bar} のような構文を使用して、foo オブジェクトの bar プロパティにアクセスできます。 また、ストア コマンドで foo.bar を値プロパティとして使用することで、foo の bar プロパティに書き込むこともできます。 \${foo[0]} のような構文を使用して、foo 配列内のインデックス 0 の項目にアクセスすることもできます。

## <a name="next-steps"></a>次の手順

- [Selenium IDE のフローを作成する](create-web.md)
- [Windows レコーダー (V1) のフローを実行する](run-desktop-flow.md)
