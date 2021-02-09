---
title: Power Automate でのトリガー | Microsoft Docs
description: Power Automate のトリガーについて詳細を説明します。
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
ms.date: 11/17/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowadmin
ms.openlocfilehash: e6702eecb71c7d0673992a90a147f5dbea9ce871
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4710287"
---
# <a name="get-started-with-triggers"></a>トリガーの基本

## <a name="what-is-a-trigger"></a>トリガーとは?

**トリガー** とは、クラウド フローを開始するイベントのことです。 たとえば、誰かがあなたに電子メールを送り、Microsoft Teams で通知を受け取る場合、このケースでこのフローを開始する **トリガー** となるのは、電子メールの受信です。

Power Automate はコネクタを提供し (SharePoint、Outlook、/. のようなアプリ/サービス)、ほとんどのコネクタはフローの開始に使用できる事前構築済みのトリガーを提供します。 これが、Office 365 Outlook コネクタが既定で提供するトリガーの外観の一部です。

   ![Office 365 Outlook トリガーのスクリーンショット](./media/triggers-introduction/12700a7ab29c81632d6c15024a9779e8.png)

## <a name="choose-the-right-trigger"></a>適切なトリガーを選択する

トリガーは、即時または手動で、スケジュールに従って、または他の何かが発生したときに自動的に開始されます。

### <a name="triggers-for-instantmanual-flows"></a>インスタント/手動フローのトリガー

モバイル デバイスのボタンをタップするだけでクラウド フローを実行する場合は、チームに毎日のチーム会議に参加するように通知するために、インスタント フロー (ボタン フロー) を作成します。 これらのフローは、任意のデバイスから手動でトリガーできます。 

[インスタント フローの詳細](https://docs.microsoft.com/power-automate/introduction-to-button-flows#trigger-an-instant-flow)。


### <a name="triggers-for-scheduled-flows"></a>予定フローのトリガー

毎週のプロジェクト レポートを送信する場合など、スケジュールに従ってクラウド フローを実行する場合、[予定フロー]() を作成します。 予定フローでは、いつ (日付と時刻) と頻度 (毎月/毎日/毎時など) を選択できます。 

[予定フロー](https://docs.microsoft.com/power-automate/run-scheduled-tasks) の詳細はこちらをご覧ください。

![予定フローの開始ページを示すスクリーンショット](./media/triggers-introduction//1270c8bd76f42e6531daa735a562502a.png)


### <a name="triggers-for-automated-flows"></a>自動フローのトリガー

たとえば、イベント後にタスクを自動的に実行するクラウド フローを作成する場合は、指定したキーワードを誰かがツイートしたときにメールで通知するクラウド フローを作成し、自動フローを作成します。 

[自動フロー](https://docs.microsoft.com/power-automate/get-started-logic-flow) の詳細はこちらをご覧ください

## <a name="add-a-trigger-to-an-existing-flow"></a>既存のフローにトリガーを追加する 

1. 新しいステップを追加します

1. コネクタを検索し、アプリ アイコンを選択します。

   ![コネクタの検索を示すスクリーンショット](./media/triggers-introduction/da75261b15a79f891d38b4adbe9be3f3.png)

1. 選択すると、対応するトリガーとアクションが表示されます。 ニーズに最適なトリガーを選択します。

   ![選択したコネクタのトリガーを示すスクリーンショット](./media/triggers-introduction/d869f08de1135874ed9f0dcbe6fa002d.png)

>[!IMPORTANT]
>トリガーはフローの最初のステップである必要があります。


## <a name="licensing-for-premium-connectors"></a>プレミアム コネクタのライセンス

![いくつかのプレミアム コネクタを示すスクリーンショット](./media/triggers-introduction/premium-connectors.png)

すべてのプレミアム、オンプレミス、およびカスタム コネクタにアクセスするには、スタンドアロン [Power Apps ライセンス](https://powerapps.microsoft.com/pricing/) または [Power Automate ライセンス](https://flow.microsoft.com/pricing/) が必要です。 Microsoft 365 プランのライセンシーは、標準コネクタを使用できますが、プレミアム コネクタは使用できません。

ライセンスを見つける方法は次のとおりです。

1. [flow.microsoft.com](https://preview.flow.microsoft.com/) に移動します

1. **マイ フロー** を選択します。

1. クラウド フローを選択します。

1. **詳細** セクションに移動し、**プラン** を選択します。  

   現在のライセンス プランが表示されます。

## <a name="customize-a-trigger-by-adding-conditions"></a>条件を追加してトリガーをカスタマイズする

特定の条件が満たされた場合にのみ起動するように、トリガーをカスタマイズする必要がある場合があります。 たとえば、Power Automate で SharePoint の **アイテムが作成または変更されたとき** トリガーを使用することがあります。 このトリガーは、SharePoint アイテムが変更されるたびに発生しますが、アイテムが作成されたとき、またはステータスが *承認済み* とマークされたときにのみフローをトリガーしたい場合があります。 フローに条件を追加することで他のイベントにフィルターを適用できますが、フローは引き続き実行され、呼び出しは API リクエストとしてカウントされるため、API リクエストの制限にすばやく到達できます。
これを回避するには、トリガー条件を式を記述して、トリガーの条件が満たされていない場合に *実行* を回避するようにします。

[トリガー条件の使用方法に関するコミュニティ記事](https://www.timlinenterprises.com/microsoft-power-automate-flow-trigger-conditions/) はこちらをご覧ください。

クラウド フローの実行履歴でトリガーの入力や出力を保護する必要がある場合もあります。 これを行うには、トリガーでセキュア入力やセキュア出力の設定をオンにします。 それを行う方法に関する優れたコミュニティ記事は、[こちら](https://d365demystified.com/2019/12/19/secure-input-output-in-power-automate-run-history/) を参照してください。

