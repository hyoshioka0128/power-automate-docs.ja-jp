---
title: はじめに | Microsoft Docs
description: Power Automate を使用して、仕事や生活をすばやく自動化する方法を紹介します
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 7/29/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 114fcc8f93e5b4ac641326a80a191e3a7e7cea4d
ms.sourcegitcommit: 970ad18a7ef795bff294f39ccfc8578bab9387d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "4714057"
---
# <a name="get-started-with-power-automate"></a>Power Automate に関する入門情報 

ようこそ! Power Automate ご利用いただく目的は何ですか？ たとえば、次のようなことが実現できます :

* ビジネス プロセスを自動化する
* 期限を過ぎたタスクのリマインダーを自動送信する
* スケジュールに基づいてシステム間でビジネス データを移動する
* 約300のデータソース、または公開されている API に接続する
* Excel でのデータの計算など、ローカル コンピューターでのタスクを自動化できます。 

マウスクリック、キーストローク、コピー ペーストのステップをデスクトップから記録するだけで、反復的な手動タスクを自動化し、時間の節約ができることを考えてみてください。 Power Automate は自動化を促進します。 

<br/>

> [!VIDEO https://www.youtube.com/embed/H4H_jPJWlxU]

## <a name="who-is-power-automate-for"></a>Power Automate はどういう人に向けたものか 

*どんなスキルが必要なのか？* 基本的なビジネス ユーザーから IT のプロまで、誰でも Power Automate のノーコード/ローコード プラットフォームを使って自動化プロセスを作成することができます。

*どんな業種が Power Automate の恩恵を受けることができるか* 一部の企業が Power Automate を使用して Power Platform のソリューションをどのように実装したのかを確認してみましょう : 

  * [銀行業](https://customers.microsoft.com/en-us/story/821782-illimity-bank-banking-power-automate)
  * [Retail](https://customers.microsoft.com/en-us/story/drivetime-retail-consumer-goods-azure)
  * [製造業](https://customers.microsoft.com/en-us/story/810656-hexion-manufacturing-power-platform)
  * [保険](https://customers.microsoft.com/en-us/story/811345-aioi-nissay-dowa-insurance-microsoft-power-platform)
  * [ヘルスケア](https://customers.microsoft.com/en-us/story/vnshs-health-provider-microsoft-flow) 

[あなたの業種の例](https://customers.microsoft.com/en-us/search?sq=%22Power%20Automate%22&ff=story_product_categories%26%3EPower%20Automate&p=0&so=story_publish_date%20desc)を探してみましょう


自動化を作成する最初のステップとして、[サインアップ](sign-up-sign-in.md)をしてください。あるいはすでに Power Automate のアカウントをお持ちの場合は、[ログイン](https://flow.microsoft.com/signin)してください。

## <a name="what-are-the-different-types-of-flows"></a>フローには何の種類がありますか?

タスクを自動化するために作成できるさまざまなタイプのフローの詳細については、[フロー タイプ](flow-types.md) の記事を参照してください。

## <a name="check-out-the-start-page"></a>スタート ページを確認する 

Power Automate の[スタート ページ](https://flow.microsoft.com)では、[さまざまなテンプレートが用意されている](https://flow.microsoft.com/templates) ほか、Power Automate. のいくつかの主要な機能について説明されています。 Power Automate で何ができるか、またビジネスや普段の生活にどのように役立つかを簡単に把握することができます。

各テンプレートは、特定の目的のために設計されています。 たとえば、上司から電子メールが届いたときにテキスト メッセージを送信したり、Twitter の潜在顧客を Dynamics 365 に追加したり、ファイルをバックアップしたりするためのテンプレートがあります。 これらのテンプレートは氷山の一角にすぎません。 必要なプロセスに最適にカスタマイズされたフローを作成するよう促すことを目的としています。

## <a name="create-your-first-flow"></a>最初のフローの作成 

1. 目的に合ったテンプレートを選択します。 単純なテンプレートの 1 つに、[**メールで毎日リマインダーを受け取る**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/) があります:

    ![毎日のリマインダーのテンプレート](./media/getting-started/template-details.png)

1. **続行** を選択します。

    ![接続の作成](./media/getting-started/create-connection.png)

1. 毎日のリマインダーを送信する電子メール アドレスを入力します。 次に、リマインダーのメッセージを入力します。 最後に、**フローの作成** を選択し、フローが想定どおりに実行されることを確認します。

    ![接続の資格情報の入力](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > フローをトリガーする条件と、そのイベントから発生するアクションを確認できます。 さまざまな設定を試して、フローをカスタマイズします。 アクションを追加または削除することもできます。

1. **完了** を選択します。

[このチュートリアルに従い](get-started-logic-template.md)、テンプレートからフローを作成する方法の詳細を確認してください。

## <a name="get-creative"></a>クリエイティブになる

テンプレートから最初のフローを作成したら、Power Automate  でサポートされる [380 を超えるデータ ソース](https://flow.microsoft.com/connectors/) のいずれかを使って、[独自のフローをゼロから作成します](get-started-logic-flow.md)。

![クラウド フローをビルディング](./media/getting-started/build-a-flow.png)

最初からクラウド フローを作成するときは、ワークフロー全体を制御します。 開始するためのアイデアをいくつか示します:

- [多くのステップが含まれるフロー](multi-step-logic-flow.md)。
- [スケジュールに従ってタスクを実行します](run-scheduled-tasks.md)。
- [承認フローを作成します](wait-for-approvals.md)。
- [実行中のクラウド フローを確認](see-a-flow-run.md)。
- [テンプレートを発行します](publish-a-template.md)。
- [Microsoft Teams のテンプレートから フローを作成する](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/)。


## <a name="peek-at-the-code"></a>コードのプレビュー

Power Automate には **ピーク コード** 機能があり、クラウド フロー内のあらゆるアクションとトリガーに対して生成されるコードを誰でも詳しく調べることができます。開発者でなくてもフローを作成できます。 コードをプレビューすることで、トリガーやアクションで使用されているデータに対する理解度が上がります。 フローに対して生成されたコードは、Power Automate デザイナー内から次の手順でプレビューできます。 

1. **アクション** または **トリガー** の右上隅にある **...** メニュー項目を選択します。 
1. **コードのプレビュー** を選択します。

    ![コードのプレビュー](media/getting-started/peek-code.png)

1. アクションとトリガーが完全に JSON で表現されていることにご注目ください。 これには、ユーザーが直接入力するテキストや使用されている式など、あらゆる入力が含まれます。 ここで式を選択し、**動的コンテンツ** 式エディターに貼り付けます。 必要なデータがフローに存在することも確認できます。

    ![コードの詳細を確認する](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>フローを簡単に見つける

あなたの創作意欲が *流れ* 始めたら、たくさんのフローが作られるかもしれません。 ご心配なく、フローは簡単に見つけられます - **マイ フロー**、**チーム フロー**、**接続**、または **ソリューション** 画面の検索ボックスを使用すれば、入力した単語に一致するフローのみが表示されます。

![フィルターまたは検索フロー](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> 検索フィルターでは、ページに読み込まれているフローのみが見つかります。 自分のフローが見つからない場合、ページの下部にある **さらに読み込む** を選択してみてください。

## <a name="get-notifications-when-somethings-wrong"></a>問題が発生したときに通知を受け取る

(デザイナーの右上にある) Power Automate 通知センターを利用すると、最近エラーを出したフローを簡単に一覧表示できます。 この通知センターには、最近エラーを出したエラーの数を示す数値が表示されます。

通知センターから、Power Automate の **アクティビティ**  ページに移動すると、最近実行されたフロー、通知が送信されたフロー、エラーを出したフローをすべて表示できます。

![通知センター](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>モバイル アプリを使用する 

[Android](https://aka.ms/flowmobiledocsandroid)、 [iOS](https://aka.ms/flowmobiledocsios)、[Windows Phone](https://aka.ms/flowmobilewindows) 用の Power Automate モバイル アプリをダウンロードします。 このアプリを使用して、[フローのアクティビティを監視](mobile-monitor-activity.md) し、[フローを管理](mobile-manage-flows.md) し、[テンプレートからフローを作成](mobile-create-flow.md) します。

## <a name="get-help-planning-your-power-automate-projects"></a>Power Automate プロジェクト計画の助けを得る

Power Automate プロジェクトを開始する準備ができたら、[ガイダンスおよび計画の記事](./guidance/planning/introduction.md)にアクセスして、すばやく実行してください。

## <a name="were-here-to-help"></a>サポート情報 

マイクロソフトでは、Power Automate に関する皆様のご意見をお待ちしております。また、 Microsoft Flow が皆様のお役に立つことを心より願っております。 [ガイド付き学習](https://flow.microsoft.com/guided-learning/) のチュートリアルを確認したり、[コミュニティに参加](https://go.microsoft.com/fwlink/?LinkID=787467) して質問したり、アイデアを交換したりすることもできます。 問題が発生した場合は、[サポートにお問い合わせください](https://go.microsoft.com/fwlink/?LinkID=787479)。
