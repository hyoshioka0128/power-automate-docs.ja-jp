---
title: クラシック Common Data Service ワークフローを Power Automate に置き換える | Microsoft Docs
description: クラシック ワークフローではなく、フローを使用するための Power Automate の機能と推奨されるパターンについて説明します。
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
ms.service: flow
ms.topic: article
ms.date: 08/27/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c4be61dfafa17c3808eb497aa9ed7d1bcaaecbab
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74373667"
---
# <a name="replace-classic-common-data-service-workflows-with-flows"></a>クラシック Common Data Service ワークフローをフローに置き換える
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

このトピックでは、Power Automate の機能をクラシック ワークフローと比較します。

Power Automate には、クラシック ワークフロー モデルよりも大きな利点があります。クラシック ワークフローではなく、プロセスを自動化するための Power Automate の使用を検討してください。 

新しい自動化プロセスを構築するために、クラシック Common Data Service ワークフローではなくフローを作成します。 また、既存のクラシック ワークフロー プロセスを確認し、それらをフローに置き換えることを検討する必要があります。

## <a name="feature-capability-comparison"></a>機能の性能比較

この表は、Power Automate とクラシック ワークフローの機能の比較についてまとめたものです。 

*クラシック ワークフローの機能と同等およびさらに優れた新機能が、Power Automate に継続的に追加されています。この表の情報は、Power Automate の機能が追加されるたびに更新されるため、随時確認してください。クラシック ワークフローをフローに置き換えるのに役立つ、今後のフロー機能の詳細については、2019 年 4 月版リリース ノートの [Power Automate の新機能と予定されている機能](https://docs.microsoft.com/business-applications-release-notes/April19/microsoft-flow/planned-features)に関するページを参照してください。*

<table>
<tr>
<th colspan="2">機能</th>
<th>Power Automate</th>
<th>クラシック ワークフロー</th>
</tr>
<tr>
<td rowspan="5">モデリング</td>
<td>条件分岐</td>
<td>はい</td>
<td>
                    
   はい
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   ループ
                    
                </td>
                <td>
                    
   はい
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   フィールドの待機条件
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
                <td>
                    
   はい
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   並列分岐
                    
                </td>
                <td>
                    
   はい
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   外部システムへの既定のコネクタ (外部サービスでのアクションのトリガーと実行)
                    
                </td>
                <td>
                    
   はい
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   構成
                    
                </td>
                <td>
                    
   動的コンテンツ
                    
                </td>
                <td>
                    
   はい
                    
                </td>
                <td>
                    
   はい
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   イベント データのプレイメージへのアクセス
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
                <td>
                    
   はい
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   子ワークフローの実行
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
                <td>
                    
   はい
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Common Data Service アクション (カスタムを含む) の実行
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
                <td>
                    
   はい
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   カスタム ワークフロー アクティビティの実行
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
                <td>
                    
   はい
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   トランザクションで実行する手順のグループ化
                    
                </td>
                <td>
                    
   はい (変更セット)
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   承認ワークフロー
                    
                </td>
                <td>
                    
   はい
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   実行
                    
                </td>
                <td>
                    
   フィールド変更でのトリガー
                    
                </td>
                <td>
                    
   はい
                    
                </td>
                <td>
                    
   はい
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   フィールド値 (日付フィールドの特定の日付など) での条件付きトリガー
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   複数の Common Data Service エンティティ イベントでのトリガー
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
                <td>
                    
   はい
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   オンデマンドでの実行
                    
                </td>
                <td>
                    
   はい
                    
                </td>
                <td>
                    
   はい
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   実行スコープ    <br/>
   (組織、事業単位、ユーザーなど)
                    
                </td>
                <td>
                    
   はい
                    
                </td>
                <td>
                    
   はい
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   スケジュールに従って実行
                    
                </td>
                <td>
                    
   はい
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   同期実行 (リアルタイム)
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
                <td>
                    
   はい
                    
                </td>
            </tr>
            <tr>
                <td rowspan="2">
                    
   履歴
                    
                </td>
                <td>
                    
   監査
                    
                </td>
                <td>
                    
   はい
                    
                </td>
                <td>
                    
   はい
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   分析の実行
                    
                </td>
                <td>
                    
   はい
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
            </tr>
            <tr>
                <td rowspan="3">
                    
   作成と移植性
                    
                </td>
                <td>
                    
   ソリューションのサポート
                    
                </td>
                <td>
                    
   はい
                    
                </td>
                <td>
                    
   はい
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   モダン デザイナー
                    
                </td>
                <td>
                    
   はい
                    
                </td>
                <td>
                    
   いいえ
                    
                </td>
            </tr>
            <tr>
<td>AI 支援による作成</td>
<td>はい</td>
<td>いいえ</td>
</tr>
</table>

## <a name="example-scenario-replace-workflow-with-a-flow"></a>シナリオ例: ワークフローをフローに置き換える

顧客の見積書はまとめており、現在、顧客に見積書を送信する前に、管理チームからの承認を要求する必要がある販売シナリオを想像してください。 クラシック ワークフローでは、これを簡単に行うことができず、これに対するほとんどのソリューションでは、開発者がカスタム ワークフロー アクティビティを記述して、見積品目を取得する必要があります。

フローでは、この構築はより簡単になります。このシナリオをサポートするためのいくつかの Power Automate 機能については、チュートリアルの後半で説明します。 これには、以下のことが含まれます。

-   オンデマンドで実行するフローの作成

-   Common Data Service エンティティに関連するレコードのリストの取得

-   レコードのリストでのループ

-   承認要求の送信

販売員がオンデマンドで承認要求をトリガーできるようにするには、次のようにします。

1. [Power Automate](https://flow.microsoft.com/) にサインインし、ソリューションにフローを作成します。 詳細については、「[ソリューションにフローを作成する](create-flow-solution.md)」を参照してください。 

1. トリガーのリストから、**Common Data Service (現在の環境) – [レコードが選択されたとき]** を選び、エンティティとして **[見積もり]** を選択します。 このトリガーを使用すると、レコードまたはレコード リストに対してオンデマンドでフローを実行できます。

1. トリガーが構成されたら、フローで実行するアクションを追加します。 これにより、見積品目と値を識別するために必要な集計の詳細が承認者に提供されます。 まず、**Common Data Service (現在の環境) - [レコードの一覧表示]** アクションを追加します。 見積もりから個々の品目を取得する必要があるため、エンティティを **[見積依頼明細行]** に設定します。 フローがトリガーされた見積もりに属する見積品目のみを確実にリストするには、OData スタイル フィルター条件を指定します。 **[フィルター クエリ]** フィールドに「*\_quoteid_value eq*」と入力し、表示される動的な値のリストから *[見積もり]* を選択します。

    ![フローを定義する](media/define-flow-1.png "フローを定義する")

1. 承認のために見積品目をまとめる必要があるため、**[変数を初期化する]** アクションを追加します。 **[名前]** フィールドを *[Quote line summary]\(見積品目の集計\)* に、**[種類]** を (ドロップダウンから) [文字列] に設定して、**[値]** フィールドは空のままにします。

1. **[文字列変数に追加]** アクションを追加し、先ほど作成した *[Quote line summary]\(見積品目の集計\)* を選択します。 **[値]** フィールドで、動的な値のリストから *[数量]、[名前]、[単位あたりの価格]、[小計] および [Manual amount]\(手動額\)* を選択します。 Power Automate デザイナーにより、これらの値が見積品目リストからのものであることが識別され、**[個々に適用]** ループにこのアクションが追加され、各品目の情報がこの集計に確実に追加されるようになります。

    ![フローを定義する](media/define-flow-2.png "フローを定義する")

1. 作成した見積もりの集計に対する承認を要求するには、**[承認 – 承認の開始と待機]** アクションを追加します。 承認の種類 (たとえば、[承認/拒否 – 最初に応答]) を選択し、承認要求に**タイトル** (たとえば、動的な値のリストから選択された、承認が要求されている見積もりの名前) を付け、**[割り当て先]** フィールドで見積もりを確認し、承認する必要がある人のメール アドレスを入力します。 詳細フィールドで、*[Quote line summary]\(見積品目の集計\)* 変数を、動的な値のピッカーを使用して関連する可能性のあるその他の情報 (合計金額など) と共に追加します。

1. 承認が受理または拒否された場合の動作を決定するには、**[条件]** アクションを追加します。 条件の最初のフィールドの動的な値リストから *[結果]* を選択し、2 番目のフィールドのドロップダウンから *[が次の値を含む]* を選んで、条件の 3 番目のフィールドに「*受理*」と入力します。 最後に、承認の結果に基づいてアクション (通知メールの送信など) を追加します。

    ![フローを定義する](media/define-flow-3.png "フローを定義する")

これで承認の構造が作成されたので、承認者は次の手順について決定するために必要なすべての情報を得られました。 承認を要求するオンデマンド フローの完全な例を以下に示します。

![承認フローの構造](media/approval-flow-structure.png "承認フローの構造")

このフローを見積もりに対して実行すると、その見積もりの見積品目が集計され、Power Automate から承認者が応答できる承認要求、または受信されるアクション可能なメールが送信されます。 表示例を以下に示します。

![実行中のフロー](media/flow-in-action.png "実行中のフロー")

## <a name="recommended-patterns"></a>推奨されるパターン


-   **複雑な else-if 条件付きロジックを使用するワークフロー**  
    
    条件を使用するのではなく、代わりに[スイッチ アクション](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-switch-statement#add-switch-statement)を使用することをお勧めします。

-   **プラグイン/コードから実行するワークフロー**  
    
    トリガーから開始するようにフローを再設計することをお勧めします。

    -   Common Data Service トリガーを使用して、その中のイベントに基づいてフローを実行します。

    -   外部サービスのイベントに基づいてフローを実行するには、260 を超える既定のコネクタを利用します。

    -   必要なコネクタがすぐに利用できないシナリオの場合は、独自のカスタム コネクタを簡単に作成します ([カスタム コネクタの作成](https://docs.microsoft.com/connectors/custom-connectors/define-blank)に関するページを参照)。

    -   最後に、Common Data Service コネクタ (既定のコネクタの 1 つ) を使用してフローをトリガーできない、あるいはカスタム コネクタを作成できないシナリオがある場合は、[[HTTP 要求の受信時] トリガー](https://docs.microsoft.com/azure/connectors/connectors-native-reqres#use-the-http-request-trigger)を利用して、フローを呼び出すようにします。

-   **再帰的に実行されるワークフロー**  
    
    [do-until](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) ループ、または代わりにフローの[個々に適用](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#foreach-loop)ループを使用します。

-   **レコードのリストを必要とするワークフロー**  
    
    **[レコードの一覧表示]** アクションを使用します。 このアクションを使用する場合は、取得するレコードの数を最小限に抑えてアクションを最適化するために、OData 構文を使用してレコードのフィルター条件を定義します。

-   **スケジュールに基づいて実行されるようにスリープするワークフロー**  
    
    定期的にビジネス ロジックを実行するには、**繰り返し**トリガーを使用します。

-   **1 つのトランザクションでアクティビティが実行されたことを確認するために実行が管理されたワークフロー**  
    
    [変更セット アクション](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/automated-flows-support-change-sets-common-data-service)を使用して、その中のすべてのアクションが 1 つのアトミック単位として実行されるようにします。その場合、すべて成功するか、グループとして失敗します。 変更セット内のいずれかのアクションが失敗した場合、完了した操作によって行われた変更がロールバックされます。

-   **失敗したワークフローの実行を監視する**  
    
    Power Automate で、アクションに対して **run-after 設定**を使用し、前のアクションが失敗したときに実行するように構成します。 たとえば、**レコードの更新**アクションが失敗したとき、またはタイムアウトになったときに、Power Automate モバイルに通知を送信します。

## <a name="faqs"></a>FAQ


-   **Dynamics 365 ライセンスがあります。Power Automate を使用することはできますか?**

    すべての Dynamics 365 ユーザーに、Power Automate を使用する権利があります。 <https://flow.microsoft.com/pricing/> でライセンス情報を確認してください。

-   **フローはどのくらいの頻度でトリガーできますか?**

    -   Dynamics 365 (または Common Data Service) のフローは、Webhook を使用する(ポーリングを必要としない) ため、トリガー後にほぼリアルタイムで実行されます

    -   直接 API アクセスと同様に、システムにはスロットル/制限があります。詳細については、こちら (<https://docs.microsoft.com/flow/limits-and-config>) を参照してください

    -   具体的には、フローごとに、5 分あたりのアクション数は 10 万に制限されており、フロー内の 1 つのループで一度に 10 万を超える項目を処理することはできません

    -   5 分あたり最大 6 GB のスループット

-   **1 つのフローはどれくらいの時間実行できますか?**  
    
    1 つのフローの実行は 30 日後にタイムアウトになります。

-   **環境間でフローを移動するにはどうすればよいですか?**  
    
    クラシック ワークフローと同じように、ソリューションにフローを作成し、プロセスの完全なアプリケーション ライフサイクルをサポートすることができます。

-   **Power Automate の依存関係は Common Data Service で追跡されますか?**  
    
    ソリューション内の他のコンポーネントと同様に、ソリューション内のフローのすべての依存関係は Common Data Service で追跡されます。

-   **同期ワークフローについてはどうですか?** 
 
    同期ワークフローの必要性を再評価し、フローを使用して、ワークフローの目標、または一部を構築できるかどうかを判断する必要があります。 具体的には、同期ワークフローが、全体的なエンド ユーザーのパフォーマンス エクスペリエンスの低下の大きな原因であることが、テレメトリから確認できます。 しかし、多くの用途で、これらのアクションを非同期として分割することをお勧めします。これにより、Power Automate で引き続きアクションを確実に完了しながら、ユーザーはアクティビティを続けることができます。

-   **Power Automate を使用すると、データはリージョン (つまり、Dynamics 365 または Common Data Service 環境と同じリージョン) 内にとどまりますか?**  
    
    はい。Power Automate では常に、Common Data Service と同じリージョンが使用されます。

-   **プロキシ/ファイアウォールの変更を行う必要がありますか?**  
    
    プロキシ/ファイアウォールの変更を行う必要があるかどうかを判断する場合は、[IP アドレス構成のリファレンス](limits-and-config.md#ip-address-configuration)に関する記述を参照してください。