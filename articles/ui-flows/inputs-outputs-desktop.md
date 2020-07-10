---
title: デスクトップ UI フローで入力と出力を使用する | Microsoft Docs
description: デスクトップの UI フローで入力と出力を使用します。
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
ms.date: 06/30/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 28f8600e76efb78a3f7e2e359b7c230b2c20b486
ms.sourcegitcommit: a51ebdce86c0c2399afa4ba36591fb3230eb82d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "3527372"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>デスクトップの UI フローで入力と出力を使用する

入力を使用すると、データベースやサポートされている任意のコネクタなどの外部ソースからの情報を、UI フローで自動化されるレガシ ソフトウェアに渡すことができます。

たとえば、SharePoint リストの顧客情報を、従来の会計ソフトウェアへの入力のソースとして使用できます。 また、**機密性の高いテキスト入力** を使用して、レガシー アプリケーションへのログインに必要なユーザー名やパスワードなどの機密性の高い入力を渡すこともできます。

## <a name="define-inputs-in-the-ui-flows"></a>UI フローで入力を定義する

1. **テキスト** を選択して入力を定義するか、**機密性の高いテキスト** を選択して機密性の高いテキスト入力を定義します。 

   ![新規を選択](../media/inputs-outputs-desktop/text-input.png)

1. 入力に名前、サンプル データ、説明を追加します。

    - サンプル データは、記録またはテスト時に使用されます。

    - 説明は、作成した入力を区別するのに役立ちます。

    - 機密性の高いテキスト入力の場合、サンプル値は隠され、保存後に保持されません

   ![入力フィールド](../media/inputs-outputs-desktop/text-input.png)

1.  入力を作成したら、[次へ] をクリックすると、それらを記録で使用できるようになります。

>[!TIP]
>**CTRL+ALT+L** キーの組み合わせを使用すると、UI フローで使用されているアプリケーションとの間で渡すことができるテキストを挿入できます。 このキーの組み合わせは、機密性の高いテキスト、静的テキスト、出力テキスト、および入力テキストに対して機能します。 

## <a name="use-inputs-to-pass-information-to-the-application"></a>入力を使用してアプリケーションに情報を渡す

1. 記録中に、**入力の使用** を選択すると、アプリで入力を使用できます。

1. 一覧では、次の 3 つのオプションから選択できます:

    - **入力の設定** ステップで定義した入力のいずれかを選択します。

      >[!TIP]
      >機密性の高いテキスト入力は、テキスト入力とは異なるアイコンがあるため、簡単に識別できます。

    - 以前に定義した出力を使用します (「出力」 セクションを参照)。 これは、同じ UI フロー内の異なるアプリケーション間で情報を渡す場合に便利です。

    - **新しい入力** オプションを使用して記録しているときに、新しいテキストまたは機密性の高いテキスト入力を作成します。 これは **入力の設定** ステップに戻ると見つかります。

   ![入力の種類の選択](../media/inputs-outputs-desktop/select-input-type.png)

1. 入力を使用する場所を選択します。 定義したサンプル値が自動的に使用されます。 次の例では、“WingTip Toys” は入力名 “Invoice Account” のサンプル値であり、アプリケーションに追加されます。  
    
    ![入力の場所の選択](../media/inputs-outputs-desktop/select-location-for-input.png)

1. Power Automate の **ステップの記録と編集** で、入力を使用するアクションを展開して、選択されているものを表示します。

    次の例では、“Invoice Account” が値として使用されていることがわかります。

   ![アクションの展開](../media/inputs-outputs-desktop/expand-actions.png)


   >[!NOTE]
   >機密性の高いテキスト入力を使用した場合、右上にロック アイコンが付いたアクションが表示され、機密性の高いテキスト入力を使用したことが示されます。


   ![アクションの展開](../media/inputs-outputs-desktop/lock-action.png)

1. UI フローをトリガーするときに、入力値を任意に変更できます。

## <a name="use-outputs-to-extract-information-from-the-app"></a>出力を使用してアプリから情報を抽出する

出力を使用すると、UI フローが自動化されるレガシ ソフトウェアから、データベースや任意の [サポートされているコネクタ](https://flow.microsoft.com/connectors/) などの外部宛先に情報を渡すことができます。

たとえば、従来の会計ソフトウェアの顧客情報を抽出して、SharePoint リストに追加することができます。

出力は、UI フローを記録するときにのみ作成できます。

1. 記録中に、**出力** を選択します。

   ![出力の取得](../media/inputs-outputs-desktop/get-output.png)

1. **テキストの選択** を選択します。

   ![テキストの選択](../media/inputs-outputs-desktop/select-text.png)

1. ユーザー インターフェイス要素を選択して、出力用のテキストを取得します。 テキスト値は自動的にキャプチャされます。 次に、出力の名前と説明を指定できます。

   ![UI 要素の選択](../media/inputs-outputs-desktop/select-ui-element.png)

1. 出力の名前と説明を指定します。

1. **保存**を選択します。 

これで、出力がウィザードの専用領域で使用できるようになりました。

   ![出力が可能](../media/inputs-outputs-desktop/output-available.png)

各出力には次のものがあります:

-  記録中に定義された出力名。
-  説明: このフィールドは、記録中に多くの出力を定義し、それらを後続の処理で簡単に識別できるようにする場合に非常に便利です。
-  アクション名: UI フローで出力が定義されているアクション。

## <a name="use-clipboard-content-to-define-outputs"></a>クリップボードのコンテンツを使用して出力を定義する 

記録中に、コンピューターのクリップボードにテキストをコピーして、UI フローの出力として定義することができます。

1. 記録中に文字列値をコピーする  

1. **クリップボードからテキストを取得する** を選択します。 クリップボードの内容が **サンプル値** フィールドに表示されます 

   ![クリップボード出力](../media/inputs-outputs-desktop/get-output-clipboard.png)

1. (上記のように) 出力の名前と説明を定義し、**保存** を選択します。 

    ![クリップボード出力](../media/inputs-outputs-desktop/get-output-clipboard-2.png)

## <a name="delete-an-output-from-a-ui-flow"></a>UI フローから出力を削除する

出力が不要になった場合は、関連付けられているアクションに移動し、動的な値で出力名を削除することで、出力を削除します。

## <a name="test-your-ui-flow"></a>UI フローをテストする

UI フローをテストすることで、変更と適切な再生動作を検証できます。

1. (任意) 入力フィールドに値を入力します。 

   >[!NOTE]
   >レコーダーで作成される機密性の高いテキスト入力の場合、テスト前にサンプル値を再度指定する必要があります。
    
    ![新しいテスト値](../media/inputs-outputs-desktop/new-test-value.png)

1. **今すぐテスト** を選択して、自動化されているレガシ ソフトウェアを確認します。 記録したステップが UI フロー オートメーションによって再生されます。 **再生中は、デバイスを操作しないでください。**

1. 再生が完了すると、UI フローの実行状態が表示されます:

    - アクションごとに、関連付けられている入力と共に、テストが正常に機能したことを示す状態インジケーター。

      ![正常な実行](../media/inputs-outputs-desktop/successful-run.png)

   - **機密性の高いテキスト** 入力を使用する各アクションでは、入力値は表示されません。

      ![別の画像](../media/inputs-outputs-desktop/sensitive-text-not-displayed.png)

   - また、デザイナーの下部に、このテストで得られた出力の値が表示されます。 

      ![別の画像](../media/inputs-outputs-desktop/outputs-value.png)

   - エラーが発生した場合は、エラーが発生したときのスクリーンショットとともに、問題の原因となったステップが表示されます。

## <a name="learn-more"></a>詳細はこちら

- [UI フローのトリガー](run-ui-flow.md) 方法について学習します。



