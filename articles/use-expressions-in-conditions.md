---
title: 条件のある式を使用します。  | Microsoft Docs
description: Power Automate の条件で、"and"、"or"、"empty"、"less"、"greater" などの高度な式を使用します。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/15/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9796bfad4bd5e34e418217cd6cb1740ca1dfce8e
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4710216"
---
# <a name="use-expressions-in-conditions-to-check-multiple-values"></a>複数の値を確認する条件で式を使用する

このチュートリアルでは、式と **条件** を使用し、**詳細モード** で複数の値を比較する方法を説明します。

クラウド フローを作成するとき、基本モードで [**条件**](add-condition.md#add-a-condition) カードを使用し、単一の値を別の値と簡単に比較できます。 ただし、複数の値を比較しなければならない場面もあります。 たとえば、スプレッドシートまたはデータベース テーブルのいくつかの列の値を確認する場合です。

条件では、次の論理式をあらゆる組み合わせで使用できます。

Expression|内容|例
--------|-----------|-------
|[および](#use-the-and-expression)|2 つの引数を受け取り、両方の値が true の場合は true を返します。<br><b>注</b>: 両方の引数をブール値にする必要があります。|次の式は、false を返します。 <br>and(greater(1,10),equals(0,0))
|[または](#use-the-or-expression)|2 つの引数を受け取り、どちらかの引数が true の場合は true を返します。 <br><b>注</b>: 両方の引数をブール値にする必要があります。|次の式は、true を返します。<br>or(greater(1,10),equals(0,0))
|等しい|2 つの値が等しい場合に true を返します。|たとえば、parameter1 が someValue のとき、次の式は true を返します。<br>equals(parameters('parameter1'), 'someValue')
|[表示を減らす](#use-the-less-expression)|2 つの引数を受け取り、最初の引数が 2 番目の引数よりも小さい場合、true を返します。 <br><b>注</b>: サポートされている型は整数、浮動小数点数、文字列です。|次の式は、true を返します。<br>less(10,100)
|lessOrEquals|2 つの引数を受け取り、最初の引数が 2 番目の引数よりも小さい、または等しい場合は true を返します。 <br><b>注</b>: サポートされている型は整数、浮動小数点数、文字列です。|次の式は、true を返します。<br>lessOrEquals(10,10)
|[より大きい](#use-the-greater-expression)|2 つの引数を受け取り、最初の引数が 2 番目の引数よりも大きい場合は true を返します。 <br><b>注</b>: サポートされている型は整数、浮動小数点数、文字列です。|次の式は、false を返します。<br>greater(10,10)
|greaterOrEquals|2 つの引数を受け取り、最初の引数が 2 番目の引数よりも大きい、または等しい場合は true を返します。 <br><b>注</b>: サポートされている型は整数、浮動小数点数、文字列です。|次の式は、false を返します。<br>greaterOrEquals(10,100)
|[空](#use-the-empty-expression)|オブジェクト、配列、文字列が空の場合は true を返します。|次の式は、true を返します。<br>空 ('')
|等しくない|逆のブール値を返します。 |次の式は、true を返します。<br>not(contains('200 Success','Fail'))
|if|式の結果が true か false の場合、特定の値を返します。|次の式は、「yes」を返します。<br>if(equals(1, 1), 'yes', 'no')

## <a name="prerequisites"></a>前提条件
* Power Automate へのアクセス。
* テーブルを含むスプレッドシートはこのチュートリアルで後ほど説明します。 Power Automate でアクセスできるように、Dropbox や Microsoft OneDrive などの場所にスプレッドシートを保存してください。
* Microsoft Office 365 Outlook (Office 365 Outlook を使用するとき、サポートされているあらゆる電子メール サービスをフローで利用できます。)

## <a name="use-the-or-expression"></a>or 式を使用する
項目の値が valueA **または** valueB の場合にアクションを行うワークフローがあります。 たとえば、スプレッドシート テーブルのタスクの状態を追跡します。 テーブルに *状態* という名前の列があり、*状態* 列の指定できる値は次のとおりです。

* **完了済み**
* **ブロック済み**
* **不要**
* **開始前**

スプレッドシートは、たとえば、次のようになります。

![サンプル スプレッドシート](./media/use-expressions-in-conditions/spreadsheet-table.png)

先のスプレッドシートの場合、Power Automate を利用し、たとえば、*状態* 列が *完了済み* または *不要* に設定されているすべての行を削除します。

フローを作成してみましょう。

### <a name="start-with-a-blank-flow"></a>空のフローから始める
1. [Power Automate](https://flow.microsoft.com) にサインインする。

    ![サインインする](includes/media/modern-approvals/sign-in.png)
2. **マイ フロー** タブを選択します。

    ![マイ フローを選択](includes/media/modern-approvals/select-my-flows.png)
3. **一から作成** を選択します。

    ![一から作成](includes/media/modern-approvals/blank-template.png)

### <a name="add-a-trigger-to-your-flow"></a>トリガーをフローに追加する
1. **スケジュール** を検索し、**スケジュール - 繰り返し** トリガーを選択します

    ![スケジュール トリガー](includes/media/schedule-trigger/schedule-trigger.png)
2. 1 日に 1 回実行するようにスケジュールを設定します。

    ![スケジュールの設定](includes/media/schedule-trigger/set-schedule.png)

### <a name="select-the-spreadsheet-and-get-all-rows"></a>スプレッドシートを選択し、すべての行を取得する
1. **新しいステップ** > **アクションの追加** を選択します。

    ![新しいステップ](includes/media/new-step/action.png)
2. **行** を検索し、**Excel - 行の取得** を選択します。

    注: 使用しているスプレッドシートに対応する「行の取得」アクションを選択します。 たとえば、Google スプレッドシートを使用している場合、**Google スプレッドシート - 行の取得** を選択します。

    ![行の取得](includes/media/new-step/get-excel-rows.png)
3. **ファイル名** ボックスのフォルダー アイコンを選択し、参照し、データが含まれるスプレッドシートを検索して選択します。

    ![スプレッドシートを選択する](includes/media/new-step/select-spreadsheet.png)
4. **テーブル名** の一覧からデータを含むテーブルを選択します。

    ![テーブルの選択](includes/media/new-step/select-table.png)

### <a name="check-the-status-column-of-each-row"></a>各行の状態列を確認する
1. **新しい手順** > **その他** > **それぞれへの適用の追加** の順に選択します。

    ![テーブルの選択](includes/media/new-step/apply-to-each.png)
2. **値** トークンを **前の手順から出力を選択** ボックスに追加します。

    ![テーブルの選択](includes/media/apply-to-each/add-value-token.png)
3. **条件の追加** > **詳細モードで編集** の順に選択します。
4. 次の **or** 式を追加します。 この **or** 式はテーブル内の各行の値を確認します (式内でアクセスされるとき、行は項目として認識されます)。 **状態** 列の値が *完了済み***または***不要* の場合、**or** 式は「true」として評価します。

    **or** 式は次のように表示されます。

    ````@or(equals(item()?['status'], 'unnecessary'), equals(item()?['status'], 'completed'))````

    **条件** カードは次のイメージに似ています。

    ![or 式のイメージ](./media/use-expressions-in-conditions/or-expression.png)

### <a name="delete-matching-rows-from-the-spreadsheet"></a>一致する行をスプレッドシートから削除する
1. 条件の **IF YES, DO NOTHING** 分岐で **アクションの追加** を選択します。
2. **行の削除** を検索し、**Excel - 行の削除** を選択します。

    ![行の削除のイメージ](includes/media/new-step/select-delete-excel-row.png)
3. **ファイル名** ボックスで、削除するデータが含まれるスプレッドシート ファイルを検索し、選択します。
4. **テーブル名** 一覧で、データを含むテーブルを選択します。
5. **行 ID** トークンを **行 ID** ボックスに配置します。

    ![スプレッドシート ファイル](includes/media/new-step/delete-excel-row.png)

### <a name="name-the-flow-and-save-it"></a>フローに名前を付け、保存する
1. フローに名前を付け、**フローの作成** ボタンを選択します。

    ![フローを保存する](./media/use-expressions-in-conditions/name-and-save.png)

### <a name="run-the-flow-with-the-or-expression"></a>or 式を含むフローを実行する
保存後、フローが実行されます。 このチュートリアルの前半で説明したスプレッドシートを作成すると、そのスプレッドシートは実行後、次のようになります。

![or 式が完了する](./media/use-expressions-in-conditions/spreadsheet-table-after-or-expression-runs.png)

状態列が「完了済み」または「不要」の行からすべてのデータが削除されています。

## <a name="use-the-and-expression"></a>and 式を使用する
2 つの列を含むスプレッドシート テーブルがあると仮定します。 列の名前は状態と割り当て済みです。 また、状態列の値が「ブロック済み」で、割り当て済み列の値が「John Wonder」の場合、すべての行を削除するとします。  このタスクを実現するには、このチュートリアルの前述のすべての手順に従います。ただし、詳細モードで **条件** カードを編集する場合は、以下の **and** 式を使用します。

````@and(equals(item()?['Status'], 'blocked'), equals(item()?['Assigned'], 'John Wonder'))````

**条件** カードは次のイメージに似ています。

![and 式のイメージ](./media/use-expressions-in-conditions/and-expression.png)

### <a name="run-the-flow-with-the-and-expression"></a>and 式を含むフローを実行する
ここまで実行していれば、スプレッドシートは次のイメージのようになります。

![and 実行前](./media/use-expressions-in-conditions/spreadsheet-table-before-and-expression-runs.png)

フローの実行後、スプレッドシートは次のイメージのようになります。

![and 実行後](./media/use-expressions-in-conditions/spreadsheet-table-after-and-expression-runs.png)

## <a name="use-the-empty-expression"></a>empty 式を使用する
スプレッドシートに空の行があることに注目してください。 空の行を削除するには、**empty** 式を使用し、割り当て済み列と状態列にテキストが入っていないすべての行を特定します。

このタスクを実行するには、このチュートリアルで前述した **and 式を使用する** セクションのすべての手順を実行します。ただし、詳細モードで **条件** カードを編集するとき、次の empty 式を使用します。

````@and(empty(item()?['Status']), empty(item()?['Assigned']))````

**条件** カードは次のイメージに似ています。

![empty 式のイメージ](./media/use-expressions-in-conditions/empty-expression.png)

フローの実行後、スプレッドシートは次のイメージのようになります。

![empty 実行後](./media/use-expressions-in-conditions/spreadsheet-table-after-empty-expression-runs.png)

余分な行がテーブルから削除されていることにご注意ください。

## <a name="use-the-greater-expression"></a>greater 式を使用する
同僚のために野球のチケットを購入し、スプレッドシートを使用して同僚からの返済を確認するとします。 全額を支払っていない同僚にメールを毎日送信するクラウド フローをすばやく作成できます。

**greater** 式を使用し、全額を支払っていない従業員を特定します。 全額を支払っていない従業員には催促メールを自動送信できます。

このスプレッドシートは次のようになります。

![スプレッドシートのイメージ](./media/use-expressions-in-conditions/tickets-spreadsheet-table.png)

**greater** 式が実装されていますが、これにより支払額が全額に達していないすべての従業員が特定されます。

````@greater(item()?['Due'], item()?['Paid'])````

## <a name="use-the-less-expression"></a>less 式を使用する
同僚のために野球のチケットを購入し、スプレッドシートを利用して同僚からの返済を確認するとします。返済は各同僚が同意した日付までとします。 支払期日到達まで 1 日未満になっても全額支払いが完了していない同僚にアラーム メールを送信するクラウド フローを作成できます。

**and** 式と **less** 式を併用します。評価する条件が 2 つあるためです。


|          検証する条件          | 使用する式 |                    例                     |
|-----------------------------------------|-------------------|------------------------------------------------|
|   全額が支払われましたか?    |      より大きい      |   @greater(item()?['Due'], item()?['Paid'])    |
| 期日到達まで 1 日未満になっていますか? |       表示を減らす        | @less(item()?['DueDate'], addDays(utcNow(),1)) |

## <a name="combine-the-greater-and-less-expressions-in-an-and-expression"></a>and 式の中で greater 式と less 式を組み合わせます
**greater** 式を使用し、全額を支払っていない従業員を特定します。**less** 式を使用し、期日到達まで 1 日未満になっているか確認します。 次に、**メールの送信** アクションを使用し、期日到達まで 1 日未満になっても全額を支払っていない従業員に催促のメールを送信します。

このスプレッドシート テーブルは次のようになります。

![スプレッドシートのイメージ](./media/use-expressions-in-conditions/spreadsheet-table-due-date.png)

**and** 式が実装されていますが、それにより期日到達まで 1 日未満になっても全額を支払っていないすべての従業員が特定されます。

````@and(greater(item()?['Due'], item()?['Paid']), less(item()?['dueDate'], addDays(utcNow(),1)))````

## <a name="use-functions-in-expressions"></a>式で関数を使用する

いくつかの式は、クラウド フローの実行が開始するときにまだ存在していない可能性があるランタイム アクションから値を取得します。 式でこれらの値を参照したり使用したりするには、ワークフロー定義言語で提供される関数を使用します。 詳細: [Power Automate でのワークフロー定義言語の関数リファレンス](https://docs.microsoft.com/azure/logic-apps/workflow-definition-language-functions-reference)
