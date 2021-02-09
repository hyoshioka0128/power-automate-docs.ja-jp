---
title: Teams 向けアダプティブ カードの概要 | Microsoft Docs
description: Microsoft Teams でアダプティブ カードを使用する方法を説明します。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/01/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: add1a647385abaa303a08d201aeae1692cf2c350
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709207"
---
# <a name="overview-of-adaptive-cards-for-microsoft-teams"></a>Microsoft Teams 向けアダプティブ カードの概要

<br>
<iframe width="1129" height="635" src="https://www.youtube.com/embed/FqQ3jM2qPRM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


アダプティブ カードは、プラットフォームに依存せずに情報ブロックを共有および表示するための方法で、CSS または HTML をカスタマイズしてレンダリングする複雑さがなくなります。 クラウド アプリおよびサービスをオープンに入れ替えできる統合を使用して、JSON 形式でアダプティブ カードを作成します。 Microsoft Teams などの特定のホストに配信されると、JSON は、そのホストに自動的に適応するネイティブ UI に変換されます。 そのため、プロセス デザイナーは、ビジネス プロセス/自動化の一部として情報を表示する必要がある場合にいつでも、一貫した UI パターンを提供できるようになります。
 
アダプティブ カードはそのホストに適応するため、Microsoft Teams とその他のサービスとの間で情報を共有するための最適な手段となります。

  ![アダプティブ カードのスクリーンショット](media/adaptive-cards/multi-adaptive-cards.png)
 
## <a name="currently-available-actions-for-flows"></a>フローで現在使用可能な操作
 
次の操作により、作成者は Microsoft Teams 用のアダプティブ カードを作成できます。 統合シナリオの進化に伴い、他のホストも Power Automate によってサポートされるようになるため、Microsoft クラウド サブスクリプション全体でアダプティブ カードを活用する機会が広がります。
 
## <a name="directing-content-to-teams-members-or-aad-users"></a>コンテンツを **Teams メンバーまたは AAD ユーザー** に宛てる
 
- **独自のアダプティブ カードをフロー ボットとしてユーザーに投稿する**  
  この操作により、特定のユーザーにアダプティブ カードがフロー ボットとして投稿されます。 この場合、受信者の電子メール アドレスを入力する必要があります。フローの実行中に、受信者のチャットやアクティビティ フィードにカードが表示されます。 こうした種類のアダプティブ カードを受け取るために、ユーザーは Teams インスタンスの一部になる必要はありません。 この場合、フロー内で構成されている URL にリダイレクトすることで、URL ボタンのみが機能します。

    ![アダプティブ カードのサンプル](media/adaptive-cards/top.png)
 
- **フロー ボットとしてアダプティブ カードを Teams ユーザーに投稿して応答を待機する**  
  この操作では、この記事で既に説明したケースのように、アダプティブ カードをフロー ボットとして特定のユーザーに投稿します。 ただし、この場合、受信者がカード内で必要な入力に応答するまで、投稿後、フロー実行は続行されません。 受信者が応答した後、フローは続行されます。 フローでは、受信者およびカードごとに、1 つの応答に対して動的コンテンツが返されます。
 
## <a name="directing-content-to-teams-channels"></a>コンテンツを **Teams チャネル** に宛てる
 
- **独自のアダプティブ カードをフロー ボットとしてチャンネルに投稿する**  
  この操作により、特定の Teams チャネルにアダプティブ カードがフロー ボットとして投稿されます。 この場合、Teams インスタンスと、カードが投稿されるチャネルを入力するように求められます。 フローの作成者は、そこにアダプティブ カードを投稿するために、Teams インスタンスにアクセスできる必要があります。 この場合、フロー内で構成される URL にリダイレクトすることで、URL ボタンのみが機能します。
 
- **フロー ボットとしてアダプティブ カードを Teams チャネルに投稿して応答を待機する**  
  この操作により、上記の場合と同様、特定の Teams チャネルにアダプティブ カードがフロー ボットとして投稿されます。 ただし、この場合、チャネル上のだれかがカード内の必要な入力に応答するまで、フローは続行されません。 フローは、Teams チャネル内のだれかが応答すると続行されますが、応答者およびカードごとに 1 つの応答に対して動的なコンテンツのみが返されます。
 
     ![フロー ボットとしてアダプティブ カードを Teams チャネルに投稿して応答を待機する](media/adaptive-cards/bottom.png)

     >[!TIP]
     >このカードを使用した場合、フローは任意の Teams メンバーからの応答を待機します。
 
 
## <a name="known-issues"></a>既知の問題
 
- いずれかの "応答の待機" 操作を使用して作成された場合を除き、アダプティブ カードからデータを収集することはできません。 待機しないアダプティブ カードでは、OpenURL 以外のすべてのボタン操作でエラーが返されます。 詳細については、[OpenURL ボタン](https://adaptivecards.io/explorer/Action.OpenUrl.html)を参照してください。 

- "応答を待機する" サフィックスを含まないカードで Action.Submit ボタンを選択すると、エラーがスローされます。
 
- "応答の待機" 操作を使用して作成されたアダプティブ カードは、カードごとに 1 回のみ送信できます。 最初の応答後、フロー実行が続行され、以降の送信はすべて無視されます。
 
- "更新メッセージ" 入力ボックス (イメージ 3 を参照) 内の情報のみが、コンシューマーがカードを送信した後、代わりのカードに表示されます。

  カードを送信する個人のユーザー ID などのその他の詳細情報は、"応答の待機" 操作に続く操作で、動的コンテンツ内で利用できます。 ただし、カードを送信したユーザーに対して必要なプロファイル情報を完成させるには、Office 365 Users コネクタを含める必要がある場合があります。
 
- "応答を待機する" アダプティブ カードが送信されると、交換/更新メッセージ領域が構成されない限り、カードはリセットされて、まったく同じように表示されます。 更新メッセージはベスト プラクティスであり、他のユーザーを更新するために、また、コンシューマーが複数回カードを送信できないようにするためにも推奨されます。
 
   ![更新メッセージ](media/adaptive-cards/update-message.png) 
 
>[!TIP]
>**更新メッセージ** と **カードの更新が必要** の入力は、代わりのカードが必要な場合に構成される必要があります。
 
- Power Automate では、Microsoft アダプティブ カード固有の機能とサービスを使用して、任意のホスト内のカードが処理されます。 この記事は、フローの操作に関連する詳細を明確にすることを目的としています。 [アダプティブ カードの作成](https://docs.microsoft.com/adaptive-cards/)については、詳細なドキュメントもご覧ください。
 
## <a name="learn-more"></a>詳細情報を見る 
 
- [アダプティブ カードを初めて](https://docs.microsoft.com/power-automate/create-adaptive-cards)作成する
- [Microsoft Teams コネクタ](https://docs.microsoft.com/connectors/teams/) に関する完全なドキュメント
- [アダプティブ カードの IO](https://docs.microsoft.com/adaptive-cards) に関する詳細なドキュメント 

