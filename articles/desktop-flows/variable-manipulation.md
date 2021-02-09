---
title: 変数の操作と % 表記 | Microsoft Docs
description: 変数の操作と % 表記
author: georgiostrantzas
ms.service: flow
ms.topic: article
ms.date: 09/22/2020
ms.author: getrantz
ms.reviewer: ''
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7d98d2412454a5733441c38a0af991aae2f1e23b
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711677"
---
# <a name="use-variables-and-the--notation"></a>変数と % 表記を使用する



フロー内では、さらなる処理で使用するデータを保存する変数が使用されます。 すべての変数名はパーセント記号 (**%**) で囲む必要があります。 パーセント記号は、変数を表す特殊文字として使用されます。 パーセント記号の間にある式はすべて評価する必要があります。

![変更テキスト ケース アクション フィールド内のパーセンテージ表記。](media\variable-manipulation\percentage-notation.png)

場合によっては、パーセンテージ記号は計算ではなく、単純な文字として使用する必要があります。 そのような場合は、別のパーセント文字 (%%) を使用してエスケープする必要があります。

Power Automate Desktop では、ハードコードされた値、変数名、算術演算と論理演算、比較と括弧を含む複雑な式を作成できます。

![変数の設定アクションのフィールド内の複素数式。](media\variable-manipulation\expression.png)

## <a name="hardcoded-values"></a>ハードコードされた値

変数内にハードコードされたテキスト値を含めるには、引用符を使用します。 引用符の間のすべての値は、変数名としてではなく、テキスト値として扱われます。

![変数設定アクションのフィールドにハードコードされた値。](media\variable-manipulation\hardcoded-values.png)

## <a name="variable-names"></a>変数名

変数は、それ以上の表記をせずに式に名前を追加することで使用できます。

![変数設定アクションのフィールド内の複数の変数。](media\variable-manipulation\variables-names.png)

## <a name="basic-arithmetic"></a>基本的な算術

数学的な操作を行うには、加算 (**+**)、減算 (**-**)、乗算 (**\**_)、除算 (_*/**)などのすべての必須の算術演算子を使用しています。

算術演算は、主に数値や変数を使って行われます。 ただし、加算演算子を使って文字列を連結することも可能です。 同じ式の中に数字とテキスト文字列を追加すると、数字をテキストに変換し、他のテキスト文字列と連結します。

| Expression                  | 結果                                              |
|-----------------------------|-----------------------------------------------------|
| %5 * 3%                     | 15 (数字)                                         |
| %4 / Var%                   | 4 を "Var" という名前の変数の値で割ったものです  |
| %'this is ' + 'text'%       | これはテキストです (テキスト)                                 |
| %'This is the number ' + 5% | これは数字 5 です (テキスト)                         |

## <a name="comparisons"></a>比較

算術演算子の他に、以下の演算子を使って比較を行います

| オペレーター | 内容                        |
|--------- |------------------------------------|
| =, !=    | 等しい/等しくない                    |
| <, <=    | より小さい/より小さいか又は等しい       |
| >, >=    | より大きい/より大きいか又は等しい |

比較が評価された場合、 **True** または **False** のどちらかを値として生成されることに注意してください。 比較は同じ型の値同士でしかできません。

## <a name="logical-operators"></a>論理演算子

論理演算子を使用して複数の条件を同時に確認することもできるため、ひとつの式でより複雑なロジックを実装することができます。 サポートされている演算子は、AND および OR です。 

| Expression                     | 結果                                                                                                           |
|--------------------------------|------------------------------------------------------------------------------------------------------------------|
| %Index = 1 OR Index = 2%     | **インデックス** 変数の値が 1 または 2 の場合は真、そうでない場合は偽                                           |
| %Index = 4 AND Text = "Four"% | **インデックス** 変数の値が 4 で、かつ **テキスト** 変数の値が 4 の場合は真、それ以外の場合は偽です |


## <a name="parentheses"></a>かっこ

演算子の優先度を変更するには、括弧を使用します。 括弧は、代数やプログラミング言語と同じく処理されます。

![変数の設定アクションのフィールド内の括弧付きの式。](media\variable-manipulation\parentheses.png)