---
title: Markdown を使用して Power Automate の承認の書式設定を行う | Microsoft Docs
description: Markdown を使用して Power Automate の承認要求を書式設定する方法を説明します。
services: ''
suite: flow
documentationcenter: na
author: gcorvera
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/29/2020
ms.author: gcorvera
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b27effa7a904687141d606532d37927b87f69300
ms.sourcegitcommit: 741ae960b733c4569236089a1f00114508bbb451
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "3905054"
---
# <a name="use-markdown-in-power-automate-approval-requests"></a>Power Automate の承認リクエストで Markdown を使用する


この記事では、[Markdown](https://en.wikipedia.org/wiki/Markdown) 構文を使って、承認要求に様々なフォーマット設定を追加する方法について説明します。

> [!IMPORTANT]
>
> - 承認要求の電子メールは、*アクション可能なメッセージ*です。 [Microsoft Outlook  クライアント](https://docs.microsoft.com/outlook/actionable-messages/#outlook-version-requirements-for-actionable-messages) でアクション可能メッセージがサポートされない場合、承認要求は HTML 形式で表示されます。 
> - すべての Markdown レンダラーには異なる実装がされています。 詳細は、[クライアント サポート](#client-support) セクションを参照してください。
> - Markdown は現在、[GCC および GCC High の顧客](/power-automate/us-govt) には対応していません。

## <a name="client-support"></a>クライアント サポート

クライアント間の Markdown のサポートに一貫性がありません。 Power Automate チームはこれらの不整合に対処するために取り組みますが、不整合は残ります。 次の表に、対応しているクライアント間の既知の制約を示します。

| 機能 | Power Automate | Power Automate モバイル アプリ | Outlook デスクトップ | Outlook Web | チーム  | Teams mobile アプリ |  
|---------|--------|---------------|-----------------|-------------|-------|--------------|
| **ヘッダー** | 有効 | 有効 | 有効 | 有効 | **_No_** | **_No_** |
| **番号付きリスト** | 有効 | 有効 | **_No_** | 有効 | 有効 | 有効 |
| **ネストされた番号付きリスト** | 有効 | 有効 | **_No_** | 有効 | 有効 | 有効 |
| **テーブル** | 有効 | 有効 | 有効 | 有効 | **_No_** | **_No_** |
| **画像** | **_No_** | **_No_** | **_No_** | **_No_** | **_No_** | **_No_** |
| **強制改行** | 有効 | 有効 | **_番号_**（代わりに空白行を使用してください） | 有効 | 有効 | 有効 |
| **空白行** | **_無効_** | **_無効_** | 有効 | 有効 | **_無効_** | 有効 |

> [!NOTE]
> Outlook Mobile で以前に使用したパラメーターは、使用中の Outlook クライアント アプリやバージョンにより異なる場合があります。

## <a name="headers"></a>ヘッダー

ヘッダーを使用してコメントを構造化します。 ヘッダーは長いコメントをセグメント化することで、読みやすくします。

見出しを設定するには、行の先頭をハッシュ文字 `#` で開始します。 行の先頭のハッシュ文字を増やすと(例: `####`) 、注釈を小見出しで整理できます。 最大で 6 段階の見出しに対応しています。

**用例:**  
```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**結果 :**  
![フローのエクスポート](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>段落と改行

段落や改行をすることで、テキストを読みやすくします。 改行の前に 2 つのスペースを入力すると、ほとんどのクライアントで強制的に新規行を開始させます。  

**用例:**  
```Markdown
This is line 1.(space)
Now text will appear on the next line.
```

**結果:** これは1行目です。  
テキストが次の行に表示されます。 

**例 2:**
```Markdown
This is line 1.(space, space)  

Line 2 has extra space before it.
```

**結果 :**  
これは 1 行目です。  

行 2 の前には余分なスペースがあります。
  
## <a name="lists"></a>リスト

関連する項目をリスト化して整理します。 番号付きの順序りスト、または行頭文字だけの順序なしリストを追加できます。

順序化されたリストは、リスト項目ごとに数字とピリオドで開始します。 順序なしリストは、`*` で開始します。 各リスト項目は新たな行で開始します。 新たな段落を始めるには、Markdown ファイルまたはウィジェットで、改行の前に 2 つのスペースを入力するか、連続して 2 つの改行を入力します。

### <a name="ordered-or-numbered-lists"></a>順序化されたリスト、または番号付きリスト

**用例:**

```Markdown
0. First item.
0. Second item.
0. Third item.
```

**結果 :**  
1. 最初の項目。
2. 2番目の項目。
3. 3番目の項目。

### <a name="bullet-lists"></a>箇条書きリスト

**用例:**

```Markdown
- Item 1
- Item 2
- Item 3
```

**結果 :**

- 項目 1
- 項目 2
- 項目 3

### <a name="nested-lists"></a>入れ子になったリスト

**用例:**

```Markdown
1. First item.
   - Item 1
   - Item 2
   - Item 3
1. Second item.
   - Nested item 1
   - Nested item 2
   - Nested item 3
```

**結果 :** 
1. 最初の項目。

    - 項目 1
    - 項目 2
    - 項目 3
2. 2番目の項目。
    - 入れ子の項目 1
    - 入れ子の項目 2
    - 入れ子の項目 3


## <a name="links"></a>リンク

HTTP および HTTPS の URL は、自動的に書式設定されリンク化されます。 

標準の Markdown リンク構文を使って、URL のテキスト ハイパーリンクを設定できます :

```Markdown
[Link Text](Link URL)
```

**用例:**  
```Markdown
[Power Automate](https://flow.microsoft.com)
```

**結果 :**  
[Power Automate](https://flow.microsoft.com)

## <a name="tables"></a>テーブル

構造化されたデータをテーブルで整理します。 

- 各テーブルの行を独自の行に配置する 
- テーブルのセルはパイプ文字 `|` を使って区切ります 
- テーブルの最初の 2 行には、列の見出しと、テーブルの要素の配置を設定します
- テーブルの見出しと本文を分ける際にはコロン (`:`) を使って列の配置 (左、中央、右) を指定します 
- 新しい行を開始するには、HTMLブレーク タグ（`<br/>`）を使用してください
- 各行は必ず CR または LF で終了してください。 

**用例:**  
```Markdown
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br>second line of text |  
```


**結果 :**  

| 見出し 1 | 見出し 2 | 見出し 3 |  
|-----------|:-----------:|-----------:|  
| セル A1 | セル A2 | セル A3 |  
| セル B1 | セル B2 | セル B3<br>テキストの 2 行目 |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>強調 (太字、斜体、取り消し線)  

文字に太字、斜体や取り消し線を適用することで、テキストを強調できます。
- 斜体を適用するには: テキストをアスタリスク `*` またはアンダースコア `_` で囲みます
- 太字を適用するには、テキストを 2 つのアスタリスク `**` で囲みます。    
- 取り消し線を適用するには、テキストを 2 個のチルダ文字 `~~` で囲みます。

これらの要素を組み合わせて、複数の強調表現をテキストに適用できます。    

**用例:**  
```Markdown
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
```

**結果 :**  
コメントに_強調_を使用することで、意見の**強さ**を表現し、<s>修正</s>を指摘します   
**_太字、斜体のテキスト_**   
**~~太字、取り消し線テキスト~~**  

## <a name="special-characters"></a>特殊文字

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">構文</th>
<th width="350px">例/注意</th>
</tr>



<tr>
<td>
<p>次のいずれかの文字を挿入するには、先頭に円記号を付加します :</p>

<p style="margin-bottom:2px;">```\   backslash ``` </p>
<p style="margin-bottom:2px;"><code>\`</code>   `backtick`</p>
<p style="margin-bottom:2px;">```_   underscore  ```</p>
<p style="margin-bottom:2px;">```{}  curly braces  ``` </p>
<p style="margin-bottom:2px;">```[]  square brackets ```</p>
<p style="margin-bottom:2px;">```()  parentheses  ```</p>
<p style="margin-bottom:2px;">```#   hash mark  ``` </p>
<p style="margin-bottom:2px;">```+   plus sign  ```</p>
<p style="margin-bottom:2px;">```-   minus sign (hyphen) ```</p>
<p style="margin-bottom:2px;">```.   dot  ``` </p>
<p style="margin-bottom:2px;">```!   exclamation mark ```</p>


</td>
<td>特殊文字の挿入例
<p>```\\``` と入力すると、\\ と表示されます </p>
<p>```\_``` と入力すると、 _ と表示されます </p>
<p>```\#``` と入力すると、\# と表示されます </p>
<p>```\(``` と入力すると、\( と表示されます </p>
<p>```\.``` と入力すると、\. と表示されます </p>
<p>```\!``` と入力すると、\! と表示されます </p>
</td>
</tr>

</tbody>
</table>
