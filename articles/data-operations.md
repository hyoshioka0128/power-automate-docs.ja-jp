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
ms.date: 07/20/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d40b59ea6f4e185ee1ccab8c973012e00f9e6f62
ms.sourcegitcommit: 9cd1eee32594e9b68c920c13e80515c3dcb55c1d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "3609844"
---
# <a name="use-data-operations-with-power-automate"></a>Power Automate でデータ操作を使用する

このチュートリアルでは、Power Automate で頻繁に使用するデータ操作について説明します。作成、結合、選択、配列のフィルター処理、テーブルの作成、JSON の解析など、フロー作成時のデータ操作に使用できる操作です。

## <a name="prerequisites"></a>前提条件
* Power Automate へのアクセス。
* [PostMan](https://www.getpostman.com/postman) のようなツールで、JSON 配列を使ってHTTP POST リクエストをフローに送信することができます。

## <a name="use-the-compose-action"></a>作成アクションを使用する
**データ操作 - 作成** (作成) アクションを使用すると、フローの設計時に、同じデータを何度も入力しせずに済みます。 たとえば、フローの設計時に ````[0,1,2,3,4,5,6,7,8,9]```` という数字の配列を何度も入力する必要がある場合は、作成アクションを使用して、次のように配列を保存できます :

1. **作成** を探し、**データ操作 - 作成** (作成) アクションを選択します。
   
    ![作成アクションを探し、選択する](./media/data-operations/search-select-compose-2.png)
2. 後から参照を行う配列を **入力** ボックスに入力します :
   
    ![作成アクションを構成する](./media/data-operations/add-array-compose-2.png)

> [!TIP]
> 後で容易に参照できるように、**作成**カードのタイトルバーにある「作成」というテキストをクリックして、**作成**カードの名前を変更します。
> 
> 

作成アクションのコンテンツにアクセスする必要がある場合は、以下のステップに従って、**このフローで使用されているアプリやコネクタから動的コンテンツを追加する**リストの**結果** トークンを介して行います。

1. **データ操作 - 結合** などのアクションを追加します。
2. 作成アクションで保存した内容を追加したいコントロールを選択します。
   
    **このフローで使用されているアプリやコネクタから動的コンテンツを追加する** が開きます。
3. **このフローで使用されているアプリやコネクタから動的コンテンツを追加する** で、**動的コンテンツ** タブの**作成**カテゴリにある**結果**トークンを選択します。
   
    ![作成アクションの結果を使用する](./media/data-operations/use-compose-output-2.png)

## <a name="use-the-join-action"></a>結合アクションを使用する
**データ操作 - 結合** アクション (結合) を使用し、選択した区切り記号を使用して配列を区切ります。 たとえば、メール アドレスの配列 ````["d@example.com", "k@example.com", "dal@example.com"]```` が含まれる Web 要求をフローが受け取ったことを想定します。 しかし、ご利用のメールプログラムでは、アドレスはセミコロンで区切られた単一の文字列である必要があります。 そのためには、**データ操作 - 結合** (結合) アクションを使用し、次のステップでコンマの区切り記号をセミコロン 「;」 に変更します。

1. 新たなアクションを追加し、**結合** を探します。続いて**データ操作 - 結合** (結合) を選択します。
   
    ![結合アクションを探して選択する](./media/data-operations/search-select-join-2.png)
2. **From** ボックスに配列を入力し、使用する新しい区切り記号を **結合する** ボックスに入力します。
   
    ここでは、新しい区切り記号としてセミコロン (;) を使用しました。
   
    ![結合アクションの構成](./media/data-operations/add-array-join-2.png)
3. フローを保存して実行します。
4. フローの実行後は、**データ操作 - 結合** アクションの結果は次のようになります :
   
    ![結合の結果](./media/data-operations/join-output-2.png)

## <a name="use-the-select-action"></a>選択アクションを使用する
**データ操作 - 選択** (選択) を使用し、配列内のオブジェクトのシェイプを変換します。 たとえば、配列内の各オブジェクトの要素を追加、削除、名前変更するとします。

> [!NOTE]
> 選択アクションで要素の追加や、削除をできますが、配列内のオブジェクトの数は変更できません。
> 
> 

たとえば、次のような形式で、データが Web リクエスト経由でフローに入った場合に、選択アクションを使用することができます :

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

また、「first」 を 「FirstName」 に、「last」 を 「LastName」 にリネームし、「first」 と 「last」 をスペースで区切った 「FamilyName」 という名前の新しいメンバーの追加をすることで、受信データの形を変えたいとします。

````[ { "FirstName": "Deon", "FamilyName": "Herb", "FullName": "Deon Herb" }, { "FirstName": "K", "FamilyName": "Herb", "FullName": "K Herb" } ]````。

実行手順:

1. **HTTP リクエストを受信したとき** (リクエスト) のトリガーをフローに追加します。
2. **要求**カードから **サンプルのペイロードを使用してスキーマを生成する** を選択します。
![サンプル ペイロードを選択](./media/data-operations/request-trigger.png)
3. 表示されたボックスで、ソース データ配列のサンプルを貼り付け、**完了** ボタンを選択します。
![貼り付けサンプル](./media/data-operations/paste-sample.png)
4. **データ操作 - 選択** (選択) アクションを追加し、次のイメージのように構成します :
   
    ![選択アクションの構成](./media/data-operations/select-card-2.png)
   
   > [!TIP]
   > 選択アクションの結果は、新しくシェイプされたオブジェクトを含む配列となります。 この配列は、前述の**作成**アクションなど、他のアクションでも利用できます。
   > 
   > 

## <a name="use-the-filter-array-action"></a>フィルタ配列アクションを使用する
**データ操作 - 配列のフィルター処理** (配列のフィルター処理) を使用すると、配列内のオブジェクト数を、指定した条件に一致するサブセットまで減らすことができます。

> [!NOTE]
> フィルタ配列では、配列内のオブジェクトのシェイプを変更することはできません。 また、フィルター処理をするテキストでは大文字と小文字が区別されます。
> 
> 

たとえば、次の配列でフィルター処理を利用できます :

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

*first* が “Deon” に設定されているオブジェクトのみを含む新たな配列を作成します。

作成してみましょう。

1. **配列のフィルター処理** (配列のフィルター処理) アクションを探し、フローに追加します。
2. 次のイメージのように配列のフィルター処理アクションを構成します。
   
    ![フィルター配列処理の構成](./media/data-operations/add-configure-filter-array-2.png)
3. フローを保存して実行します。
   
    [PostMan](https://www.getpostman.com/postman) を利用して、JSON 配列をフローに送信する Web 要求を生成できます。
4. フローを実行すると、JSON 入力は次のような配列になることが想定されます :
   
    ````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````
   
    結果の配列は次のようになります (*first* が “Deon” に設定されているオブジェクトのみがアクションの結果に含まれます) :
   
    ````[ { "first": "Deon", "last": "Herb" } ]````

## <a name="use-the-create-csv-table-action"></a>CSV テーブルの作成アクションを使用する
**データ操作 - CSV テーブルの作成** (CSV テーブルの作成) を使用し、JSON 配列をコンマ区切り (CSV) テーブルに変更します。 必要に応じて、CSV 出力でヘッダーの表示したままにすることができます。 たとえば、**CSV テーブルの作成** アクションを利用し、次の配列を CSV テーブルに変換することができます :

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

1. **データ操作 - CSV テーブルの作成** アクションを探して追加し、次の画像のように構成します :
   
    ![CSV テーブルの作成アクションを構成する](./media/data-operations/create-csv-table-2.png)
   
    注 : このイメージの**本文**トークンは **HTTP 要求の受信時**アクションに由来するものですが、**CSV テーブルの作成**アクションの入力は、フローに配置された直前のアクションの結果から取得できます。または、**From** ボックスに直接入力することも可能です。
2. フローを保存して実行します。
   
    フローを実行すると、**CSV テーブルの作成** 結果は次の画像のようになります :
   
    ![CSV テーブル結果の作成](./media/data-operations/create-csv-table-output-2.png)

## <a name="use-the-create-html-table-action"></a>HTML テーブルの作成アクションを使用する
**データ操作 - HTML テーブルの作成** を使用し、JSON 配列の入力を HTML テーブルに変更します。 必要に応じて、HTML 出力でヘッダーの表示したままにすることができます。

これを行うには、[CSV テーブルの作成](#use-the-create-csv-table-action)セクションに記載のステップに従ってください。 この場合は、**データ操作 - CSV テーブルの作成** アクションではなく、**データ操作 - HTML テーブルの作成** アクションを使用してください。

> [!TIP]
> HTML テーブルをメールで送信する場合は、メール アクションで "IsHtml" を選択してください。
> 
> 

