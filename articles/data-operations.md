---
title: データ操作を理解する | Microsoft Docs
description: 作成、結合、選択、配列のフィルター処理、HTML テーブル作成、CSV テーブル作成など、Power Automate による操作の実行について説明します。
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/18/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 319cdf5d668cc0dde202138b7c501d1cee530ac1
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709039"
---
# <a name="use-data-operations-with-power-automate"></a>Power Automate でデータ操作を使用する

このチュートリアルでは、作成、結合、選択、配列のフィルター処理、テーブルの作成、JSON の解析など、フローの作成時にデータを操作するために使用する Power Automate の一般的なデータ操作を説明します。

## <a name="prerequisites"></a>前提条件

* Power Automate へのアクセス。
* [PostMan](https://www.getpostman.com/postman) のようなツールで、JSON 配列を使ってHTTP POST リクエストをフローに送信することができます。

## <a name="use-the-compose-action"></a>作成アクションを使用する

**データ操作 - 作成** を使用する <!--note from editor: Here and throughout, you don't need to repeat the name of the action. The name in the UI isn't confusing, but these parenthetical phrases kind of are. Edits to the rest of this sentence are suggested.-->クラウド フローを設計するときに同じデータを複数回入力する必要がないようにするためのアクション。 この例では、フローの設計時に数値の配列 (`[0,1,2,3,4,5,6,7,8,9]`) を何度も入力する必要があります。 次の手順で説明するように、[作成] アクションを使用して配列を保存できます。

1. **作成** を検索し、**データ操作 - 作成** アクションを選択します。

    ![作成アクションを検索して、選択します](./media/data-operations/search-select-compose-2.png)

2. **入力** ボックスに今後参照する配列を入力します。

    ![作成アクションの構成](./media/data-operations/add-array-compose-2.png)

> [!TIP]
> カードのタイトル バーでテキスト **作成** を選択して覚えやすい名前を入力し、名前を変更して **作成** カードを後で見つけやすくします。

作成アクションのコンテンツにアクセスする場合は、次の手順に従います。

1. **データ操作 – 結合** などのアクションを追加します。

1. 作成アクションで保存した内容を追加したいコントロールを選択します。

   **このフローで使用するアプリやコネクタから動的なコンテンツを追加する** 画面が開きます。

1. **動的コンテンツ** タブの **作成** セクションで **出力** を選択します。

    ![作成アクションの出力を使用する](./media/data-operations/use-compose-output-2.png)

## <a name="use-the-join-action"></a>結合アクションを使用する

**データ操作 - 結合** アクションを使用して、選択した区切り記号で配列を区切ります。 たとえば、フローがメール アドレスの配列 `["d@example.com", "k@example.com", "dal@example.com"]` を含む Web 要求を受け取ります。 ただし、電子メール プログラムは、メール アドレスをセミコロンで区切った単一の文字列形式にする必要があります。 次の手順に従って **データ操作 - 結合** アクションを使用し、コンマ区切り文字 (,) をセミコロン (;) に変更します。

1. 新しいアクションを追加して **結合** を検索し、**データ操作 - 結合** を選択します。

    ![結合アクションを検索して選択する](./media/data-operations/search-select-join-2.png)

2. **From** ボックスに配列を入力して、**Join with** ボックスにセミコロン (**;**) を入力します。

    ![結合アクションを構成する](./media/data-operations/add-array-join-2.png)

3. フローを保存して実行する

4. フローの実行後、次の図に示すように **データ操作 – 結合** アクションの出力が、メール アドレスをセミコロンで結合した文字列になります。

    ![コンマ区切りメール アドレスの入力、セミコロン値で結合、セミコロン区切りメール アドレスの出力](./media/data-operations/join-output-2.png)

## <a name="use-the-select-action"></a>選択アクションを使用する

**データ操作 - 選択** アクションを使用して、配列内のオブジェクトの形状を変換します。 たとえば、配列内の各オブジェクトの要素を追加、削除、名前変更できます。

> [!NOTE]
> しかし、選択アクションで要素を追加や削除できますが、配列内のオブジェクト数は変更できません。

この例では、データは次の形式の Web 要求を介してフローに入ります。

``` JSON
[ { "first": "Eugenia", "last": "Lopez" }, { "first": "Elizabeth", "last": "Moore" } ]
```

`first` を `FirstName` に、`last` を `FamilyName` に名前を変更し、`first` と `last` (スペース区切り) を組み合わせた名前 `FullName` の新しいメンバーを追加して、受信データの形状を変更します。

``` JSON
[ { "FirstName": "Eugenia", "FamilyName": "Lopez", "FullName": "Eugenia Lopez" }, { "FirstName": "Elizabeth", "FamilyName": "Moore", "FullName": "Elizabeth Moore" } ]
```

実行手順:

1. **HTTP 要求の受信時** トリガーをフローに追加します。

2. **サンプル ペイロードを使用してスキーマを生成する** を選択します。

   ![サンプル ペイロードを選択する](./media/data-operations/request-trigger.png)

3. ボックスが表示されたら、ソース データ配列のサンプルを貼り付けて **完了** を選択します。

4. **データ操作 - 選択** アクションを追加して、次の画像のように構成します。

   :::image type="complex" source="./media/data-operations/select-card-2.png" alt-text="選択アクションの構成":::
   選択アクションを示すスクリーンショット。 From を Body に設定します。 マップ セクションで、FirstName を first、FamilyName を last、FullName を first と last に、スペース区切りで設定しています。:::image-end:::

   > [!TIP]
   > 選択アクションの結果は、新しくシェイプされたオブジェクトを含む配列となります。 次にこの配列を前述の作成アクションなど、他のアクションで使用できます。

## <a name="use-the-filter-array-action"></a>フィルタ配列アクションを使用する

**データ操作 - 配列のフィルター処理** アクションを使用して、配列内のオブジェクト数を、指定した条件に一致するサブセットまで削減できます。

> [!NOTE]
>
> * 配列内のオブジェクトの形状は、配列のフィルター処理アクションを使用して変更できません。
> * フィルター処理するテキストでは大文字と小文字を区別します。

この例では、この配列に対して配列のフィルター処理アクションを使用します。

``` JSON
[ { "first": "Eugenia", "last": "Lopez" }, { "first": "Elizabeth", "last": "Moore" } ]
```

`first` が `Eugenia` に設定されたオブジェクトのみを含む新しい配列を作成します。

作成してみましょう。

1. **配列のフィルター処理** アクションを見つけて、フローに追加します。
2. 次の画像のように配列のフィルター処理アクションを構成します。
   
    ![From セクションで最初の行を Body に設定します。 2 行目で first が Eugenia と等しく設定されています](./media/data-operations/add-configure-filter-array-2.png)
3. フローを保存して実行します。
   
    [PostMan](https://www.getpostman.com/postman) を利用して、JSON 配列をフローに送信する Web 要求を生成できます。
4. フローを実行すると出力は次のような配列になります。 `first` が `Eugenia` に設定されているオブジェクトのみがアクションの出力に含まれることに注意してください。

    ``` JSON
    [ { "first": "Eugenia", "last": "Lopez" }]
    ```

## <a name="use-the-create-csv-table-action"></a>CSV テーブルの作成アクションを使用する

**データ操作 - CSV テーブルの作成** アクションを使用して、JSON 配列をコンマの区切り値 (CSV) テーブルに変更します。 CSV 出力でヘッダーの表示を維持できます。 この例では、次の配列を CSV テーブルに変換します。

``` JSON
[ { "first": "Eugenia", "last": "Lopez" }, { "first": "Elizabeth", "last": "Moore" } ]
```

1. **データ操作 - CSV テーブルの作成** アクションを探して追加し、次の画像のように構成します :
   
    ![CSV テーブルの作成アクションを構成します。 From を Body に、Columns を Automatic に設定する](./media/data-operations/create-csv-table-2.png)
   
    この画像の **Body** トークンは **HTTP 要求の受信時** アクションのものですが、**CSV テーブルの作成** アクションの入力は、フローにおける前のアクションの出力から取得でき、または **From** ボックスに直接入力します。
2. フローを保存して実行します。

フローを実行すると **CSV テーブルの作成** アクションが次の画像に示す出力を表示します。

![CSV テーブルの作成アクションの出力では、最初の行に "first,last" が表示され、その後に "Eugenia,Lopez" と "Elizabeth,Moore" が表示されます](./media/data-operations/create-csv-table-output-2.png)

## <a name="use-the-create-html-table-action"></a>HTML テーブルの作成アクションを使用する

**データ操作 - HTML テーブルの作成** アクションを使用し、JSON 配列入力を HTML テーブルに変更します。 HTML 出力でヘッダーの表示を維持できます。

これを行うには、CSV テーブルを作成する前のセクションの手順に従いますが、**CSV テーブルの作成** の代わりに **データ操作 - HTML テーブルの作成** アクションを使用します。

> [!TIP]
> HTML テーブルをメールで送信する場合は、メール アクションで **IsHtml** を選択してください。
