---
title: トリガーでの一般的な問題のトラブルシューティング | Microsoft Docs
description: フローが実行されない場合の問題を見つけて修正します。
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
ms.date: 11/19/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowadmin
ms.openlocfilehash: baa5e62dbebec90142ff72f9fc86529c7c121e8e
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709783"
---
# <a name="troubleshoot-common-issues-with-triggers"></a>トリガーでの一般的な問題のトラブルシューティング

トリガーの問題をトラブルシューティングするためのヒントとテクニックを以下に示します。

## <a name="my-trigger-doesnt-fire"></a>トリガーが発生しない

1. データ損失防止ポリシーが原因である場合があります。

   管理者が [データ損失防止 (DLP)](https://docs.microsoft.com/power-platform/admin/wp-data-loss-prevention) ポリシーを作成すると、ユーザーが誤って組織データを露出してしまうことを防止するためのガートレールとしてポリシーを機能させることができます。 DLP ポリシーでは、**ビジネス** または **非ビジネス** のいずれかとして分類することによって、コネクタを同時に使用できるルールを適用します。 **ビジネス** グループにコネクタを置くと、付与された任意のアプリまたはフロー内のそのグループとは別のコネクタでのみ使用できます。

   フローが DLP ポリシーに違反している場合、フローは一時停止され、トリガーは発生しなくなります。 フローが一時停止されているかどうかを確認するには、フローを編集して保存を試みます。 フローが DLP ポリシーに違反している場合、フロー チェッカーはレポートを送信します。 管理者は DLP ポリシーを変更することができます。

1. トリガーが失敗していることがあります。

   確認する方法は次のとおりです。
   
   1. **マイ フロー** に移動し、フローを選択します。
   1. **詳細** で次のエラーが表示されていますか?

      ![フローのトリガーに関するエラー メッセージのスクリーンショット。](./media/triggers-introduction//e6cbe67c63044f382cfacaf3b20e8e89.png)

   このエラーは、Power Automate がトリガーを登録するための接続を確立するために複数回試行しましたが、失敗したことを意味します。 この問題が解決されるまで、フローはトリガーされません。

   一般的な失敗の理由の 1 つは、Power Automate サービスのエンドポイントが許可リストの一部でないことです。 これを修正するために、IT 部門がこれらのエンドポイントを許可リストに追加していることを確認してください。

   許可リストに追加する必要のある [IP アドレス](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config%23ip-addresses) および [ドメイン](https://support.microsoft.com/help/4557620/client-request-aborted-or-failed-to-fetch-error-in-power-automate) のリストを次に示します。

   トリガーの問題を修正する方法の詳細については、こちらの [サポート情報記事](https://support.microsoft.com/help/4540228/there-is-a-problem-with-the-flow-s-trigger) を参照してください。

   
<!--todo, what's this about-->
<!-- Make sure access to OData is enabled. -->

問題が解決したら、フローを変更して保存し、元に戻してからもう一度保存します。 フローは構成が変更されたことを認識し、トリガーの登録を再試行します。

### <a name="verify-connections"></a>接続を検証する

既定の設定では、ユーザーは接続に 1 回だけログインする必要があります。 それから、管理者によって取り消されるまでその接続を使用することができます。考えられるシナリオは、接続に対するパスワードが期限切れになる可能性があるか、特定の時間の後のコネクタのログイン トークンの有効期限を設定するポリシーが組織に存在する可能性があるということです。 トークンの有効期限ポリシーが Azure Active Directory で構成されました。 詳細については、この [Azure の記事](https://docs.microsoft.com/azure/active-directory/develop/active-directory-configurable-token-lifetimes) またはこの [サポート情報記事](https://support.microsoft.com/help/4467879/conditional-access-and-multi-factor-authentication-in-flow) を確認してください。

接続が切断されているかどうかを確認する方法は次のとおりです。

1. Power Automate にサインインします。
1. **データ** > **接続** に移動します。
1. フローで使用されている接続を検索します。 
1. **接続の修正** を選択し、**状態** 列の横に **接続の修正** メッセージがある場合は、接続の資格情報を更新します。

   ![切断された接続を修正するためのリンクを表示するスクリーンショット](./media/triggers-introduction/9de1dc46f08b7848f7080f4998f6b243.png)

### <a name="verify-if-the-flow-uses-a-premium-connector-trigger"></a>フローがプレミアム コネクタ トリガーを使用しているかどうかを確認する

1. フローを編集し、トリガーのコネクタ名を見つけます。 
1. [コネクタの一覧](https://preview.flow.microsoft.com/connectors) に移動し、そのコネクタを検索します。 コネクタがプレミアム コネクタの場合、コネクタの名前の下に表示されます。

   ![プレミアム コネクタのスクリーンショット](./media/triggers-introduction/e6ebe2c0d4ad3426355413e3b3af20a9.png)

すべてのプレミアム、オンプレミス、およびカスタム コネクタにアクセスするには、Power Apps のスタンドアロン ライセンス、または Power Automate ライセンス が必要です。 いつでも [新しいライセンスを購入](https://flow.microsoft.com/pricing) できます。

### <a name="check-your-license-type"></a>ライセンスの種類を確認する

所有しているライセンスの種類を表示する方法は次のとおりです。

- ナビゲーション タブの **マイ フロー** に移動します。
- フローを選択します。
- **詳細** セクションで、**プラン** を見つけます。 現在のライセンスのプランが一覧表示されます。

### <a name="verify-if-trigger-check-is-skipped"></a>トリガー チェックがスキップされているかどうかを確認する 

フローをトリガーするはずのイベント (新しいリスト項目を追加した、または電子メールを送信したなど) を完了しましたが、フローは実行されませんでした。

ナビゲーション ウィンドウの **マイ フロー** に移動し、フローを選択します。 **28 日間の実行履歴** で、**すべての実行** を選択します。

![すべての実行を示すスクリーンショット](./media/triggers-introduction/0b3aabbeee50e1f06e4a6003d5b2d976.png)

フローが実行されることを期待しているのに実行されなかった場合、その時点でトリガー チェックがスキップされたことを示しているかどうか確認してください。 トリガー チェックがスキップされた場合、フローがトリガーされるためのトリガー条件が満たされていません。 フローの入力とトリガー条件を確認し、最新の構成を使用してフローをトリガーしていることを確認します。


### <a name="verify-inputs-and-trigger-conditions"></a>入力とトリガー条件を確認する 

場合によっては、入力とトリガー条件によって障害が発生することがあります。 次の手順に従って、入力と条件を確認してください。

1. フローを編集します。
1. 最初のカードを展開し、トリガーで使用されているフォルダー、サイト、メールボックスなどを確認します。
1. カードの省略記号 (…) を選択します

   ![設定にアクセスする方法を示すスクリーンショット](./media/triggers-introduction/3b39950101ca05b737d04b77b38adec7.png)

1. **設定** を選択します。

   ![設定を示すスクリーンショット](./media/triggers-introduction/e5f660f5a0340aac26f67fd2df8b8440.png)
   
1. **トリガー条件** を検索します。 

   フィールドが空の場合、追加のカスタマイズがなく、カードのタイトル (この場合は、**アイテムが作成または変更されたとき**) がいつトリガーが発生するかを示していることを意味しています。
   
   **トリガー条件** に追加のカスタマイズがある場合、期待されるまたは正しい入力を使用してフローをトリガーしていることを確認します。

   ![トリガー条件を示すスクリーンショット](./media/triggers-introduction/eb624aa6e4c6da26f650c0f00628a7f9.png)

### <a name="check-permissions"></a>アクセス許可を確認する

トリガーで使用されるフォルダー、サイト、またはメールボックスにアクセスできることを確認します。 たとえば、Power Automate を介して共有受信トレイから電子メールを送信できるようにするには、共有受信トレイを介して電子メールを送信するアクセス許可が必要です。 Outlook の共有メールボックスから電子メール送信をテストします。

### <a name="verify-if-admin-mode-is-turned-on"></a>管理者モードがオンになっているかどうかを確認する 

環境の管理者モードがオンになっている場合、フローを含むすべてのバックグラウンド プロセスがオフになり、フローはトリガーされなくなります。

管理者モードを無効にするには、次の手順に従います。

1. Power Platform 管理者センターに移動し、環境管理者またはシステム管理者ロールの資格情報を使用してサインインします。
1. 左のメニューから、**環境**、次にサンドボックスまたは運用環境を選択します。
1. **詳細** ページで、**編集** を選択します。
1. **管理者** モードで、**無効** から **有効** へ切り替えます。
1. オプションで、バックグラウンド操作およびカスタム メッセージを設定することができ、次に保存するを選択します。

すべてが適切に処理されているように見えてもフローがトリガーされない場合、すべての手順の後にフローがトリガーされるかどうか確認してください。

### <a name="try-these-steps"></a>次の手順を試します。

1. フローを手動でテストします。
1. トリガーを削除し、再度追加します。
1. 接続を切り替えます。
1. フローをオフにしてからオンにします。
1. フローを [エクスポートしてからインポート](https://flow.microsoft.com/blog/import-export-bap-packages) します。
1. フローのコピーを作成します。
1. 電子メールが特定のフォルダーに届く時など、トリガーが特別な条件を使用する場合、フォルダーを削除してから、もう一度追加します。


## <a name="my-trigger-is-firing-for-old-events"></a>トリガーが古いイベントに対して発生する

トリガーには 2 つのタイプ &mdash; ポーリング トリガーまたは Webhook トリガーがあります。

フローをオフにしてからオンに戻すと、トリガーの種類によっては、古いトリガーが処理されることがあります。 

ポーリング トリガーは定期的にサービスを呼び出して新しいデータを探しますが、Webhook トリガーはサービスからの新しいデータのプッシュに応答します。 

フローがオンに戻ったときにどのように応答するかについては、次の表を確認してください。

|    |                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| トリガーの種類                            | 内容                                                                                                                                  |
| **定期的なアイテム** トリガーなどのポーリング | フローが再度オンになったときに、未処理/保留中のイベントがすべて処理されます。 フローをオンに戻したときに保留中のアイテムを処理しない場合は、フローを削除してから再作成します。 |
| Webhook                                 | フローが再度オンになったとき、フローがオンになってから生成された新しいイベントが処理されます。                               |


フローで使用されているトリガーの種類を確認する方法は次のとおりです。

1. フローの … (省略記号) を選択し、**ピーク コード** を選択します。

   ![ピークコードのスクリーンショット](./media/triggers-introduction/ce92dd95ccb32fbde3b6244f2d0fb7f7.png)

1. 間隔頻度の要素のある定期的なアイテム セクションを見つけます。 このセクションが使用可能な場合、トリガーはポーリング トリガーです。

   ![定期的なアイテム セクションのスクリーンショット](./media/triggers-introduction/eaf2f2a781a91fa960fce316b0773f3f.png)

## <a name="my-recurrence-trigger-runs-ahead-of-schedule"></a>定期的なアイテムのトリガーが予定より早く実行される

[開始時間を設定](https://powerusers.microsoft.com/t5/Using-Flows/Recurrence-set-for-10-but-ran-at-9-22/m-p/241400) し、その時点でのみ実行されることを確認してください。

## <a name="theres-a-delay-before-my-trigger-fires"></a>トリガーが発生するまでに遅延があります

トリガーがポーリング トリガーの場合、定期的に起動して、新しいイベントが発生したかどうか確認します。  起動時間は、フローが実行されるライセンス プランによって異なります。 

たとえば、**無料** ライセンス プランの場合、フローを実行できるのは 15 分ごとになります。 **無料** ライセンス プランで、前回の実行から 15 分が経過しないうちにクラウド フローがトリガーされた場合、フローは 15 分が経過するまでキューに入れられます。 

ライセンスが **Office 365 用フロー** プラン (Enterprise ライセンス E3、E5 などから)、または **Dynamics 365 用フロー** の場合、フローは 5 分が経過するまで再び実行されません。 したがって、トリガー イベントが発生する時間からフローが開始する時間まで、数分かかることがあります。 

トリガーの起動頻度を確認する方法は次のとおりです。

1. フロー トリガーに移動し、… (省略記号) を選択します。
1. **コードのプレビュー** を選択します。

   ![ピーク コード設定のスクリーンショット](./media/triggers-introduction/ce92dd95ccb32fbde3b6244f2d0fb7f7.png)

1. 間隔頻度を見つけます。

   ![頻度要素のスクリーンショット](./media/triggers-introduction/eaf2f2a781a91fa960fce316b0773f3f.png)

フローがトリガーされるまでに予想よりも非常に長い時間がかかる場合、最も可能性の高い 2 つの理由は次のとおりです。

1. コネクタまたはフローへの呼び出しが多すぎて、調整が発生した。 フローが調整中かどうかを確認するには、フローを手動でテストして、すぐにトリガーされるかどうか確認します。 すぐにトリガーされる場合、調整中ではありません。

   さらに、Power Automate アクション分析を確認することができます。 アクション分析の詳細については、この [ブログ](https://flow.microsoft.com/blog/introduction-action-usage-analytics-in-power-automate/) を確認してください。

   フローが頻繁に調整される場合、使用するアクションが少なくなるようにフローを再設計してください。
[プラン制限および使用するアクションが少なくなるようにフローを最適化するヒント](https://support.microsoft.com/help/4531688/troubleshooting-slow-running-flows) に関する詳細については、こちらをご覧ください。


   追加のヒントは次のとおりです。

   1. ユーザーごとのライセンスまたは Flow ごとのライセンスを取得します。 取得したら、フローを開いて再度保存し、関連付けられている権利を更新して、調整モードを変更します。

   1. フローをいくつかのインスタンスに分割します。 フローがデータを処理する場合、このデータをサブセットに分割することができます (国ごと、ビジネス エリアごとなど)。

   1. この後、フローで **名前を付けて保存** を使用し、それぞれ独自のデータを処理するいくつかのインスタンスを作成します。 クォータはフローごとであるため、これは回避策として使用することができます。

2. 反応からトリガー イベントへの Power Automate を妨げる通信の問題がありました。 サービスの停止、ポリシーの変更、パスワードの有効期限などが原因で、遅延が発生した可能性があります。 アクティブな停止があるかどうか [確認](https://admin.powerplatform.microsoft.com/support) することができます。 ブラウザーのキャッシュをクリアしてから再試行することもできます。

## <a name="dynamics-365-connector-trigger-issues"></a>Dynamics 365 Connector のトリガーの問題 

遅延 - [Dynamics 365](https://docs.microsoft.com/connectors/dynamicscrmonline/) のコネクタ トリガーの実行には最大 2 時間かかることがあります。 このコネクタは非推奨なので、フローを移行して [Microsoft Dataverse](https://docs.microsoft.com/connectors/commondataservice/) を使用することをお勧めします。

マイ フローが一覧表示されない - Power Automate メニューで、**レコードが Common Data Service を選択しているとき** トリガーで始まり、そのエンティティを参照しているトリガーまたはアクションが少なくとも 1 つ含まれているフローしか一覧表示されない。 他の種類のトリガー (自動、スケジュールなど) を含むフローは、Dynamics 365 には一覧表示されません。 

[Power Platform 管理センター](https://admin.powerplatform.microsoft.com/environments) でこれらのフローにアクセスすることもできます。

1. [Power Platform 管理センター](https://admin.powerplatform.microsoft.com/environments) にサイン インします。
1. **環境** を選択します。
1. フローを含む環境を選択します。
1. **リソース** セクションの下の **フロー** を選択します。

>[!IMPORTANT]
>これらのフローを検索する前に、[Power Automate](https://docs.microsoft.com/power-platform/admin/enable-embedded-flow-in-your-organization#enable-or-disable-power-automate-in-your-organization) を有効にする必要があります。

## <a name="power-apps-apps-trigger-issues"></a>Power Apps アプリのトリガーの問題

<!--todo: steps are not clear-->
クラウド フローでアクションの名前を変更できない – これは Power Apps トリガーを使用するフローに関する既知の問題です。 アクションの名前を変更するための回避策として、トリガーを削除します。 アクションの名前を変更して、Power Apps トリガーを追加し、必要に応じて変数を構成します。

Power Apps アプリが公開されたら、更新を行う Power Apps アプリで使用されるフローのコピーを作成します。 公開された Power Apps アプリによって参照されるクラウド フローへの更新により、既存のユーザーが切断される可能性があります。 すべてのユーザーが新しく公開されたバージョンの Power Apps アプリにアップグレードするまで、既存のフローを削除またはオフにしないでください。

## <a name="sharepoint-trigger-issues"></a>SharePoint のトリガーの問題

たとえば、SharePoint トリガーについては、サブフォルダーでファイルが追加または更新された場合、**ファイルが作成または変更されたとき** は発生しません。 サブフォルダーでトリガーするフローが必要な場合、複数のフローを作成します。

## <a name="my-flow-triggers-multiple-times"></a>マイ フローが複数回トリガーされる

別の環境で同じ条件に基づいてトリガーされるアクティブなフローのコピーがないことを確認します。 トリガー条件を使用してトリガーをカスタマイズし、トリガーの回数を減らします。

## <a name="users-are-unable-to-run-flows-that-are-shared-to-them-but-the-owner-can-run-the-flow"></a>共有されているフローをユーザーは実行できないが、所有者はフローを実行できる

次のいずれかの方法を試すことができます。

1. 接続を修正、または更新します。

   フローが **手動** トリガーを使用する場合、フローをトリガーしようとするユーザーの接続が必要です。 **繰り返し** トリガーを使用する場合、フロー作成者の接続上で実行することができます。

1. ユーザーがフローの接続に対して適切なライセンスを持っていることを確認してください。

   ユーザーが、保存、オフなどのアクションを実行するには Power Automate ライセンスが必要です。Power Apps、Dynamics 365、または Office 365 ライセンスでは十分ではありません。 プレミアム コネクタを使用するフローを共有されるユーザーは、フローの編集または手動のトリガーを実行するのにそれぞれ Power Automate の **ユーザーごと** または **フローごと** のライセンスが必要です。 ユーザーが以前にフローの保存や変更ができた場合は、ライセンスの期限が切れている可能性があります。
   
   または、**ユーザーごと** の90 日間の試用を開始することができますが、その後は、プレミアム コネクタを使用するフローの実行や編集を行うのに有料プランが必要になります。 詳細については、[ライセンス ページ](https://flow.microsoft.com/pricing) または この [サポート情報記事](https://support.microsoft.com/help/4552636/error-user-does-not-have-a-service-plan-adequate-for-the-non-standard) を参照してください。
