---
title: データのフィルター処理とコピー | Microsoft Docs
description: Power Automate を使用して、データをフィルターし、ソースからターゲットにコピーする方法を学習します
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: dfc07db3386f733696418c23814a662eb36787d6
ms.sourcegitcommit: 62c8891c497823be6e7691410072011d7cfc5339
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2020
ms.locfileid: "3652882"
---
# <a name="filter-and-copy-data-with-power-automate"></a>Power Automate を使用してデータのフィルターとコピーをする

このチュートリアルでは、新しい項目または変更された項目のソースを監視し、それらの変更をターゲットにコピーするフローを作成する方法を説明しています。 ユーザーがある場所でデータを入力しているが、チームが別の場所や形式でデータを必要としている場合は、このようなフローを作成することができます。

このチュートリアルで Microsoft SharePoint [リスト](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) (ソース) から [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview) テーブル (ターゲット) にデータをコピーする場合、Power Automate でサポートされる [380 のコネクター](https://flow.microsoft.com/connectors/) 以上のサービスのどのサービス間でもデータをコピーできます。

> [!IMPORTANT]
> 双方向の同期には対応していないため、ターゲットで行われた変更内容はソースにコピーされません。 双方向の同期を設定する場合は、ソースとターゲット間で変更内容が無限に送信される無限ループが発生します。
> 
> 

## <a name="prerequisites"></a>前提条件
* データ ソースとターゲットへのアクセス権があること。 このチュートリアルには、ソースとターゲットの作成ステップは含まれていません。
* [Power Automate](https://flow.microsoft.com) へのアクセス
* データの格納方法の基本を理解していること。
* フロー作成の基本を十分に理解していること。 [アクション、トリガー](multi-step-logic-flow.md#add-another-action)、および[条件](add-condition.md)の追加方法を確認することができます。 次のステップでは、これらアクションの実行方法を理解すていることが前提となります。

> [!TIP]
> ソースとターゲット内の列名がすべて一致している必要はありませんが、項目の挿入または更新する際にはすべての*必須*列にデータを指定する必要があります。 必須のフィールドは、Power Automate によって自動的に識別されます。
> 
> 

## <a name="quick-overview-of-the-steps"></a>各ステップについての簡単な概要
Power Automate を使い慣れている場合は、以下の簡単な手順を使用してデータ ソースから別の場所にデータをコピーできます：

1. 監視するソースと、変更データのコピー先を特定します。 両方にアクセスできることを確認します。
2. ソースとターゲット内の項目を一意に識別する少なくとも1 つ以上の列を特定します。 次の例では、**タイトル**列を使用していますが、実際は任意の列 (複数可) を使用することができます。
3. ソースの変更を監視するトリガーを設定します。
4. ターゲットを検索し、変更された項目が存在するかどうかを判断します。
5. **条件**は次のように使用します :
   * 新しい項目または変更された項目がターゲットに存在しない場合は、作成してください。
   * 新しい項目または変更された項目がターゲットに存在する場合は、更新します。
6. フローをトリガーし、新しい項目または変更された項目がソースからターゲットにコピーされていることを確認します。

> [!NOTE]
> SharePoint または Azure SQL Database への接続をまだ作成していない場合、サインインを求められたら、表示される指示に従ってください。
> 
> 

フローの詳しい作成ステップを以下に示します。

## <a name="monitor-the-source-for-changes"></a>ソースの変更を監視する
1. [Power Automate](https://flow.microsoft.com) にサイン インし、**マイ フロー** > **ゼロから作成する** を選択します。
2. **SharePoint** を検索し、トリガーのリストから  **SharePoint  - 項目が作成または変更されたとき** トリガーを選択します。
3. **サイト アドレス**を入力し、続いて**項目が作成、または修正されたとき**カードで**リスト名** を選択します。
   
    フローで新しい項目または更新された項目の監視に使用する、SharePoint リストの **サイト アドレス** と **リスト名** を指定します。
   
    ![SharePoint のトリガーを構成する](media/odata-filters/configure-sharepoint-trigger.png)

## <a name="search-the-destination-for-the-new-or-changed-item"></a>ターゲットで新しい項目、または変更された項目を検索する
ここでは、**SQL Server - 行の取得**アクションを使用して、ターゲットで新しい項目、または変更された項目を検索します。

1. **新しいステップ** > **アクションの追加** を選択します。
2. **行の取得** を検索し、**SQL Server - 行の取得** を選択します。続いて**テーブル名**リストから監視するテーブルを選択します。
3. **詳細オプションの表示** を選択します。
4. **フィルター クエリ**ボックスに **Title eq '** と入力します。動的コンテンツ リストから**タイトル**トークンを選択し、 **'** と入力します。
   
    前述のステップでは、ソースとターゲットで行のタイトルが一致していることを前提としています。
   
    **行の取得** カードは次の図のようになります :
   
    ![ターゲット データベースから項目を取得する](media/odata-filters/configure-sql-get-rows-action.png)

## <a name="check-if-the-new-or-changed-item-was-found"></a>新しい項目、または変更された項目が検出されたかどうかを確認する
**新しいステップ** > **条件の追加**を選択して、**条件**カードを開きます。

条件カードで、次のように指定します :

1. 左側のボックスを選択します。
   
    **このフローで使用されるアプリやコネクタから動的コンテンツを追加する** リストが開きます。
2. **行の取得** カテゴリから **値** を選択します。
   
   > [!TIP]
   > **行の取得** カテゴリから**値**が選択されたことを確認します。 **項目が作成、または変更されたとき**カテゴリからは**値**を選択しないでください。
   > 
   > 
3. 中央のボックスのリストから **と等しい** を選択します。
4. 右側のボックスに **0** (ゼロ) を入力します。
   
    **条件**カードは次のイメージのようになります :
   
    ![条件を構成する](media/odata-filters/configure-condition.png)
5. **詳細モードで編集**を選択します。
   
    詳細モードが開くと、ボックスに **\@equals(body('Get_rows')?['value'], 0)** という式が表示されます。 **body('Get_items')?['value']** 関数の周りに **length()** を追加し、この式を編集します。 式全体は、次のようになります：**@equals(length(body('Get_rows')?['value']), 0)**
   
    **条件**カードは次のイメージのようになります :
   
    ![条件を構成する](media/odata-filters/configure-condition-add-length.png)
   
   > [!TIP]
   > **length()** 関数を追加することで、フローで**値**リストを確認し、そこに項目が含まれているかどうかを判別できます。
   > 
   > 

フローでターゲットから「項目」が取得された場合には、2つの結果が考えられます。

| 結果 | 次のステップ |
| --- | --- |
| 項目が存在する場合 |[項目を更新する](odata-filters.md#update-the-item-in-the-destination) |
| 項目が存在しない場合 |[新しい品目の作成](odata-filters.md#create-the-item-in-the-destination) |

> [!NOTE]
> これらのカードはフローで使用されている Azure SQL Database テーブルのカラム名を示しているため、次に表示されている**行の挿入**と**行の更新**のカードのイメージは、実際のものとは異なる場合があります。
> 
> 

## <a name="create-the-item-in-the-destination"></a>ターゲットで項目を作成する
ターゲットに項目が存在しない場合は、**SQL Server - 行の挿入**アクションを使用して作成してください。

**条件**の **該当する場合** 分岐では、次のようにします :

1. **アクションの追加** を選択し、**行の挿入**を検索して、**SQL Server - 行の挿入** を選択します。
   
    **行の挿入**カードが開きます。
2. **テーブル名** リストから、新しい項目を挿入するテーブルを選択します。
   
    **行の挿入**カードが展開され、選択したテーブルにすべてのフィールドが表示されます。 アスタリスク (*) の付いたフィールドは必須フィールドであり、行を有効にするためには設定する必要があります。
3. 設定する各フィールドを選択し、データを入力します。
   
    データを手動で入力することも、**動的コンテンツ**から 1 つ以上のトークンを選択することも、フィールドにテキストとトークンを組み合わせて入力することも可能です。
   
    **行の挿入**カードは次のイメージのようになります :
   
    ![条件を構成する](media/odata-filters/insert-row.png)

## <a name="update-the-item-in-the-destination"></a>ターゲットで項目を更新する
項目がターゲットに存在する場合は、その項目を変更して更新します。

1. **条件**の **該当しない場合** 分岐に **SQL Server - 行の更新**アクションを追加します。
2. このドキュメントの[項目の作成](odata-filters.md#create-the-item-in-the-destination) セクションのステップに従って、テーブルのフィールドを設定します。
   
    ![環境を表示する](media/odata-filters/update-row.png)
3. ページ上部の **フロー名**ボックスにフローの名前を入力し、**フローの作成**を選択して保存します。
   
    ![フローに名前を付ける](media/odata-filters/give-the-flow-a-name.png)

以上で、SharePoint リスト (ソース) の項目が変更された場合は常に、フローがトリガーされ、Azure SQL Database (ターゲット) で新しい項目が挿入されるか、既存の項目が更新されます。

> [!NOTE]
> ソースから項目が削除された場合、フローはトリガーされません。 これが重要なシナリオである場合は、項目が不要になったタイミングを示す別の列を追加することを検討してください。
> 
> 

## <a name="learn-more"></a>詳細はこちら
フローで[データ操作](data-operations.md)を使用します。

