---
title: Power Automate 用語集 | Microsoft Docs
description: Power Automate で使用する用語集
services: ''
suite: flow
documentationcenter: na
author: nijemcevic
manager: ''
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/18/2020
ms.author: tatn
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 84ea94aa7628b5b23b4c0e45157c6406dff4a3ea
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709495"
---
# <a name="power-automate-glossary"></a>Power Automate用語集

次の用語は Power Automate で一般的に使用します。

## <a name="a"></a>A

**アクション:** アクションとは、トリガーを呼び出した際に開始するタスクです。 特定のフローを完了するために必要なものに応じて、フローに 1 つまたは複数のアクションを含めることができます。 アクションを使用して **作成**、**更新**、**削除**、**割り当て** などの操作を実行できます。

 [アクションを追加します](multi-step-logic-flow.md)

**アクション アイテム**: **アクション アイテム** 画面には、承認ステータスとビジネス プロセス フローが表示されます。 アクション アイテムは Power Automate の左側のナビゲーション ウィンドウにあります。

**承認 (承認リクエスト):** 承認とは、クラウド フローを承認する際のアクションを指します。 これは基本的な承認または拒否のアクションです。 これは複数の選択肢を含む任意の承認を送信者が要求できる、カスタム承認フローです。 承認ワークフローを作成する場合は、承認アクションを追加します。 このアクションを追加すると、フローでドキュメントまたはプロセスの承認を管理できるようになります

 [統合アクション センターの概要](https://flow.microsoft.com/en-us/blog/introducing-the-unified-action-center/)

**自動フロー:** 自動フローはあらかじめ決めたイベントによってトリガーされます。 自動フローは、イベントがフローの実行をトリガーしたときに実行されます。 例: Common Data Service でレコードを作成、削除、更新する際に、それが選択したトリガーの場合にフローを実行します。

 [Power Automate でクラウド フローを作成](get-started-logic-flow.md)

## <a name="b"></a>B

**ビジネス プロセス フロー**: ビジネス プロセス フローにより、会社の全社員が同じプロセスに従うことを保証できます。  ユーザーが従う必要のある一連の手順を定義します。 たとえばビジネス プロセス フローを作成すると、全員が顧客サービス要求を同じ方法で処理できます。  注文を送信する前に、請求書の承認を取得する必要がある場合があります。

 [ビジネス プロセス フローの概要](business-process-flows-overview.md)

## <a name="c"></a>C

**Common Data Service:** Power Automate と Power Apps など、ビジネス アプリケーションのデータを保存するために使用するクラウド スケール データベース。 これは基盤となる Azure クラウド データ管理サービスを抽象化したもので、ビジネス アプリケーションの構築を容易にします。

 [Common Data Service とは](/powerapps/maker/common-data-service/data-platform-intro)

**Common Data Service for Teams**: Microsoft Teams に対応した共有クラウド データ プラットフォーム。 Common Data Service for Teams を使用すると、Microsoft Power Apps や Microsoft Power Virtual Agents とともに Teams を利用して誰でもアプリやインテリジェントなチャットボットをすばやく構築して展開できます。

**条件:** 条件は、フローに設定済みのロジックに基づいてアクションを実行するようにフローに指示します。 特定の条件が満たされると 1 つ以上のタスクが完了します。 たとえば、キーワードを含むツイートが少なくとも 10 回リツイートされたらメールを受信するように、ユーザーが条件を指定できます。

 [クラウド フローへの条件の追加](add-condition.md)

**コネクタ:** コネクタを使用すると、ユーザーは一般的なサービス (Twitter、Outlook、Gmail など) を Microsoft Power Automate、Microsoft Power Apps、Azure Logic Apps に接続できます。 これにはアプリとワークフローで使用する一連のビルド済みトリガー ("新しいメールが届いたとき"…) とアクション ("メールの添付ファイルを SharePoint とマイ アプリにアップロードする") を含みます。

 [コネクタのドキュメント](https://docs.microsoft.com/connectors/)

**カスタム コネクタ:** カスタム コネクタを使用すると、ユーザーが Web サービスを Power Automate に接続できます。 ユーザーは、認証、サポートするトリガーとアクション、それらの各アクションのパラメーターと出力を含む Web サービスの特性を Power Automate に伝えます。 カスタム コネクタは組織と共有する前に登録が必要です。

[Power Automate のビルドを開始する](get-started-flow-dev.md)

## <a name="d"></a>D

**データ損失防止**: データ損失防止は、ポリシーを作成して適用し、ビジネス データにアクセスして共有できるコネクタを定義する機能を提供します。 これはビジネス データを確実に保護する重要な機能です。

 [データ損失防止ポリシー](prevent-data-loss.md)

## <a name="f"></a>F

**フロー チェッカー:** フロー チェッカーは、クラウド フローを実行するために改善が必要になる可能性がある、フロー内の特定の発生を示す診断ツールです。 特定した問題ごとに、フロー チェッカーが設計者のコマンド バーに表示されます。 フローで 1 件以上のエラーが特定された場合、赤い点を表示します。

 [フロー チェッカーを使用してエラーの特定と修正をする](error-checker.md)

**フロー タイプ:** 自動、即時、スケジュール、UI フロー、ビジネス プロセス フロー。

 [Power Automate の概要](getting-started.md)

**フロー デザイナー:** フロー デザイナーは、作成者が最初からフローを作成したり、(カスタマイズやステップの追加が可能な) テンプレートから開始したりするスタジオです。

## <a name="i"></a>I

**インスタント フロー:** インスタント フローを使用すると、ユーザーがモバイルやデスクトップのアプリから手動で繰り返しタスクをトリガーできます。 たとえば会議の前にモバイル アプリのボタンをクリックすると、チームにアラーム メールを送信します。

 [インスタント フローの概要](introduction-to-button-flows.md)

## <a name="m"></a>月

**マルチステップ フロー:** マルチステップ フローは複数のアクションを使用してタスクを実行します。

## <a name="r"></a>R

**ロボティック プロセス オートメーション (RPA):** コンピューター システムのユーザー インターフェイスを操作する人間のアクションを再現するソフトウェア アプリケーションを使用した自動化。

 [UI flows で Softomotive の WinAutomation を使用する](desktop-flows/create-processes.md)

## <a name="s"></a>土

**スケジュールされたフロー:** スケジュールされたフローは作成者が定義したスケジュールで実行されます。 スケジュールされたフローは次の周期で繰り返すことができます: 秒、分、時間、日、週、月ごと。 たとえば、ユーザーは SharePoint やデータベースに毎日のデータをアップロードするなど、自動化をスケジュールできます。

 [スケジュールに従ったフローの実行](run-scheduled-tasks.md)

**ステップ:** フロー デザイナの各ステップ (アクション) の下部に **+新しいステップ** とラベル付けされたボタンがあり、ユーザーがさらにアクションを追加できます。

## <a name="t"></a>T

**テンプレート:** テンプレートは、特定のビジネス ニーズを満たすフローをユーザーが簡単に作成するために設計された、事前構築済みトリガーとアクションのセットです。 テンプレートはカスタマイズできます。 一般的な自動化シナリオの多くのタイプに対応する、数百ものフロー テンプレートがあります。

 [Power Automate テンプレート](https://flow.microsoft.com/templates/)

**トリガー :** トリガーとは、クラウド フローを開始するイベントです。  たとえば、クラウド フローを作成する場合、「添付ファイル付きのメールが届いたら、ファイルを OneDrive に自動的にアップロードします」 - 添付ファイル付きの電子メールの到着は、そのようなフローのトリガーです。

フローはトリガーを 1 件以上含むことができます。

## <a name="w"></a>水

**ワークフロー:** 開始から完了までタスクを実行する一連のアクション。

## <a name="u"></a>U

**UI フロー (RPA):** ユーザーは UI フローを使用して Windows と Web のアプリケーションで反復的タスクを自動化できます。 UI フローは、使いやすい API または完全な API を使用できないアプリケーションのユーザー インターフェイス アクション (クリック、キーボード入力など) を記録して再生します。

[UI flows の概要](desktop-flows/overview.md)

## <a name="learn-more"></a>詳細情報を見る

* Power Automate の [ガイド付き学習ツアー](https://docs.microsoft.com/learn/paths/automate-process-using-flow) を見る
* [入門ガイド](getting-started.md) で Power Automate の基本を学ぶ
