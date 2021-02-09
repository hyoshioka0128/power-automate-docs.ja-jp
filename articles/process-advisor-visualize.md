---
title: Process Advisor のプロセスを視覚化する | Microsoft Docs
description: Process Advisor 機能のプロセスを視覚化する方法。
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
ms.openlocfilehash: 5f90c53a4f4cf686add8e2a066c9f972e472e2fa
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711693"
---
# <a name="visualize-processes-preview"></a>プロセスの視覚化 (プレビュー)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="process-map"></a>プロセス マップ

> [!div class="mx-imgBorder"]
> ![プロセス マップ](media/process-advisor-visualize/process-map.png "Process Advisor のプロセス マップ")

プロセス マップにより、プロセスの視覚化と分析が可能になります。 ビジネス プロセスがどのように実行されているかをグラフィカルに表現することにより、営業案件がどこにあるかについてインサイトを収集することができます。  プロセス マップを使用するには、Analytics に移動し、プロセス マップ タブを選択します。

活動はタスクまたはアクションを示し、そのシーケンスがビジネス プロセスになります。 活動は、人間が実行することも、自動化して機械が実行することもできます。 プロセス マップでは、さまざまなアクティビティがノードとして表示され、アクティビティ間の移行がエッジとして表示されます。  各プロセス シーケンスには、開始と終了があります。

さまざまなアクティビティの組み合わせとバリアントがプロセス マップに個別に表示されます。 プロセス バリアントは、プロセスの最初から最後までの一意のパスです。 つまり、プロセス バリアントは、プロセス内の最初から最後までの「トレース」のような、特定のアクティビティ シーケンスです。 各バリアントは、他のバリアントと少なくとも 1 つのアクティビティが異なります。
プロセスマップで、追加のメトリック、アクティビティの頻度、およびスループット時間を確認できます。
頻度は、それを通過する記録やケースの合計数を示します。  スループット時間は、ケースの最初のイベントから最後のイベントまでの時間です。
利用可能なさまざまなフィルターにより、プロセスにドリルダウンすることができます。

- バリアント セレクタにより、1 つのバリアント、または一連のプロセス バリアントを選択して、プロセス マップに視覚化することができます。
- 記録セレクタにより、1 つの記録、または一連の記録を選択して、プロセス マップに視覚化することができます。
- 時間フィルターにより、特定の期間で視覚化されたプロセスを確認できます。
また、プロセスをより深く理解するのに役立つ主要業績評価指標が利用可能です。 それはこのトピックで説明されています。

## <a name="time-analysis"></a>時間分析

> [!div class="mx-imgBorder"]
> ![分析画面](media/process-advisor-visualize/analytics-screen.png "分析画面")

 追加のプロセス分析を表示するには、**時間分析** タブを選択します。プロセスを理解するのに役立つ複数の主要業績評価指標 (KPI) とビジュアル化を標準で取得することができます。 メトリックとビジュアル、およびそれらがプロセスについて何を教えてくれるかの一覧を次に示します。

## <a name="kpis"></a>KPI:

- **/記録数**: このプロセスを分析するために送信された、同じプロセスの記録の数を示します。 利用できる記録が多いほど、得られるインサイトが多くなります。 たとえば、完了までのパスが異なることが多いプロセスの記録が少数の場合、プロセスが取る可能性のあるすべてのバリエーションについてのインサイトが得られない可能性があります。
- **/ユーザー数**: プロセスを記録した人数を通知します。 通常、プロセスが多くの人によって実行される場合、プロセスが取る可能性のあるバリエーションを理解するために、可能な限り多くの人々にプロセスの記録を提出してもらうのが理想です。 
- **/アクティビティ数**: プロセスにいくつの手順があるかを示します。 プロセス所有者は、独自の手順を定義したり、分析用の記録の準備中に他の人にアクティビティを定義させたりすることができます。 プロセスを分析するために、デスクトップ上のユーザー アクティビティを分かりやすいアクティビティでグループ化することができます。 たとえば、請求プロセスでは、アクティビティは次のようになります。請求書を開き、請求書発行アプリにデータを入力し、アプリと請求書を閉じます。 
- **スループット時間 (平均)**: プロセスに関連付けられているすべての記録において、プロセスが完了するまでにかかる平均時間を示します。 スループット時間を深く掘り下げると、プロセスのボトルネックがわかるため、これはプロセス マイニングにとって最も重要なデータ要素の 1 つです。
- **スループット時間 (中央値)**: 通常、中央値は、プロセスが完了するのにかかる最も頻繁な時間を示します。 少数の記録または 1 つの記録がほとんどの記録と大きく異なり、完了までの平均時間がこの問題のある記録に偏っているように見える場合に非常に役立つメトリックです。 ユーザーがプロセスを完了するまでの時間を誤って解釈することを防ぐために、この測定値は、単純な平均ではなく、最も頻繁な時間を表示することによってインサイトを提供します。
- **/バリアントの数**: ユーザーがプロセスを完了するためにかかったさまざまなパスの数を示します。 たとえば、あるユーザーは発注書を完成させるプロセスに 11 の手順があるのに対し、別のユーザーは 7 つしかないことがあります。

## <a name="visualizations"></a>ビジュアル化

- **記録による時間分布**: 最も一般的な時間範囲にある記録数を示します。
- **平均時間によるアクティビティ**: 各アクティビティにかかる平均時間を示すことにより、このビジュアルで最も時間のかかるアクティビティをひとめで識別できます。
- **時間中央値によるアクティビティ**: 各アクティビティにかかる時間中央値を示すことにより、最も時間のかかるアクティビティを識別し、外れ値が歪んでいないこと、アクティビティごとに費やされる最も頻繁な時間はどれくらいかを確認します。
- **平均時間と中央値による記録**: 平均時間と中央値で記録を表示します。 この視覚化を使用し、期間にしたがった希望の記録のフィルター処理を簡単にすることができます。 フィルター:
- **記録名**: 特定の記録または一連の記録のフィルター。 これにより、関心のある記録または一連の記録のフィルター処理をすることができます。
- **開始日**: 記録が開始および終了した時間範囲のフィルター処理をします。 たとえば、プロセスが時間の経過と共に変化した場合、特定の期間の後に開始された記録のフィルター処理をすることにより、プロセスの変更後にメトリックに影響があったかどうかを確認することができます。