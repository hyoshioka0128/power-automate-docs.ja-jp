---
title: 携帯電話からのフローの管理 | Microsoft Docs
description: フローの一覧を表示し、有効または無効にして、各フローのイベントの所要時間 (秒単位)、アクションの所要時間 (秒単位)、および実行履歴を表示します
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
ms.openlocfilehash: ce9a943f50ef5c8cc69e5dbf8fde796a75e4cdf9
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195811"
---
# <a name="manage-flows-in-power-automate-from-your-phone"></a>携帯電話から Power Automate のフローを管理する

作成したすべてのフローの一覧と、各フローのイベントとアクションを表示します。また、そのフローを有効または無効にしたり、実行履歴を確認したりします。

**前提条件**

* [Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios)、または [Windows Phone](https://aka.ms/flowmobilewindows) 用の Power Automate モバイル アプリを、[サポートされているデバイス](getting-started.md#use-the-mobile-app)にインストールします。 このトピックのグラフィックは iPhone バージョンのアプリを示していますが、Android および Windows Phone の場合もこれに似ています。
* フローをまだ準備していない場合は、[Power Automate 用の Web サイト](https://flow.microsoft.com/)で作成してください。 より簡単にテストできるように、外部イベントが発生するのを待つのではなく、自分でトリガーできるフローを使用します。

このチュートリアルのフローは、特定のアドレスからメールを受信したときに実行されます。

![特定のアドレスからメールを受信したときにフローをトリガー](./media/mobile-manage-flows/create-trigger.png)

このようなフローは、テストするときは自分の個人用電子メール アドレスを、そのフローを実際に使用する準備ができたときは別のアドレス (マネージャーのアドレスなど) を指定して構成できます。

フローが実行されると、次の構文のカスタム プッシュ通知が携帯電話に送信されます。

![Slack へのメッセージの送信](./media/mobile-manage-flows/create-event.png)

**注:** モバイル アプリから[フロー アクティビティを監視](mobile-monitor-activity.md)することもできます。

## <a name="manage-a-flow"></a>フローの管理
1. モバイル アプリを開き、画面下部にある **[自分のフロー]** をタップして、フローの一覧を表示します。
   
    各エントリには、フローの名前、そのイベントとアクションのアイコン、最後に実行された時間、最後の実行が成功したかどうかを示すアイコンが表示されます。
   
    ![フローの一覧](./media/mobile-manage-flows/flow-list.png)
2. フローをタップして、そのフローを管理するためのオプションを表示します。
   
    ![フローの管理オプション](./media/mobile-manage-flows/flow-details.png)
3. **[Enable flow (フローを有効にする)]** をタップして、フローを有効または無効にします。
4. **[See flow (フローを表示)]** をタップして、そのフローのイベントとアクションを表示します。次に、各イベントまたはアクションをタップして展開し、 **[Back (戻る)]** をタップします。
   
    ![フローのイベントとアクション](./media/mobile-manage-flows/flow-event-action.png)
5. **[Run history (実行履歴)]** をタップして、フローの成功、失敗、またはその両方を表示します。
   
    ![実行の一覧](./media/mobile-manage-flows/history-mixed.png)
6. 実行をタップして、各イベントとアクションが成功したかどうかを表示し、成功した場合はその所要時間 (秒単位) を表示します。
   
    ![実行の詳細](./media/mobile-manage-flows/flow-run.png)

