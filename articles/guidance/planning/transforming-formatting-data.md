---
title: Power Automate プロジェクトの一部としてのデータの変換とフォーマット | Microsoft Docs
description: プロセスの後半で別のシステムから使用できるように、システムから取得したデータを変換する必要がある場合があります。 この記事では、使用できるさまざまな方法について説明します。
author: taiki-yoshida
ms.service: flow
ms.topic: conceptual
ms.custom: guidance
ms.date: 12/10/2020
ms.author: tayoshi
ms.reviewer: kathyos
ms.openlocfilehash: a2640fb6c60bc3a508f38a77e9667a1a520add82
ms.sourcegitcommit: 970ad18a7ef795bff294f39ccfc8578bab9387d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "4714421"
---
# <a name="transforming-and-formatting-data"></a>データの変換およびフォーマット

システムから取得したデータの一部は、プロセスの後半で使用されるその他のシステムが認識できるように変換する必要がある場合があります。 たとえば、ローカル時間を協定世界時 (UTC) に変換したり、ある通貨を別の通貨に変換したりする必要がある場合があります。 データを別のシステムが認識できるように、別の形式に変換できます。 プロセス自動化のアーキテクチャを設計するときは、データ形式 (および形式の変換) を考慮してください。

データの変換およびフォーマットを行う方法の一部を次に示します。

## <a name="built-in-actions"></a>組み込みアクション

組み込みアクションを使用して、値と文字列を異なる形式に変換できます。

![テキスト用の組み込みアクション](media/text-function.png "テキスト用の組み込みアクション")

## <a name="expressions"></a>式

式は、データの変換と操作に使用できる Excel 風の方程式です。 

![式を使用して文字列を連結する例](media/using-expressions.png "文字列と式を連結する例")

さまざまな式の一覧を以下に示します。

-   [文字列関数](/azure/logic-apps/workflow-definition-language-functions-reference#string-functions)

-   [コレクション関数](/azure/logic-apps/workflow-definition-language-functions-reference#collection-functions)

-   [論理比較関数](/azure/logic-apps/workflow-definition-language-functions-reference#logical-comparison-functions)

-   [変換関数](/azure/logic-apps/workflow-definition-language-functions-reference#conversion-functions)

-   [暗黙的なデータ型変換](/azure/logic-apps/workflow-definition-language-functions-reference#implicit-data-type-conversions)

-   [数学関数](/azure/logic-apps/workflow-definition-language-functions-reference#math-functions)

-   [日付と時刻関数](/azure/logic-apps/workflow-definition-language-functions-reference#date-and-time-functions)

-   [ワークフロー関数](/azure/logic-apps/workflow-definition-language-functions-reference#workflow-functions)

-   [URI 解析関数](/azure/logic-apps/workflow-definition-language-functions-reference#uri-parsing-functions)

-   [操作関数: JSON & XML](/azure/logic-apps/workflow-definition-language-functions-reference#manipulation-functions-json--xml)

詳細な一覧については、[Azure Logic Apps および Power Automate の式で関数を使用するためのリファレンス ガイド](/azure/logic-apps/workflow-definition-language-functions-reference) に移動してください。

> [!div class="nextstepaction"]
> [次のステップ: メッセージと通知の形式化](formalizing-messages-alerts.md)