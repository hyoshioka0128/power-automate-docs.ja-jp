---
title: Power Automate を使用した SharePoint ページの管理 | Microsoft Docs
description: Power Automate を使用した SharePoint ページの管理を説明します。
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
ms.date: 04/06/2020
ms.author: deonhe
ms.openlocfilehash: 8d7432ee33ec468e9958cbdd09e805db8ed043a0
ms.sourcegitcommit: a09a957460f7495c0b103e1d832f65963025fbac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2020
ms.locfileid: "3697007"
---
# <a name="manage-sharepoint-page-approvals-with-power-automate"></a>Power Automate を使用して SharePoint ページを管理する


SharePoint のサイト管理者は、Power Automate を使用して、新規または更新されたサイト ページが発行される前に承認を求めることができます。

この記事では、SharePoint サイトでフローを使用して、サイトへの変更を公開前に承認の要求を設定する方法を説明します。

## <a name="configure-sharepoint-for-page-approvals"></a>SharePoint を構成してページの承認をする

### <a name="prerequisites"></a>前提条件 

この記事のアクティビティを実行するには、 SharePoint サイトの管理者である必要があります。

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]

1. サイト管理者として SharePoint にサインインします。
1. ナビゲーション バーから **ページ** を選択します。

    ![ページの承認フローの選択](media/customize-sharepoint-page-approvals/pages.png)

1. **自動化** > **Power Automate** > **ページの承認フローの構成** を選択します。
    
    ![ページの承認フローの選択](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. **フローの作成** を選択します。

1. 場合によっては、この Power Automate テンプレートで使用されるサービスにサインインする必要があります。

1. **続行** を選択します。

1. **フロー名** を指定し、**承認者** ボックスに少なくとも 1 つの名前を入力して、**作成** を選択します。
    
    ![ページの承認フローの選択](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

OK! これで、ページが追加または変更されるたびに、フローにリストされている **承認者** に承認要求が送信されます。

ページの承認フローは他のフローと同様で、**マイ フロー** タブに一覧表示されます。

![ページの承認フローの選択](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>承認のためにページを送信する

ページの承認フローを作成したので、ページを追加または変更した人すべてが次の操作を行う必要があります:

 - サイトに (新しいページを追加するなどの) 変更を加え、変更を保存します。

     ![承認のためにページを送信する](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - だれかが変更を承認するのを待ちます。
    
    ![承認のためにページを送信する](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>ページを承認する

承認者は、ページの承認要求があるたびにメールを受信します。 メールで直接リクエストを承認するか（メールクライアントがアクション可能なメッセージに対応している場合）、メールからページを開いて確認してから SharePoint でページを承認することもできます。

## <a name="customize-page-approval-flows"></a>ページの承認フローをカスタマイズする

ページの承認ではバックグラウンドで Power Automate が使用しているため、サイト所有者はページの承認フローを使用して、フロー内の任意のカスタム ビジネス ロジックを変更、追加することができます。 フローを変更するには、サイト所有者が **フロー** 選択し、ページ ライブラリで **フローの表示** を選択してページの承認フローを見つけることができます。

## <a name="learn-more"></a>詳細はこちら

- [ページの承認フロー](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [ページの承認を構成する](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
