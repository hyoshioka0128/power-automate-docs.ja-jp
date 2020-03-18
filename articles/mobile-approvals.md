---
title: モバイル デバイスで要求を承認する | Microsoft Docs
description: モバイル デバイスを使用して、Power Automate で作成された要求を承認します。
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
ms.date: 07/20/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 513200d18ac2a845cd63a6d269513f3bcb45118c
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193981"
---
# <a name="approve-requests-on-your-mobile-device-by-using-power-automate"></a>Power Automate を使用してモバイル デバイスで要求を承認する

フローによって承認者として識別された場合、Power Automate 用のモバイル アプリがインストール済みであると、承認を要求されるたびにプッシュ通知を受け取ります。

この記事では、Power Automate 用のモバイル アプリで承認要求を管理するときに、発生する可能性があるいくつかの一般的なシナリオについて説明します。

> [!NOTE]
> このトピックで示すイメージは、Android デバイスからのものですが、iOS でのエクスペリエンスもほぼ同じです。
> 
> 

## <a name="prerequisites"></a>前提条件
このチュートリアルを完了するには、次のことが必要です。

* Power Automate 用のモバイル アプリを実行している [Android](https://aka.ms/flowmobiledocsandroid) または [iOS](https://aka.ms/flowmobiledocsios) デバイス。
* 承認フローの承認者として指定される。
* 承認待ちの要求。

## <a name="view-pending-requests"></a>承認待ちの要求を表示する
1. Power Automate 用のモバイル アプリを開きます。
   
    ![モバイル アプリを起動する](./media/mobile-approvals/open-app.png)
2. 右上隅の **[承認]** を選択します。
   
    ![[承認] を選択する](./media/mobile-approvals/select-approvals.png)
3. 承認待ちの要求をすべて表示する:
   
    ![承認待ちの要求を表示する](./media/mobile-approvals/show-pending-approval-requests.png)

承認待ちの要求がない場合は、[承認フロー](modern-approvals.md)を作成し、自分自身を承認者として設定し、フローをトリガーします。 フローがトリガーされ承認の要求が送信されると、その数秒後に、承認センターに承認要求が表示されます。

## <a name="approve-requests-and-leave-an-optional-comment"></a>要求を承認し、必要に応じてコメントを残す
1. そのようにしていない場合は、上記の手順に従って[承認待ちの要求を表示](mobile-approvals.md#view-pending-requests)します。
2. 承認する要求に対して **[承認]** を選択します。
   
    ![承認を選択する](./media/mobile-approvals/select-approve.png)
3. (省略可能) **[コメントの追加]\(省略可能)** を選択します。
   
    ![コメントの追加を選択する](./media/mobile-approvals/select-add-comment.png)
   
    **[コメントの追加]** 画面にコメントを入力します。
   
    ![コメントを入力する](./media/mobile-approvals/enter-comment-for-approval.png)
4. 右上隅にある **[確認]** を選択します。
   
    ![完了したことを確認する](./media/mobile-approvals/tap-confirm-button.png)
   
    意思決定の内容をフローが記録すると、成功画面が表示されます。
   
    ![成功画面](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>要求を却下し、必要に応じてコメントを残す
[要求を承認する手順](mobile-approvals.md#approve-requests-and-leave-an-optional-comment)に従いますが、2 番目の手順で **[却下]** を選択します。

## <a name="learn-more"></a>詳細情報
[最新の承認フローを作成する](modern-approvals.md)。

