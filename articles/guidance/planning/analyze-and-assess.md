---
title: Power Automate プロジェクトでの自動化によるビジネスへの影響の評価 | Microsoft Docs
description: 自動化を正常に展開した後、成功の指標を使用して、新旧のビジネス プロセスを比較することにより、その影響を評価できます。
author: taiki-yoshida
ms.service: flow
ms.topic: conceptual
ms.custom: guidance
ms.date: 12/10/2020
ms.author: tayoshi
ms.reviewer: kathyos
ms.openlocfilehash: 0385a7468f5c41b3dbde87a622f2924c3ef1ffdd
ms.sourcegitcommit: 970ad18a7ef795bff294f39ccfc8578bab9387d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "4714407"
---
# <a name="assessing-the-business-impact-of-the-automation"></a>自動化のビジネスへの影響を評価する

自動化を正常に展開した後、定義した成功の指標を使用して、元のビジネス プロセスと新しいビジネス プロセスを比較することにより、その影響を評価できます。 自動化の結果は 30 日間保存されます。その間、その結果を表示して 1 日のアクションと実行の総数を分析できます。
<!--markdownlint-disable MD036-->
**フロー分析を表示するには**

1. **自分のフロー** に移動します。

2. 分析するフローを選択します。

3. **分析** を選択します。

   ![フローに対する分析](media/analytics-tab.png "フローに対する分析")

4. **使用** タブを選択します。

   ![フローの使用](media/usage-tab.png "フローの使用")

## <a name="get-the-number-of-flow-runs"></a>フロー実行の数を取得する

**使用** タブには、特定のビジネス プロセスを自動化するためにフローが 1 日に何回使用されたかが表示されます。

**Excel のワークブックにデータをエクスポートするには**

1. エクスポートするデータを示すグラフにカーソルを合わせます。

2. **詳細オプション** を選択します。

3. **データのエクスポート** を選択します。

   ![フロー実行のグラフ](media/flow-runs-graph.png "フロー実行のグラフ")

4. 必要なファイル形式 (Excel ワークブックまたは CSV) を選択します。

5. **エクスポート** を選択します。

## <a name="get-the-flow-run-duration"></a>フロー実行の期間を取得する

**各フロー実行の期間を確認するには**

1. **自分のフロー** に移動します。

2. 分析するフローを選択します。

3. 28 日間の実行履歴で、**すべての実行** を選択します。

4. 情報をエクスポートする場合は、**.csv ファイルを取得する** を選択します。

   ![実行履歴の一覧](media/run-history-list.png "実行履歴の一覧")

CSV ファイルには、各実行の開始時刻と終了時刻が含まれています。 Excel を使用して、期間を再計算し、追加の分析 (平均期間の検索など) を実行できます。
期間を秒単位で取得するには、次の式を使用します。

&nbsp;&nbsp;&nbsp;(**実行終了時間** セル &minus; **実行開始時間** セル) &times; 24 &times; 60 &times; 60

![Excel で期間を計算する](media/excel-calculation.png "Excel で期間を計算する")

平均期間を取得するには、期間の合計数を取得し、それを実行数 (行の数) で割ります。

実行回数と実行期間がわかったので、前の手動プロセスと比較することで、自動化によって節約された時間を確認できます。

## <a name="example-scenario"></a>シナリオの例

例として、現金償還のシナリオを取り上げましょう。

![現金償還のシナリオ例](media/diagram-accounting-before.png "現金償還のシナリオ例")

これまで Abhay の会計チームは、経費報告書に添付された承認メールで受け取った情報に基づいて、会計システムで会計コードを入力し、取引を入力し、取引を転記する必要がありました。 自動化計画フェーズで、Abhay がこれにかかる時間を測定し、従業員の銀行の詳細を調べるのに 3 分、オンライン バンキングの Web サイトから申請者に払い戻すのにさらに 5 分かかることを記録したとします。

フロー実行分析に基づいて、Abhay は自動化が 1 日に 91～110 回、平均 107 回実行されたことを確認できます。

![フロー実行の傾向グラフ](media/flow-run-trends.png "フロー実行の傾向グラフ")

得られた[自動化の期間](#get-the-flow-run-duration) は平均 40 秒でした。 したがって、実行ごとに短縮される時間は次のとおりです。

&nbsp;&nbsp;&nbsp;自動化前の時間 (3 分 &plus; 5 分) &minus; 自動化後の時間 (40 秒) = 440 秒

![自動化前後の比較](media/before-after-automation.png "自動化前後の比較")

自動化は 30 日間で 3,226 回実行されたため、節約された合計時間は次のとおりです。

&nbsp;&nbsp;&nbsp;短縮時間 (440 秒) &times; 実行回数 (3,226 回) = 1,419,440 秒 = 394.28 時間

> [!div class="nextstepaction"]
> [次のステップ : パフォーマンス問題の診断](discover-performance-issues.md)