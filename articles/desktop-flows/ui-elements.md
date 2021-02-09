---
title: UI 要素とコントロール | Microsoft Docs
description: UI 要素とコントロール
author: rokontol
ms.service: flow
ms.topic: article
ms.date: 09/22/2020
ms.author: rokontol
ms.reviewer: rokontol
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d8db6a36aa1628a1e7d30827b903e412b6ac8fed
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711643"
---
# <a name="automate-using-ui-elements"></a>UI 要素を使用して自動化する



**UI オートメーション** グループ配下のアクションは、ウィンドウやアプリケーションとの直接的なやり取りを意図して設計されています。 画像認識や絶対座標に頼らずにこの結果を得るには、Power Automate Desktop は **UI 要素** を利用してウィンドウとその要素を識別しています。

## <a name="ui-elements"></a>UI 要素
UI オートメーションのアクションを使用する場合、UI 要素を入力値として使用する必要があります:

![UI 要素の入力](./media/ui-elements/ui-element-input.png)

新しい UI 要素を追加するには、アクションのプロパティから直接追加するか、デザイナーの右側にある UI 要素ペインから追加します:

![新しい UI 要素の追加](./media/ui-elements/add-new-ui-element.png)

フローに要素を追加するには、それを強調表示して **Ctrl と左クリック** を押します:

![UI 要素のキャプチャ](./media/ui-elements/capturing-ui-elements.png)

終了後は、**完了** を押します。 キャプチャされた UI 要素はすべて UI 要素ペインに追加されます。 **ソート** アイコンを選択することで、要素をアルファベット順に並べ替えることができます。

UI 要素の名前を変更、削除するには、アイテムを右クリックして適切な機能を選択します。

キャプチャされた要素をアクションで使用するには、ドロップダウンリストから要素を選択するだけです:

![UI 要素を入力として追加する](./media/ui-elements/add-ui-element-as-input.png)

## <a name="element-types"></a>要素の種類

キャプチャされた要素は、キャプチャされたアプリケーションの種類に基づいて、主に次の 2 つのカテゴリに分類されます: **UI コントロール** と **Web コントロール**。

互換性のある Web ブラウザ (Internet Explorer、Microsoft Edge、Firefox、Google Chrome) で表示される Web ページの一部であるキャプチャされた要素は、Web コントロールとして自動的に保存され、**Web オートメーション** のアクションの入力として使用することができます。 他のすべての要素は UI コントロールと見なされ、それぞれのアクションで使用できます。

## <a name="element-properties"></a>要素のプロパティ

UI 要素を右クリックし、**セレクターの編集** を選択して要素のセレクターを管理します。 これにより、セレクター ビルダーが表示され、ビジュアル エディターでセレクターを編集できます。

![ビジュアル セレクター エディター](./media/ui-elements/visual-selector-editor.png)

セレクターの値を手動で入力するには、ビジュアル エディターをオフに切り替えると、セレクターのテキスト値が編集可能になります。

![手動のセレクター エディター](./media/ui-elements/manual-selector-editor.png)