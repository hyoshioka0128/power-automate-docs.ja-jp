---
title: 携帯電話からのアクティビティの監視 | Microsoft Docs
description: 各フローが成功または失敗した回数、各実行が発生した時間、およびその所要時間を表示します
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/11/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 70e12872e997ae962b5d2b0c313615675dce8012
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709303"
---
# <a name="monitor-activity-in-power-automate-from-your-phone"></a>電話から Power Automate のアクティビティを監視する

各フローが成功または失敗した回数の要約を表示します。この回数は、今日、昨日、およびその前の日付に対して表示されます。 また、実行された時間、各ステップの所要時間、失敗したかどうか、失敗した場合はその理由など、各実行の詳細を確認します。

**前提条件**

<iframe width="560" height="315" src="https://www.youtube.com/embed/vZuYZ64K3tI?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

* [対応している デバイス](getting-started.md#use-the-mobile-app)に、[Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios)、[Windows Phone](https://aka.ms/flowmobilewindows) 向けの Power Automate モバイル アプリをインストールします 。 このトピックのグラフィックは iPhone バージョンのアプリを示していますが、 Android および Windows Phone の場合にも共通しています。
* クラウド フローをまだ準備していない場合は、[Power Automate の Web サイト](https://flow.microsoft.com/)上で作成してください。 より簡単にテストできるように、外部イベントが発生するのを待つのではなく、自分でトリガーできるフローを使用します。

このチュートリアルのフローは、特定のアドレスからメールを受信したときに実行されます。

![特定のアドレスからメールを受信したときにフローをトリガー](./media/mobile-monitor-activity/create-trigger.png)

このようなクラウド フローは、テストするときは自分の個人用電子メール アドレスを、そのフローを実際に使用する準備ができたときは別のアドレス (マネージャーのアドレスなど) を指定して構成できます。

フローが実行されると、次の構文のカスタム プッシュ通知が携帯電話に送信されます。

![プッシュ通知を送信する](./media/mobile-monitor-activity/create-event.png)

**注:** モバイル アプリから[フローを管理](mobile-manage-flows.md)することもできます。

## <a name="display-a-summary-of-activity"></a>アクティビティの概要の表示
<iframe width="560" height="315" src="https://www.youtube.com/embed/nVCGJamOw6s?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. フローが実行されたことがない場合は、実行をトリガーしてデータを生成します。
   
    データがアプリに表示されるまで時間がかかる場合があります。
2. モバイル アプリを開きます。既定では、**アクティビティ** タブが表示されます。
   
    このタブには日付ごとにデータが表示され、上部には今日のデータが示されます。
   
    ![日付ごとに整理されたアクティビティ](./media/mobile-monitor-activity/activity-day2.png)
   
    各エントリには、クラウド フローの名前と、そのトリガー イベントとアクションに対応するアイコンが表示されます。
   
    ![各フローの名前とアイコン](./media/mobile-monitor-activity/activity-flow-name.png)
   
    クラウド フローの実行が少なくとも 1 日に 1 回成功すると、成功した回数と、最後に成功した時間が表示されます。 クラウド フローが失敗すると、別のエントリに同様の情報が表示されます。
   
    ![成功または失敗の概要](./media/mobile-monitor-activity/activity-summary.png)
   
    クラウド フローがプッシュ通知を送信すると、最新の通知テキストが、成功した実行のエントリの下部に表示されます。
   
    ![プッシュ通知の例](./media/mobile-monitor-activity/activity-notification.png)
3. 1 日に複数のプッシュ通知が送信された場合、通知を左にスワイプすると、3 つ前までの実行の通知が表示されます。 1 日に送信されたプッシュ通知が 4 つを超える場合は、**さらに表示** が表示されるまで左にスワイプし、それをタップすると、すべての通知の一覧が表示されます。
   
    ![プッシュ通知の例](./media/mobile-monitor-activity/activity-notification-list.png)
4. **戻る** をタップして、アクティビティの概要に戻ります。
5. アクティビティの概要をフィルター処理するには、右上隅にあるアイコンをタップします。
   
    すべてのエントリ、失敗したエントリのみ、またはプッシュ通知が含まれるエントリのみを表示できます。
   
    ![すべての実行、失敗のみ、または通知のみを表示](./media/mobile-monitor-activity/activity-filter.png)

## <a name="show-details-of-a-run"></a>実行の詳細の表示
1. アクティビティの概要でエントリをタップして、最後の実行の詳細を表示します。
   
     各イベントとアクションが、そのイベントまたはアクションが成功したか失敗したかを示すアイコンと共に表示されます。 成功した場合は、所要時間 (秒単位) も表示されます。
   
    ![実行の詳細](./media/mobile-monitor-activity/activity-icons.png)
2. 画面下部で **前回の実行を表示** をタップしてフローのすべての実行を一覧表示し、いずれかの実行をタップして詳細を表示します。
   
    ![成功/失敗の履歴](./media/mobile-monitor-activity/history-mixed.png)

