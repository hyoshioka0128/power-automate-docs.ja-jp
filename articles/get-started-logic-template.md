---
title: テンプレートからフローを作成する | Microsoft Docs
description: 組み込みテンプレートのいずれかからフローを作成します。
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/07/2020
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c4a5ae6a2f5b1bccc81f5e7add3b6380b01b3847
ms.sourcegitcommit: d31569a29a01119c22feaa3012761b24c426f60b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "3791313"
---
# <a name="create-a-flow-from-a-template-in-power-automate"></a>Power Automate でテンプレートからフローを作成します

多くの組み込みテンプレートのいずれかからフローを作成します。組み込みテンプレートでは、たとえば、Office 365 で上司からのメールを受け取ったときに Slack メッセージが送信されるようにすることができます。

>[!TIP]
>すでにプロセスのアイデアがあり、ちょうど良いテンプレートが見つからない場合は、[最初からフローを作成します](get-started-logic-flow.md)。

**前提条件**

* [flow.microsoft.com](https://flow.microsoft.com) のアカウント
* Slack アカウント
* Office 365 の認証情報

## <a name="choose-a-template"></a>テンプレートの選択

1. [flow.microsoft.com](https://flow.microsoft.com) で **すべてのテンプレートを検索する** 検索ボックスを選択して **Slack** と入力し、Enter キーを押します。
1. Slack に関連するテンプレートのみが表示されるので、**マネージャーからメールが届いたら Slack でメッセージを送信する** を選択できます。
   
    ![左側のナビゲーション バーの新しいオプション](./media/get-started-logic-template/select-template.png)
1. このテンプレートが目的を満たすことを確認してから **このテンプレートを使用する** を選択します。
1. Office や Slack にサインインしていない場合は **サインイン** を選択してプロンプトに従います。
   
1. 接続を確認したら **続行** を選択します。
   
    フローが表示され、オレンジ色のタイトル バーに各アクションが示されます。
   
    ![テンプレートによる既定のイベントとアクション](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>フローをカスタマイズする

1. イベントのタイトル バーを選択して展開し、カスタマイズします (たとえば必要なメールに対してフィルターを指定します)。
1. 入力する必要があるアクションは自動的に展開されます。
   
    たとえば *\@ユーザー名* などのチャネルを入力する必要があるので **メッセージを投稿する** アクションは展開されます。 メッセージ内容のカスタマイズもできます。 既定でメッセージは件名のみを含みますが、他の情報を含めることもできます。
   
1. 画面上部付近でフロー名を指定してから **フローの作成** を選択します。
1. 目的のフローが完成したら最後に **完了** を選択します。

これでマネージャーからメールを受け取ると、指定した情報を含む Slack メッセージを受信します。

## <a name="next-steps"></a>次の手順

* [実行中のフローを確認する](see-a-flow-run.md)
* [独自のテンプレートを公開する](publish-a-template.md)
* [Common Data Service で使用するテンプレートをアップロードします](common-data-model-intro.md)
* [チーム フローを開始し](create-team-flows.md)、他のユーザーを招待して一緒にフローを設計します。

