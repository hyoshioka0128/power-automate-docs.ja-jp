---
title: Microsoft Teams にアダプティブ カードを投稿するフローを作成する | Microsoft Docs
description: アダプティブ カードを使用して、充実したフォーマットのされたコンテンツを Microsoft Teams に投稿するフローの作成方法について説明します。
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
ms.date: 01/04/2020
ms.author: deonhe
ms.openlocfilehash: 186526427d8de7ee05dd6860e302faae5ac1d97f
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297430"
---
# <a name="create-your-first-adaptive-card"></a>アダプティブ カードを初めて作成する

Power Automate 内のアダプティブカードは、情報のブロックを共有するか、所定のデータソースのフォームを介してデータを収集します。 

どちらの場合も、どのデータセットを共有するか、および/またはフォームでどのデータを収集する必要があるかについて、概要を考える必要があります。 

>[!TIP]
>複雑なテーブル配列ではなく、シンプルなデータ ブロックを使用します。

## <a name="prerequisites"></a>前提条件

<!-- Is it still called Flow App? -->
- Microsoft Teams Flow アプリがインストールされます。

## <a name="add-an-action"></a>アクションを追加します

この手順では、フロー内の前のアクションのデータを使用して、 Microsoft Teams チャネルに情報を投稿するアクションを追加します。

1. Power Automate にサイン インする。
1. 上部のナビゲーション バーで **[マイ フロー]** を選択します。
1. **[新規]** > **[インスタント - 一から作成]** の順に選択します。
1. 自分のフローに名前を付けます。
1. トリガーとして **[手動でフローをトリガーします]** を選択します。
1. **作成** を選びます。

    <!-- | [./media/image5.png](./media/image5.png) | [./media/image6.png](./media/image6.png) | -->

1. **+ 新しいステップ** を選択します。
1. **Microsoft Teams** を検索し、アクションとして **アダプティブ カードを Teams チャネルに投稿して応答を待機する** を選択します。
1. カードの投稿先にする **[チーム]** と **[チャネル]** を選択します。
1. 次の JSON を **[メッセージ]** ボックスに貼り付けます。

    ``` JSON
    {
        "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
        "type": "AdaptiveCard",
        "version": "1.0",
        "body": [
            {
                "type": "TextBlock",
                "text": "Poll Request",
                "id": "Title",
                "spacing": "Medium",
                "horizontalAlignment": "Center",
                "size": "ExtraLarge",
                "weight": "Bolder",
                "color": "Accent"
            },
            {
                "type": "TextBlock",
                "text": "Header Tagline Text",
                "id": "acHeaderTagLine",
                "separator": true
            },
            {
                "type": "TextBlock",
                "text": "Poll Header",
                "weight": "Bolder",
                "size": "ExtraLarge",
                "spacing": "None",
                "id": "acHeader"
            },
            {
                "type": "TextBlock",
                "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer vestibulum lorem eget neque sollicitudin, quis malesuada felis ultrices. ",
                "id": "acInstructions",
                "wrap": true
            },
            {
                "type": "TextBlock",
                "text": "Poll Question",
                "id": "acPollQuestion"
            },
            {
                "type": "Input.ChoiceSet",
                "placeholder": "Select from these choices",
                "choices": [
                    {
                        "title": "Choice 1",
                        "value": "Choice 1"
                    },
                    {
                        "title": "Choice 2",
                        "value": "Choice 2"
                    },
                    {
                        "title": "Choice 3",
                        "value": "Choice 3"
                    }
                ],
                "id": "acPollChoices",
                "style": "expanded"
            }
        ],
        "actions": [
            {
                "type": "Action.Submit",
                "title": "Submit",
                "id": "btnSubmit"
            }
        ]
    }
    ```

1. JSON の値を次のように置き換えます。

    >[!IMPORTANT]
    >置き換えを行うときに、引用符を削除しないでください。 必要に応じて、自動車の選択肢を変更することができます。

    変更するテキスト | 新しいテキスト
    ------|------
    Header Tagline Text (ヘッダー タグラインのテキスト)|Power Automate を使用した投票
    Poll Header (投票ヘッダー)| Preferred Car Model (好みの自動車モデル)
    | Poll Question (投票の質問)   | Please vote on your preferred car model from the choices listed here. (ここに記載された選択肢から、好みの自動車モデルに投票してください。) 
    Replace the latin text with a reason, or business context, related to why you are conducting the poll. (投票を実施している理由に関連して、ラテン語のテキストを理由またはビジネス コンテキストに置き換えます。)      |  We are polling our employees in order to determine if we should provide personalized parking places which are sized for the most popular cars. (最も人気のある自動車用に広さを設定した、個別の駐車場を用意する必要があるかどうかを判断するために、従業員に投票を行っています。) 
    | Choice 1 (選択肢 1) (両方の場所で置き換えます)  | Tesla   |
    | Choice 2 (選択肢 2) (両方の場所で置き換えます) | Lexus |
    | Choice 3 (選択肢 3) (両方の場所で置き換えます) | Honda |

1. **[新しいステップ]** を選択してから、アクセス権のある **[電子メールを送信する]** アクションのいずれかを検索して選択します。 
1. インスタント ボタンを選択したユーザーとして、メールの受信者を指定します (**トリガー** の動的コンテンツから **[メール]** タグを使用します)。
1. 次のように、メールの **[本文]** を構成します。 波かっこ "{}" 内の単語は、動的トークンに置き換えます。  
    **あなたの投票の回答は {acPollChoices} でした** (acPollChoices は、応答の待機アクションからの動的コンテンツです)。  **これは {ユーザー名} によって送信されました**  (ユーザー名はトリガーからの動的コンテンツです)

## <a name="test-your-adaptive-card"></a>アダプティブ カードをテストする

作業をテストするには、前の手順で作成したフローを実行し、次のことを確認します。

- フローを実行してもエラーが発生せず、応答を待機して、アダプティブ カード アクションの待機インジケーターが実行画面に表示される。 

- Teams チャネルに新しいアダプティブ カードが投稿されている。

- 自動車モデルを選択してカードに応答し、アダプティブ カードの下部にある **[送信]** ボタンを選択した場合:

    - アダプティブ カードでエラーが発生しない。

    - フローの実行が正常に完了する。

- **応答の待機** アクションの下部にある **[更新メッセージ]** 領域を構成した場合は、送信後にカードの置き換えが関係する (対応する代わりのカードと共に次に示します)。 それ以外の場合は、すべての送信でフォームが単にリセットされる。

    ![代わりのカード](./media/adaptive-cards/update-message-2.png)

- メール通知に、応答の送信者と選択された自動車を示す本文が含まれている。

おめでとうございます! 初めての対話型アダプティブ カードを作成できました。

![初めてのカードが完成](media/adaptive-cards/finished-first-card.png) 


## <a name="troubleshooting-tips-for-adaptive-cards"></a>アダプティブ カードに関するトラブルシューティングのヒント

アダプティブ カードの作成時に発生する最も一般的な問題は次のとおりです。

-   フロー実行のエラーは、多くの場合、次のいずれかの要因によって発生します。

    -  Flow アプリが Microsoft Teams にインストールされていません。Teams に [Flow アプリをインストール](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams) してください。 
    
    この場合、次のスクリーンショットのようなエラーが発生することがあります。  

    ![エラー メッセージ](media/adaptive-cards/error-message.png)

    -  不適切な形式の JSON。これは通常、予想されるほど複雑ではありません。 ほとんどの場合、単に次のような状況が該当します。

        - JSON 内の値をカールした引用符で囲っていたり、引用符が不足していたりする。 常に JSON をチェックして、すべてのテキスト値が二重引用符で囲まれていることと、数値が引用符で囲まれていることを確認してください。 すべての引用符は、カールしたものではなく、まっすぐである必要があります。

        - JSON を [カード ペイロード エディター](https://adaptivecards.io/designer/)に貼り付けることで、使用する JSON の形式を検証できます。

    - 画像の URL が見つからない。アダプティブ カード内のすべての画像の値が、有効な URL を参照している必要があります。 アダプティブ カードでは、完全な画像コンテンツは直接サポートされていません。 ブラウザーに URL を貼り付けて画像が表示されるかどうかを確認することで、お使いの画像リンクをテストします。

- スタイル設定やスキーマの制約のために、アダプティブ カードの外観が期待どおりにならない場合があります。

    - プレースホルダーの値、テキストのスタイル、およびすべてのマークアップ言語がアダプティブ カードのスキーマ要件と一致していることを確認します (**アダプティブ カードのスキーマのベスト プラクティス** について、[こちら](https://adaptivecards.io/explorer/)から確認します)

    - **Visual Studio Code** のアダプティブ カード検証ツールを活用します。 これを Visual Studio Code アプリケーションからインストールするには、拡張機能マーケットプレースを開き、**アダプティブ カード ビューワー** を検索します。

      ![Visual Studio Code 拡張機能](media/adaptive-cards/visual-studio-code-extension.png)
  
Visual Studio Code にインストールされた アダプティブ カード ビューワー 拡張機能のスクリーンショットの一部 (ショートカット:Ctrl+V+A 有効化が必要です)。

- アダプティブ カードの送信後に発生するエラーは、多くの場合、次が原因です。

    - 名前に 'wait for response' (応答の待機) が含まれていないアクションの使用  
        
        ![やり直し](media/adaptive-cards/try-again.png)

    - カードの送信を複数回試行。 各アダプティブ カードは一度だけ送信できます。その後は、それ以降の送信はすべて無視されます。
