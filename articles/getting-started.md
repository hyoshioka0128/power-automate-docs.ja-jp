---
title: はじめに | Microsoft Docs
description: Power Automate を使用して、仕事や生活をすばやく自動化する方法を紹介します
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/05/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ace2fc20c5ce4eb17015a632308101b2efcc1e2b
ms.sourcegitcommit: ab26d3b17cc34c650298ec5ac3b4ea9554e291cf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2020
ms.locfileid: "3502341"
---
# <a name="get-started-with-power-automate"></a>Power Automate に関する入門情報 

ようこそ! Power Automate は、よく使うアプリやサービスとの間で自動ワークフローを作成し、ファイルの同期、通知の受信、データの収集などを実行できるようにするためのサービスである。

<br/>

> [!VIDEO https://www.youtube.com/embed/hCuxuUaGC6Y]


## <a name="types-of-flows"></a>フローの種類

Power Automate は Power Platform を支える柱の 1 つであり、 ワークフローおよびプロセスの自動化のためのローコード プラットフォームを提供する。 さまざまな種類のフローをまとめると以下のようになります:

| **フローの種類**                                                                       | **ユース ケース**                                                                                  | **対象**                                                                             |
|-------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| [自動化されたフロー](get-started-logic-flow.md)                 | イベントによってトリガーされたら 1 つまたは複数のタスクを自動的に実行するフローを作成します。 | クラウドまたはオンプレミスのサービス向けの [コネクタ](https://docs.microsoft.com/connectors/)。 |
| [ボタン フロー](introduction-to-button-flows.md)              | モバイル デバイスでいつでも、どこからでも繰り返しタスクを実行します。                        |                                                                                        |
| [スケジュールされたフロー](run-scheduled-tasks.md)                    | スケジュール上で1つ以上のタスクを実行するフローを作成します。             |                                                                                        |
| [業務プロセス フロー](business-process-flows-overview.md) | 望む結果を得るためにユーザーが従うべき一連の手順を定義します。                 | 人的プロセス                                                                        |
| [UI フロー](ui-flows/overview.md)                                                | 従来のソフトウェアで行われていた手動ステップを記録し自動再生します。                    | 自動化に API を利用できないデスクトップと Web アプリケーション。    |

フローはすべて、Power Automate の **マイ フロー** タブで作成し、管理できます。

Dynamics 365 ユーザーの場合、[ワークフロー](configure-workflow-steps.md)、[アクション](create-actions.md)、 [モバイル タスク フロー](create-mobile-task-flow.md)、[ダイアログ](use-cds-for-apps-dialogs.md) など、従来の Common Data Service  プロセスに慣れている場合も考えられます。

まずは [サインアップ](sign-up-sign-in.md) してください。既に Power Automate のアカウントをお持ちの場合は、タブレットやデスクトップ コンピューター、さらにはスマートフォンで[サインイン](https://flow.microsoft.com/signin)できます。

## <a name="check-out-the-start-page"></a>スタート ページを確認する ##

Power Automate の[スタート ページ](https://flow.microsoft.com)では、[さまざまなテンプレートが用意されている](https://flow.microsoft.com/templates) ほか、Power Automate. のいくつかの主要な機能について説明されています。 Power Automate で何ができるか、またビジネスや普段の生活にどのように役立つかを簡単に把握することができます。

Power Automate では、次のことが可能です。

- テンプレートとサービスを簡単に検索できます。

    ![Flow のスタート ページ 1](./media/getting-started/flowhome1.png)

- 特に人気のあるサービスから選択できます。

    ![Flow のスタート ページ 2](./media/getting-started/flowhome2.png)

- 各フローの概要を参照できます。

    ![Flow のスタート ページ 3](./media/getting-started/flowhome3.png)

各テンプレートは、特定の目的のために設計されています。 たとえば、上司から電子メールが届いたときにテキスト メッセージを送信したり、Twitter の潜在顧客を Dynamics 365 に追加したり、ファイルをバックアップしたりするためのテンプレートがあります。 これらのテンプレートは氷山の一角にすぎません。 必要なプロセスに最適にカスタマイズされたフローを作成するよう促すことを目的としています。

## <a name="create-your-first-flow"></a>最初のフローの作成 ##

1. 目的に合ったテンプレートを選択します。 単純なテンプレートの 1 つに、[**メールで毎日リマインダーを受け取る**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/) があります:

    ![毎日のリマインダーのテンプレート](./media/getting-started/template-details.png)

1. **続行** を選択します。

    ![接続の作成](./media/getting-started/create-connection.png)

1. 毎日のリマインダーを送信する電子メール アドレスを入力します。 次に、リマインダーのメッセージを入力します。 最後に、**フローの作成** を選択し、フローが想定どおりに実行されることを確認します。

    ![接続の資格情報の入力](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > フローをトリガーする条件と、そのイベントから発生するアクションを確認できます。 さまざまな設定を試して、フローをカスタマイズします。 アクションを追加または削除することもできます。

1. **完了**を選択します。

[このチュートリアルに従い](get-started-logic-template.md)、テンプレートからフローを作成する方法の詳細を確認してください。

## <a name="get-creative"></a>クリエイティブになる ##

テンプレートから最初のフローを作成したら、Power Automate  でサポートされる [150 を超えるデータ ソース](https://flow.microsoft.com/connectors/) のいずれかを使って、[独自のフローをゼロから作成します](get-started-logic-flow.md)。

![フローの構築](./media/getting-started/build-a-flow.png)

最初からフローを作成するときは、ワークフロー全体を制御します。 開始するためのアイデアをいくつか示します:

- [多くのステップが含まれるフロー](multi-step-logic-flow.md)。
- [スケジュールに従ってタスクを実行します](run-scheduled-tasks.md)。
- [承認フローを作成します](wait-for-approvals.md)。
- [実行中のフローを確認します](see-a-flow-run.md)。
- [テンプレートを発行します](publish-a-template.md)。
- [Microsoft Teams のテンプレートから フローを作成する](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/)。


## <a name="peek-at-the-code"></a>コードのプレビュー

Power Automate には**コードのプレビュー** 機能があり、フロー内のあらゆるアクションとトリガーに対して生成されるコードを誰でも詳しく調べることができます。開発者でなくてもフローを作成できます。 コードをプレビューすることで、トリガーやアクションで使用されているデータに対する理解度が上がります。 フローに対して生成されたコードは、Power Automate デザイナー内から次の手順でプレビューできます。 

1. **アクション** または **トリガー** の右上隅にある **...** メニュー項目を選択します。 
1. **コードのプレビュー** を選択します。

    ![コードのプレビュー](media/getting-started/peek-code.png)

1. アクションとトリガーが完全に JSON で表現されていることにご注目ください。 これには、ユーザーが直接入力するテキストや使用されている式など、あらゆる入力が含まれます。 ここで式を選択し、**動的コンテンツ** 式エディターに貼り付けます。 必要なデータがフローに存在することも確認できます。

    ![コードのプレビュー](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>フローを簡単に見つける

あなたの創作意欲が *流れ* 始めたら、たくさんのフローが作られるかもしれません。 ご心配なく、フローは簡単に見つけられます - **マイ フロー**、**チーム フロー**、**接続**、または **ソリューション** 画面の検索ボックスを使用すれば、入力した単語に一致するフローのみが表示されます。

![フィルターまたは検索フロー](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> 検索フィルターでは、ページに読み込まれているフローのみが見つかります。 自分のフローが見つからない場合、ページの下部にある **さらに読み込む** を選択してみてください。

## <a name="get-notifications-when-somethings-wrong"></a>問題が発生したときに通知を受け取る

(デザイナーの右上にある) Power Automate 通知センターを利用すると、最近エラーを出したフローを簡単に一覧表示できます。 この通知センターには、最近エラーを出したエラーの数を示す数値が表示されます。

通知センターから、Power Automate の **アクティビティ**  ページに移動すると、最近実行されたフロー、通知が送信されたフロー、エラーを出したフローをすべて表示できます。

![通知センター](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>モバイル アプリを使用する ##

[Android](https://aka.ms/flowmobiledocsandroid)、 [iOS](https://aka.ms/flowmobiledocsios)、[Windows Phone](https://aka.ms/flowmobilewindows) 用の Power Automate モバイル アプリをダウンロードします。 このアプリを使用して、[フローのアクティビティを監視](mobile-monitor-activity.md) し、[フローを管理](mobile-manage-flows.md) し、[テンプレートからフローを作成](mobile-create-flow.md) します。

## <a name="were-here-to-help"></a>サポート情報 ##

マイクロソフトでは、Power Automate に関する皆様のご意見をお待ちしております。また、 Microsoft Flow が皆様のお役に立つことを心より願っております。 [ガイド付き学習](https://flow.microsoft.com/guided-learning/) のチュートリアルを確認したり、[コミュニティに参加](https://go.microsoft.com/fwlink/?LinkID=787467) して質問したり、アイデアを交換したりすることもできます。 問題が発生した場合は、[サポートにお問い合わせください](https://go.microsoft.com/fwlink/?LinkID=787479)。
