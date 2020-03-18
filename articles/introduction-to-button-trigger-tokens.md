---
title: ボタン トリガー トークンの概要 | Microsoft Docs
description: Microsoft ボタン フローのボタン トリガー トークンについて紹介します。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/12/2016
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d2a7cbf1f3bb582853583a790e2bd26f319655d3
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195729"
---
# <a name="get-started-with-button-trigger-tokens"></a>ボタン トリガー トークンの概要

## <a name="what-are-button-trigger-tokens"></a>ボタン トリガー トークンとは
ボタン トリガー トークンは、[ボタン フロー](introduction-to-button-flows.md)が実行されているデバイスから確認でき、使用できるデータ ポイントです。 このトークンは、現在の時刻や特定の時点でのデバイスの地理的場所などの要因に基づいています。  

たとえば、スマート フォンでボタン フローを実行している場合、日付や現在地だけでなく、現在地と**その時刻も電話が把握する**ことができます。 つまり、電話が位置する日付、時刻、住所はすべてボタン フローが実行されている時刻から決定されることになります。 この時刻はデバイスで実行されるすべてのボタン フローが自動的に使用できます。 このトリガー トークンを使用すると、現在地を他のユーザーに提供したり、特定のジョブ/サービス通話に費やした時間を把握したりするような、繰り返しの作業を最小限にするために役立つフローを構築することができます。

### <a name="list-of-button-trigger-tokens"></a>ボタン トリガー トークンの一覧
ボタン フローの作成時に使用できるボタン トリガー トークンの一覧を次に示します。

| パラメーター | 説明 |
| --- | --- |
| 市区町村 |フローを実行しているデバイスが位置する市区町村。 |
| 国/地域 |フローを実行しているデバイスが位置する国/地域。 |
| 完全な住所 |フローを実行しているデバイスが位置する完全な住所。 |
| 緯度 |フローを実行しているデバイスが位置する緯度。 |
| 経度 |フローを実行しているデバイスが位置する経度。 |
| 郵便番号 |フローを実行しているデバイスが位置する郵便番号。 |
| 州 |フローを実行しているデバイスが位置する都道府県。 |
| 番地 |フローを実行しているデバイスが位置する番地。 |
| タイムスタンプ |フローを実行しているデバイスが位置する地域の時間。 |
| Date |フローを実行しているデバイスが位置する地域の日付。 |
| ユーザー名 |フローを実行しているデバイスにサインインしているユーザーのユーザー名。 |
| ユーザーの電子メール |フローを実行しているデバイスにサインインしているユーザーのメール アドレス。 |

## <a name="create-a-button-flow-that-uses-trigger-tokens"></a>トリガー トークンを使用するボタン フローを作成する
ボタンを作成するときに、トリガー トークンを使用してボタンに豊富な機能を追加できます。

このチュートリアルでは、Android デバイスでボタン フローを作成します。 このボタン フローは、トリガー トークンを使用して "**在宅勤務**" の電子メールの日付と完全な住所を上司に送信します。

このチュートリアルでは Android デバイスのスクリーンショットが使用されますが、iOS デバイスおよび Windows Phone デバイスでの表示もこれに似ています。

### <a name="prerequisites"></a>前提条件
* 職場または学校のメール アドレス、もしくは Power Automate にアクセスできる [Microsoft アカウント](https://account.microsoft.com/about?refd=www.microsoft.com)。
* [Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios)、または [Windows Phone](https://aka.ms/flowmobilewindows) 向けの Power Automate モバイル アプリ。

開始手順:

1. Flow を起動し、 **[参照]**   を選択します  
   ![ボタン トリガー トークン](./media/introduction-to-button-trigger-tokens/1.png)  
2. **[ボタン]** カテゴリの下にある **[Send a 'Working from home today' email to your manager]** ('本日在宅勤務' のメールをマネージャーに送信する) サービスを選択します   
   ![ボタン トリガー トークン](./media/introduction-to-button-trigger-tokens/2.png)  
3. **[このテンプレートを使用]** を選択します  
   ![ボタン トリガー トークン](./media/introduction-to-button-trigger-tokens/3.png)  
4. **[Send an email]** (電子メールを送信する) カードの **[編集]** を選択します  
   ![ボタン トリガー トークン](./media/introduction-to-button-trigger-tokens/3-5.png)  
5. **[件名]** テキスト ボックスをタップし、"WFH" テキストの後ろのテキスト ボックスに「**today -** 」と入力します。 テキスト ボックスをタップしたときにパラメーター/トークンの一覧も開いていることを確認してください。 次のステップでは、このトークンの 1 つを使って電子メールの件名に日付を追加します。  
   ![ボタン トリガー トークン](./media/introduction-to-button-trigger-tokens/4.png)  
6. カーソルを [件名] テキスト ボックスに置いた状態で、パラメーターの **[manual]** (手動) 一覧にスクロールして、 **[日付]** をタップします。 日付パラメーターが **[件名]** テキスト ボックスに表示されていることを確認します。  
   ![ボタン トリガー トークン](./media/introduction-to-button-trigger-tokens/6.png)  
7. **[本文]** テキスト ボックスにスクロールし、既定のメッセージが表示されたらタップして、追加のトークンが含められるようにします。  
   ![ボタン トリガー トークン](./media/introduction-to-button-trigger-tokens/7.png)  
8. **[完全な住所]** パラメーターをタップしてから **[作成]** をタップします。  
   ![ボタン トリガー トークン](./media/introduction-to-button-trigger-tokens/8.png)  
9. **[完了]** をタップします。 これで、ボタン フローが作成されました。  
   ![ボタン トリガー トークン](./media/introduction-to-button-trigger-tokens/9.png)  

## <a name="run-the-button-flow"></a>ボタン フローを実行する
**注**:このボタン フローにより、ご自分の現在の場所が電子メールで送信されます。  

1. 画面の下部にある **[ボタン]** カテゴリをタップします。 使用が許可されているボタンの一覧が表示されます。 今作成したボタン フローを表すボタンをタップします。  
   ![ボタン トリガー トークン](./media/introduction-to-button-trigger-tokens/10.png)  
2. ボタン フローにデバイスの場所に関する情報へのアクセスを許可することを示す **[ALLOW]** (許可) をタップします。  
   ![ボタン トリガー トークン](./media/introduction-to-button-trigger-tokens/11.png)  
3. 数分以内に、上司に電子メールが送信されます。  
   ![ボタン トリガー トークン](./media/introduction-to-button-trigger-tokens/12.png)  

おめでとうございます。日付と完全な住所の両方のトリガー トークンを使用するボタン フローが作成されました。 

## <a name="next-steps"></a>次の手順
* [ボタン フローを共有する](share-buttons.md)
* [ボタン フローについて](introduction-to-button-flows.md)
