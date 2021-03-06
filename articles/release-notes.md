---
title: リリース ノート | Microsoft Docs
description: Power Automate リリースの一般的な問題と新機能
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/07/2020
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 82e175f463e9cbc264b6ac388e90eaa3433211b4
ms.sourcegitcommit: 4b9261984a554dfccb0d0d77f3d5fdca60e26433
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "3340145"
---
# <a name="release-notes"></a>リリース ノート

>[!NOTE]
>リリース計画は、[こちら](https://docs.microsoft.com/dynamics365/release-plans/) から追跡できるようになりました。

## <a name="top-questions"></a>よくある質問
1. 自分のフローでエラーが発生しました。 解決するにはどうすればよいですか。
   
   1. エラーを特定します。 最初に Web ポータルの上部にある通知アイコンを選ぶか、モバイル アプリで **アクティビティ** タブを選びます。 フローが表示され、選択できるようになります。
   2. これでフローの詳細を調べられるようになりました。 赤い感嘆符のアイコンの付いたステップを探すと、フローのエラー メッセージが表示されています。
   3. エラー メッセージに応じて、フローを **編集** して修正できます。 [フローの一般的なエラーの解決方法についてお読みください](fix-flow-failures.md)。
2. 高度な条件または式はどのようにして使えばよいですか。
   
   * [条件の追加](add-condition.md) についてお読みください。
   * フローに複数のケースが必要な場合は、既存の条件内から **条件の追加** を選択します。
   * 高度な式を作成するには、[Logic Apps の関数](https://docs.microsoft.com/rest/api/logic/definition-language) を参照してください。
3. Office 365 ではライセンスはどのように機能しますか?
   
   * Office 365 ユーザーの場合は、Power Automate for Office 365 プランでフル アクセスを取得します。 詳細については、[Power Automate の料金プラン](https://flow.microsoft.com/pricing/) を参照してください。
   * 管理者の場合は、Office 365 などで [Power Automate ライセンス](organization-q-and-a.md) に関する情報を参照してください。

## <a name="known-issues"></a>既知の問題
1. [マイ サイト] にある、種類が *カスタム リスト* 以外の SharePoint リストはサポートされていません。 この問題を回避するには、標準的な SharePoint サイトにカスタム リストを作成します。
2. 選択したフォルダー内で入れ子になったフォルダーの中に追加されるファイルに対しては、ファイル トリガーが起動されません。

## <a name="whats-new"></a>最新情報

Power Automate でリリースされた新機能の詳細については、以下を参照してください:
- [2020 リリース ウェーブ 1 プラン](https://docs.microsoft.com/power-platform-release-plan/2020wave1/power-automate/planned-features): 今後数か月の間にリリースされる新機能について。
- [週間リリース ノート](https://docs.microsoft.com/business-applications-release-notes/powerplatform/released-versions/flow): 過去数週間にリリースされた新機能、修正プログラム、機能強化について。

### <a name="release-2018-09-24"></a>2018 年 9 月 24 日リリース

- **ヘルプとサポートへの管理者アクセス** - Power Platform の管理センターで Power Automate のサポート チケットを開き、ワークフローの失敗に関する追加の詳細を指定します。
- **Power Automate コミュニティの再設計** - Power Automate コミュニティで必要な情報をより簡単に検索できるようになりました。
- **Microsoft Teams コネクタの機能強化** - チャネルに新しいメッセージがあるときにフローを実行できるようにする、Microsoft Teams 用の新しいトリガー。
- **SharePoint アクションの追加** - SharePoint コネクタには、ファイルを移動するための新しいアクションなどがあります。
- **新規管理者の分析レポート** - 環境とテナントに関する広範な分析がビジネス アプリケーション プラットフォームの管理センターに追加されました。
- **Power Query の統合** - 作成者が SQL Server からデータのマッシュアップを形成できるようにする Power Query エクスペリエンスを構築中です。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/support-tickets-teams-sharepoint/)。

### <a name="release-2018-08-31"></a>2018 年 8 月 31 日リリース

- **サンプル データを使用してフローをテストする** - Power Automate デザイナー内で構築するときに、コネクタからのサンプル データを使用して、フローをテストします。 サンプル データでフローをテストするときは、運用環境に展開したときに意図したとおりにフローが実行することを確認します。
- **5 つの新しいコネクタ** - 4 つの新しい管理コネクタを追加しました: Power Apps for App Makers、Power Platform for Admins、Power Apps for Admins、管理者向け Power Automate、Microsoft School Data Sync。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/test-data-management-connectors/)。

### <a name="release-2018-08-24"></a>2018 年 8 月 24 日リリース

- **新しいカレンダー同期テンプレート** - Google カレンダーと Office 365 または Outlook.com の間でイベントをコピーする新しいカレンダー テンプレート。
- **SharePoint の複数値サポート** - SharePoint の Choice、Person、または Lookup 型の複数値フィールドの読み取りと書き込み。
- **組織内の他のユーザーに代わって承認を送信する** - 組織内の他のユーザーに代わって承認を送信します - たとえば、フローを作成したユーザーの代わりに、SharePoint リストでファイルをアップロードしたユーザー。
- **入力型のボタンの追加** - ボタンには数値とはい/いいえの 2 つの新しい入力型ボタンがあります。
- **コネクタの更新** - 新しい NetDocuments コネクタ、Azure コネクタなどの機能強化。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/button-types-more/)。

### <a name="release-2018-08-02"></a>2018 年 8 月 2 日リリース

Power Automate プレビュー プログラムは、Power Automate の今後の機能と更新にいち早くアクセスする方法です。 最新の機能にいち早くアクセスするには、だけを作成し、プレビュー リージョンに環境を作成して使用するだけです。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/flow-preview-program/)。

### <a name="release-2018-07-23"></a>2018 年 7 月 23 日リリース

- **Excel からのフローの構築と実行** - 新しい **フロー** ボタン (リボンの **データ** タブからアクセス) を使用して、Power Automate から Excel のテーブル データ上でオートメーションを作成してトリガーできます。 データ処理またはデータのコピー/インポートを自動化します。
- **ビジネス プロセス フローの作成** - ビジネス プロセス フローとは、Common Data Service に基づく、ステートフルでヒューマン インタラクティブな新しい種類のフローです。 これらの新しいフローを使用して、ユーザーが従う一連のステージと手順を定義します。 これは必要に応じて前後できます。
- **Outlook Web App での Microsoft To-Do のフローの作成** - Outlook Web App で \@ 誰かが言及した場合、フローを作成するためのショートカットが表示されます。 このフローでは、メールのコンテンツに基づき、Microsoft To-Do で \@言及されたユーザーのタスクが自動的に作成されます。
- **SharePoint ビューのサポート** - SharePoint コネクタで、トリガーとアクションでの特定の SharePoint ビューの選択がサポートされるようになりました。 これによって列が、選択したビュー内にあるフィールドのみにフィルター処理されます。
- **4 つの新しいコネクタ** - Azure IoT Central が追加されました - 拡張性の高い IoT ソフトウェアとしてのサービス (SaaS) ソリューション - Survey 123、LMS365、ProjectWise Design Integration。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/excel-bpf-todo-and-more/)。

### <a name="release-2018-06-29"></a>2018 年 6 月 29 日リリース

- **SharePoint に組み込まれる承認の要求フロー** - SharePoint でファイルや項目を選択すると、新しい **承認の要求** フローが表示されます。 このフローは構成や設定を必要とせず、1 回のクリックで承認要求を送信します。
- **2 つの新しいコネクタ** - Cloud Connect Studio と PoliteMail が追加されました。
- **履歴と作成ページの機能強化** - 実行履歴の一覧に正確な実行時間が含まれます。また、作成ページに新しいチュートリアル ビデオが追加されます。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/request-sign-off-four-connectors/)。

### <a name="release-2018-06-08"></a>2018 年 6 月8 日リリース

- **PowerShell コマンドレット** - フローの作成者とテナント管理者の両方が、PowerShell を使用して各自の Flow をプログラムで管理できるようになりました。
- **Teams Flow ボットの機能強化** - Microsoft Teams の Flow ボットで、フロー ボタンの実行とフローの説明を行うことができるようになりました。
- **3 つの新しいコネクタ** - Marketo、ElasticOCR、DynamicSignal のサポートが追加されました。 
- **追加の共有情報** - フローを共有するか、共有フローを実行するときに、詳細情報が追加されました。これにより、他のユーザーが受け取るアクセス許可を正確に確認できます。
- **SharePoint URL の自動トリミング** - ブラウザーで SharePoint URL をコピーして貼り付けると、サイト以外のテキストが含まれている場合がありますが、サイトにのみ接続できるように、このテキストは自動的に削除されます。
- **GDPR 要求に関するドキュメント** - 企業組織がデータ主体の権利要求を処理するための、包括的なガイドとツールセットを作成しました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/powershell-flow-bot-marketo/)。

### <a name="release-2018-05-21"></a>2018 年 5 月 21 日リリース

- **SharePoint リストとライブラリによって "所有されている" フロー** - SharePoint リストとライブラリを操作するフローは、それらのリストまたはライブラリと共有することができます。 そのため、個人やグループと共有されるのではなく、リストにアクセスできるすべてのユーザーと共有されます。 ユーザーがリストまたはライブラリに追加または削除されると、それに従ってメンバーシップも自動的に変更されます。
- **エラーの詳細分析** - フロー内で発生するすべてのエラーに関する情報が掲載された新しい埋め込みレポートです。
- **Office 365 グループとのフローの共有** - Office 365 の最新のグループをフローの所有者にすることができ、グループ内のすべてのユーザーがフローを実行できるように、Office 365 グループとボタン フローを共有することができます。
- **SharePoint コネクタの改善** - 2 つの新しい SharePoint コネクタ機能があります: 項目またはファイルが削除されるときにフローをトリガーする機能と、SharePoint REST API がサポートする任意の HTTP エンドポイントを呼び出す機能です。
- **2 つの新しいコネクタ** - Azure Data Factory と MailParser のサポートが追加されました

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/share-with-sharepoint-office-365/)。

### <a name="release-2018-05-01"></a>2018 年 5 月 1 日リリース

- **承認メッセージ内のリッチ テキスト** - Markdown を使って、送信する承認の詳細を書式設定します。
- **複数の選択入力を含むボタン** - 複数選択リストを使って複数の値を一度に収集するフロー ボタンを構築します。
- **より広いフローで作業する** - Power Automate モバイル アプリは横向きビューをサポートするようになり、Web デザイナーには水平スクロール バーがあります。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/rich-approvals-text-and-multiselect/)。

### <a name="release-2018-04-12"></a>2018 年 4 月 12日リリース

- **フローから Power Apps にデータを返す** - Power Apps でビルドされたアプリから呼び出すことができるフローを構築して、データをアプリに戻すことができます。 視覚的なドラッグ アンド ドロップのフロー デザイナーを使用して、アプリに必要なロジックを構築できます。 
- **配列の入力に複数レコードが追加されます** - 複数の添付ファイルを電子メールに追加する場合などに使用できるリスト ビルダーが Power Automate に追加されました。
- **以前の実行データでフローをテストできます** - 以前のフロー実行のトリガー データでフローをテストできる、新しい [フローのテスト] ボタンがデザイナーに追加されました。
- **新規ワークフロー () フィールド** - 環境名とフローの表示名に新規ワークフロー () 式でアクセスできるようになりました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/return-data-to-powerapps/)。

### <a name="release-2018-04-04"></a>2018 年 4 月 4 日リリース

- **Common Data Service での承認** - 最新バージョンの Common Data Service に最新の承認が構築されます。 つまり、Common Data Service コネクタとの間で送受信する承認の状態を読み取るフローを構築することができます。
- **それぞれに適用でのエラーの検出** - ループ内に大量の項目がある場合でも、フロー実行ビューでエラーのループに直接移動します。
- **承認の再割り当て** - 受け取った承認を組織内の別のユーザーに割り当てて、承認を委任することができます。 
- **会議室の一覧** - Office 365 の Outlook Connector で、組織の会議室データを取得するアクションが追加されました。
- **フロー ボタンの詳細表示** - 共有されているフローを実行すると、そのフローで使用されるすべてのアクションが表示されるようになりました。
- **英国のリージョン** - 英国でのデータを格納するための環境を作成できるようになりました。
- **2 つの新しいコネクタ** - AtBot Admin と Marketing Content Hub のサポートが追加されました。
- **新しいドキュメントのランディング ページ** - ドキュメントのランディング ページが更新され、その対象が初心者か、中級者か、上級者かによってグループ化されるようになりました。 

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/approvals-in-cds-and-seven-updates/)。

### <a name="release-2018-03-13"></a>2018 年 3 月 13 日リリース

- **承認履歴** - 応答、送信したコメント、正確な発生時刻を含む、送信済みの承認依頼がすべて表示されます。
- **4 つの新しいコネクタ** - Excel Online (Business)、Excel Online (OneDrive)、Azure SQL Data Warehouse、および Pitney Bowes Tax Calculator が追加されました。
- **動的コンテンツのツールヒント** - 動的コンテンツにマウスを合わせることで、アクションの内容を表示したり、完全な式エディターを開かずに式をプレビューしたりできます。
- **同時実行制御** - 指定したワークフローに一度に 1 つの実行のみが含まれるように、同時実行制御が有効になります。
- **指数近似の再試行** - 新しい種類の再試行ポリシーでは、再試行が指数関数的な間隔で行われます。
- **アクセシビリティへの準拠** - Power Automate がどのようにアクセシビリティの基準を満たすかについて説明した、新しい準拠ドキュメントをリリースしました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/approval-history-accessibility/)。

### <a name="release-2018-02-09"></a>2018 年 2 月 9 日リリース

- **ゲートウェイの高可用性** - オンプレミス データ ゲートウェイで可用性の高いクラスターを作り、1 台のコンピューターが停止しても接続が維持されるようにします。
- **それぞれに適用の改善** - Flow プラン 1 または Flow プラン 2 によって、最大 100,000 個の項目が 1 回の実行で処理され、それぞれに適用のループで 50 件のアクションが並列処理されます。 

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/)。

### <a name="release-2018-01-29"></a>2018 年 1 月 29 日リリース

- **Microsoft Teams 内の Flow** - Teams から、フローを作成して管理し、送受信した承認を見直し、Teams デスクトップ アプリまたは teams.microsoft.com で直接フローを起動できます - [詳細についてはここをお読みください](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/)。
- **共同編集通知** - 自分が所有しているフローが共同作業者によって変更されると、メール通知で変更者と変更されたフローが伝えられます。
- **新規の式** - 新規式セットが 2 つ追加されました。1 つは URL を解析するための式セットで、もう 1 つは JSON オブジェクトと連動する式セットです。
- **3 つの新しいコネクタ** - 今週は新しい Plumsail コネクタが 2 つあります。Plumsail SP と Plumsail Forms です。また、新しい kintone コネクタがあります。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/shared-notifications-and-expressions/)。

### <a name="release-2018-01-17"></a>2018 年 1 月 17 日リリース

- **Office 365 プロファイル情報** - ユーザーのプロファイルと写真を操作する新しいアクションを Office 365 Users コネクタに追加しました。
- **文字列変数を増やす** - ループ内の文字列を増やし、テーブルやその他の一覧をビルドできます。
- **Infobip コネクタ** - Infobip は、音声通話や受信 SMS のトリガーなど、企業レベルの通信を可能にするサービスです。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/o365-profile-infobip/)。

### <a name="release-2017-12-20"></a>2017 年 12 月 20 日リリース

すべての Power Automate リージョンで Power Automate Analytics を利用できるようになり、環境内で実行されているフローの正常性を詳細に知ることができます。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/)。


### <a name="release-2017-12-14"></a>2017 年 12 月 14 日リリース

- **Outlook Connector の機能強化** - ".eml" ファイルとしてのメールの保存、予定表の招待への自動応答、メール スレッドで言及されたときのフローのトリガーを行うことができるようになりました。
- **接続の機能強化** - Power Automate はユーザーが最近使った接続を記憶し、新しく追加されたすべてのコネクタを表示します。
- **5 つの新しいコネクタ** - Azure Container Instances、Azure Kusto、Metatask、Microsoft To-Do、Plumsail Documents が追加されました。
- **HTTP の改善** - HTTP のアクションがチャンク エンコードをサポートするようになりました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/outlook-connector-more/)。

### <a name="release-2017-12-05"></a>2017 年 12 月 5 日リリース

すべてのリージョンで、Power Automate の起動パネルを利用できるようになりました。 このパネルでは、SharePoint のリストまたはドキュメント ライブラリ内でフローを実行するときに、フローに値を追加することができます。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/)。


### <a name="release-2017-11-28"></a>2017 年 11 月 28 日リリース

- **管理されたメタデータ** - 管理されたメタデータ (分類とも呼ばれます) 型を使う SharePoint の列からデータを読み取ったり書き込んだりできます。 (aka.Taxonomy) タイプ。
- **配列への追加** - 新しい [配列変数に追加] アクションを使って、配列の末尾に項目を追加できます。
- **Tago** - Tago へのコネクタが新しく追加されました。外部データを提供する電子デバイスを簡単に接続し、コンテキスト分析を使ってより賢明な意思決定を下すことができます。
- **iPhone X** - iPhone X の全画面表示を使い、画像のアップロードの速度が向上した、新しいバージョンの Power Automate アプリです。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/managed-metadata-tago/)。

### <a name="release-2017-11-09"></a>2017 年 11 月 9 日リリース

- **OneDrive for Business 統合** - [OneDrive for Business 内にフロー ボタン](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/)が追加され、選んだファイルまたはフォルダーに対するフローを作成またはトリガーできるようになりました。
- **プランナーのトリガー** - 新しいタスクが作成されたとき、自分にタスクが割り当てられたとき、またはタスクが完了したときにフローを開始します。
- **SharePoint の添付ファイル** - SharePoint リスト項目の添付ファイルを処理 (添付ファイルの一覧表示、ダウンロード、追加、削除) します。
- **フロー管理コネクタ** - 環境内の他のフローの管理を自動化するフローを作成します (たとえば、アクセス許可をフローに自動的に追加します)。
- **4 つの新しいコネクタ** - Azure Custom Vision Service、D&B Optimizer、Enadoc、Derdak SIGNL4 が追加されました。 
- **コネクタ アクションの追加** - SQL クエリの実行、メール トリガーの取得の高速化、Azure AD での HTTP の任意のメソッドの使用など。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/)。

### <a name="release-2017-11-02"></a>2017 年 11 月 2 日リリース

- **監査ログ** - Power Automate 監査イベントを、すべてのテナントの Office 365 セキュリティ/コンプライアンス センターで使用できるようになりました。
- **フロー ウィジェットの修正** - ウィジェットにボタンが読み込まれなくなる Power Automate モバイル アプリの問題を修正しました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/security-and-compliance-center/)。

### <a name="release-2017-10-19"></a>2017 年 10 月 19 日リリース

- **入れ子になったそれぞれに適用** - その他のそれぞれに適用のコンテナー アクションに対してそれぞれに適用のアクションを追加、フィルター処理、および選択ができます。
- **日付と時刻のアクション** - ローカル時刻の取得、および時間の追加、減算、書式設定のための新しいアクション。
- **4 つの新しいコネクタ** - Content Moderator、Docparser、Microsoft Kaizala、Pitney Bowes Data Validation が追加されました。
- **接続エクスペリエンスの向上** - 接続が切れたときの Power Automate ポータルでの通知と、より充実した接続の詳細情報。
- **外出先コレクション** - [外出先で作業する作業者](https://flow.microsoft.com/collections/onthego/) のための新しいテンプレート コレクション。
- **メール アドレスのボタン入力** - ユーザーがボタンを実行したときに、ユーザーからメール アドレスを収集します。
- **ファイルのボタン入力** - ユーザーがボタンを実行したときに、写真などのアップロードされたファイルをユーザーから取得します。
- **最初の実行と自動サインイン** - 自動サインインなど、モバイル アプリでの最初の実行エクスペリエンスが向上しました。
- **Microsoft Forms トリガーの高速化** - Forms ではこれまでよりはるかに速くフローをトリガーできます (これまでは 1 時間に 1 回)。
- **セッション間でのボタン入力** - 携帯電話でトリガーされたボタンが、以前の入力を記憶しています。
- **モバイル アクティビティ フィード** - より詳細な実行の概要とトラブルシューティングの詳細を含めるように、アクティビティのフィードが強化されました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/nested-apply-to-each/)。

### <a name="release-2017-10-03"></a>2017 年 10 月 3 日リリース

- **全員の承認が必要** - 承認要求を受け取ったすべてのユーザーによる承認を必要とします。
- **新しい OneDrive for Business アクション** - OneDrive for Business に格納されたファイルの PDF 生成および他の 4 つの新しいアクション。
- **Apache Impala コネクタ** - Apache Impala (incubating) はオープン ソースであり、Apache Hadoop のネイティブの分析データベースです。
- **フローの説明の追加** - フローを共有するときに同僚がフローの概要を理解できるように、フローの説明を追加します。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/)。

### <a name="release-2017-09-25---q3-update-for-power-automate"></a>2017 年 9 月 25 日リリース - Power Automate の第 3 四半期の更新プログラム

- **最初のリリースでの SharePoint のより深い統合** - レビュー フロー用の新しい "標準" 送信と、初期リリース テナントのフローを実行するときに入力を収集するためのフロー パネルがあります。
- **Dynamics 365 アプリ** - Power Automate が、Dynamics 365 Sales や Dynamics 365 Customer Service などの Dynamics 365 アプリの UI に統合されるようになりましが。
- **Microsoft セキュリティ センター** - Power Automate が Microsoft セキュリティ センターに一覧表示され、HIPAA、ISO、SOC などの認定が示されます。
- **利用状況分析** - すべてのフローには、基本的な利用状況分析機能を備えた Power BI ダッシュボードが埋め込まれています。
- **初期リリースでの監査ログ** - すべてのフロー管理イベントは、初期リリース テナントの Office 365 セキュリティ/コンプライアンス センターに記録されます。
- **6 つの新しいコネクタ** - LinkedIn、Office 365 Groups、Skype for Business、Adobe Sign、Bizzy、Azure Log Analytics Data Collection が追加されました。
- **SQL トリガー** - SQL テーブルで新しい行が追加、または行が更新されると、フローが実行されます。
- **オンプレミスのカスタム コネクタ** - カスタム コネクタは、オンプレミスのデータ ゲートウェイを使って、ネットワーク上の内部エンドポイントに接続できるようになりました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/q3-2017-update/)。

### <a name="release-2017-09-21"></a>2017 年 9 月 21 日リリース

- **フロー履歴のダウンロード** - フローの実行履歴を Excel で開くために CSV ファイルとしてダウンロードします。
- **高度な定期実行** - 定期的なスケジュールを作成してフローをトリガーします (たとえば、平日にのみトリガーする)。
- **IntelliSense** - 式を入力すると、IntelliSense がパラメーターの候補を表示します。
- **4 つの新しいコネクタ** - Azure AD HTTP サービス、Amazon Redshift、Azure Event Grid Publish、FlowForma 用のコネクタが追加されました。
- **リンクの共有** - OneDrive ファイルまたは Azure Storage Blob の共有できるリンクを生成する新しいアクション。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/download-history-recurrence/)。


### <a name="release-2017-08-25"></a>2017 年 8 月 25 日リリース
* **SharePoint 用のドキュメント プロパティおよびその他** - [SharePoint ドキュメント ライブラリのプロパティの読み取りおよび設定](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/) を行い、SharePoint アイテムへのリンクなど追加のフィールドを使用できます。
* **フロー コレクション** - フロー コレクションは、ロールごと、または縦方向で整理された一連のテンプレート コレクションです。
* **ボタンの再共有** - ボタンを同僚と共有すると、同僚はそのボタンを他のユーザーと再共有することができます。
* **ボタンからのリストの収集** - ユーザーがボタンをタップしたときに、選択対象とするオプションのドロップダウン リストを定義できます。
* **7 つの新しいコネクタ** - AWeber、Azure Log Analytics、Azure Tables、DocFusion365、Azure Event Grid、Azure Event Hubs、StaffHub。 
* **Slack および MySQL の機能強化** - Slack でのチャネルの作成または結合がサポートされ、MySQL のデータベースへの書き込みを行うことができます。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/button-updates-seven-connectors/)。

### <a name="release-2017-08-02"></a>2017 年 8 月 2 日リリース
* **個人、選択肢、参照フィールドに書き込む** - SharePoint の作成項目と更新項目は、個人、選択肢、参照フィールドを設定する [機能をサポート](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/) します。
* **その他のアクション設定** - トリガーやアクションの実行で制御できる項目が増えました。たとえば、再試行ポリシーや改ページを構成できます。
* **4 つの新しいコネクタ** - Azure File Storage、Elastic Forms、Plivo、Video Indexer を利用できるようになりました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/four-connector-action-settings/)。

### <a name="release-2017-07-27---q2-update-for-power-automate"></a>2017 年 7 月 27 日リリース - Power Automate の第 2 四半期の更新プログラム
* **インポートとエクスポート** - 環境間で、あるいはテストから本稼働にフロー ソリューションをエクスポートし、インポートできます。 
* **アクションで式を使用する** - アクションに式を入力し、使い方についてインライン ヘルプを表示できます。
* **拡大し、Azure Logic Apps になる** - Visual Studio や Azure Portal を介して展開できる Azure Logic App リソースとしてフローを保存します。
* **表示方法の管理** - Power Automate の利用状況をテナントにダウンロードすると、どこでどのようにフローが使用されているのかを正確に把握できます。
* **Dynamics 365のフロー** - Dynamics 365 for Operations ＆Financials、Business Edition 内のフローを使用する。
* **もっと簡単にシナリオを見つける** - コネクタでできることをすべて参照し、フロー作成のための出発点としてトリガーを使用します。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/q2-2017-update/)。

### <a name="release-2017-07-13"></a>2017 年 7 月 13 日リリース
* **テンプレート公開機能の強化** - 作成したフローとそのカテゴリを一般ギャラリーに公開します。
* **Outlook カレンダーのイベントを取得する** - カレンダーの 2 つの時刻の間にあるすべてのイベントを返す新しいアクションです。
* **新しいモバイル機能** - モバイル アプリでフローを必要に応じて実行し、失敗した実行を再提出します。
* **カスタム コネクタの動的ドロップダウン** - 動的ドロップダウン、ポーリング トリガーを作成し、カスタム コネクタをテストします。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/publishing-and-custom-connectors/)。

### <a name="release-2017-06-28"></a>2017 年 6 月 28 日リリース
* **言語設定の更新** - [設定] メニューによって、Power Automate で使用する言語とリージョンの両方をカスタマイズできます。
* **5 つの新しいコネクタ** - Adobe Creative Cloud、Bing Maps、Bing Search、JotForm、Freshservice に対するサポートを追加しました。
* **タイムアウトの構成** - 承認など、実行時間の長いアクションの "タイムアウト" 設定を事前に変更することで、フローが継続します。
* **Outlook にコメントを追加し承認を求める** - 承認要求を受け取ったら、Outlook を終了せずにコメントを記入できます。
* **カスタム コネクタのブランドの色** - 背景に使用されるカスタム コネクタの色を入力できるようになりました。
* **チーム フローに名前を付けて保存する** - チーム フローなど任意のフローのコピーを作成します。
* **フロー削除の情報** - フローを削除する場合、そのフローで保留中のすべての実行が一覧表示されます。
* **コネクタ ページのフィルター処理** - [コネクタ] ページで希望するコネクタを検索し、コネクタの種類によってフィルター処理します。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/language-settings-3-connectors/)。

### <a name="release-2017-06-19"></a>2017 年 6 月 19 日リリース
送信済みであるすべての保留中の承認要求の状態を表示できるようになりました。 さらに、モバイル デバイスから直接、保留中のすべての承認を参照して操作することができます。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/sent-requests-flow-mobile/)。

### <a name="release-2017-06-15"></a>2017 年 6 月 15 日リリース
* **コンテンツの変換** - HTML コンテンツをプレーン テキストに変換できる新しいコネクタ。HTML で書式設定された電子メールを処理するのに便利です。
* **3 つの新しいデータベース コネクタ** - MySQL、PostgreSQL、Teradata の読み取り専用のサポートを追加しました。 これらのコネクタは、オンプレミスのデータ ゲートウェイ経由で接続されます。
* **その他の 3 つのコネクタ** - Azure Application Insights、Calendly、Teamwork Projects に接続します。
* **エラー処理のために視覚化を向上** - エラー発生後に実行される手順が赤い点線の矢印で表示され、容易に識別できるようになりました。
* **実行の詳細を示すウィンドウ** - フローが失敗した場合に、フローを修正するための有効な手順を含む新しいウィンドウが右側に表示されます。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/seven-connectors-and-html/)。

### <a name="release-2017-06-04"></a>2017 年 6 月 4 日リリース
* **Windows Phone の一般公開** - [Power Automate モバイル アプリが Windows Phone 用にリリースされ一般公開されました](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/)。
* **フローの失敗に関するメール** - フローが失敗すると、メールで通知が届きます。 このような失敗に関する電子メールは、週に 1 回だけ送信されます。ユーザー側でメールの配信のオンまたはオフを設定できます。
* **テーブルに対するアクションを選択する** - 新規 [アクションの選択] を使用することで、テーブルに含める列セットを変更することができます。
* **Microsoft Forms コネクタ** - Microsoft Forms は Office 365 Education に新たに組み込まれ、教師と生徒が迅速かつ容易に独自のクイズを作成し、調査、アンケート、登録などを行うことができます。
* **Office 365 Enterprise K1 プラン** - Power Apps と Power Automate は、一定の割り当てを持つ Office 365 Enterprise K1 プランに含まれるようになりました。
* **HTTP ヘッダーの設定がより簡単に** - アクションの選択と同様に、アクションに対するテキスト ボックスに入力するだけで、ヘッダー名とヘッダー値を指定できます。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/)。

### <a name="release-2017-05-23"></a>2017 年 5 月 23 日リリース
* **Microsoft Teams コネクタ** - [Microsoft Teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) は、Office 365 のチャットベースのワークスペースであり、、チームが必要とするツールとともに、人々、会話、コンテンツをまとめて提供し、共同作業が簡単になり、より多くの成果を達成できるようになります。
* **iOS と Android のウィジェット** - Power Automate ウィジェットは、ホーム画面から直接、簡単にすばやくボタンをトリガーできるようになるボタン ショートカットです。
* **"エラー処理" 手順の作成** - アクションが失敗した後に実行する 1 つ以上の手順を定義します。 たとえば、Dynamics 365 でレコードを作成するフローに失敗した場合に、すぐに通知を取得することができます。
* **整数と浮動小数点の変数** - 特定のロジック セットを実行する回数をカウントするために、フロー実行内のカウンターを初期化して増減します。
* **フローの詳細ページ** - **マイ フロー** 一覧からフローを選択すると、アクセス権を持つユーザー、実行履歴など、そのフローの詳細情報が表示されたページが開きます。
* **管理者のフロー実行クォータ** - 管理者は、通常の会社の実行クォータと比較して、組織全体のフロー実行の使用状況を監視し、クォータの内訳を取得して、クォータに影響しているライセンスを把握できるようになりました。
* **HTTP 要求トリガーの改善** - 要求トリガーにさまざまな HTTP メソッドを使用し、パス セグメントを追加できます。
* **2 つのパートナー コネクタ** - Power Automate は、電子メール解析サービスの Parserr、およびオフラインフォーム サービスの Cognito Forms に接続できるようになりました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/error-handling/)。

### <a name="release-2017-05-12"></a>2017 年 5 月 12 日リリース
* **SharePoint ドキュメント ライブラリの統合** - ドキュメント ライブラリの任意のファイルを選択して、フローを開始できます、たとえば、承認を得るためにマネージャーに送信したり、[さらに多くのこと](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/) を実行できます。
* **Microsoft Planner コネクタ** - Microsoft Planner を使うと、より良い結果を得るためにチーム、タスク、ドキュメント、会話を簡単にまとめることができます。
* **ライセンスの管理ビュー** - 管理者は、Power Automate と Power Apps のすべてのライセンス (試用版と有料版) を Power Automate 管理センターで表示できます。
* **Power Apps コミュニティ プラン** - Power Apps コミュニティ プランは、個人が Power Apps、Power Automate、およびCommon Data Service のスキルを探索、学習、および構築するための無料のプランです。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/planner-community-and-licenses/)。

### <a name="release-2017-05-09"></a>2017 年 5 月 9 日リリース
* **Azure AD コネクタ** - ユーザーの作成やグループへの追加など、管理者の操作を Power Automate から実行するための新しいコネクタがあります。
* **Office 365 Outlook の機能強化** - フローは共有メールボックスによってトリガーされ、共有メールボックスにメールを送信できるようになりました。 また、自動返信を設定したり読むこともできます。
* **カナダでの提供** - カナダでフローを作成できるようになりました。
* **カスタム API Webhook の作成** - カスタム コネクタの開発者は、Webhook でカスタム API にトリガーを追加できるようになりました。
* **管理センターでのフロー所有者の管理** - 環境の管理者は、Power Automate 管理センターでフローの所有者を管理できます。
* **コネクタのドキュメントの参照** - [docs.microsoft.com にコネクタの完全なリファレンス](https://docs.microsoft.com/Connectors/) が公開されました。
* **2 つのパートナー サービス** - Nexmo と Paylocity という 2 つの新しいパートナー サービスがリリースされました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/canada-mailboxes-aad)。

### <a name="release-2017-04-27"></a>2017 年 4 月 27 日リリース
* **並列ステップでのフロー構築** - 並列実行によりフローを作成します。2 つ以上のステップを同時に実行できることになります。
* **新しく 5 つのサービスをサポート** - 新しい 5 つのサービスとは、承認、ベンチマーク電子メール、カプセル CRM、LiveChat、Outlook Customer Manager です。
* **操作の再試行を監視** - Power Automate はサービスでエラーがある場合に再試行します。 自動再試行の回数と、その詳細を確認できるようになりました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/parallel-actions/)。

### <a name="release-2017-04-17---q1-update-for-power-automate"></a>2017 年 4 月 17 日リリース - Power Automate の第 1 四半期の更新プログラム
* **最新の承認エクスペリエンス** - 承認者が Power Automate モバイル アプリ、または Power Automate Web サイトの統合承認センター内から安全に承認できるワークフローを作成します。
* **チーム フローの一般提供** - チーム フローが一般提供され、複数のユーザーがフローとチーム フローを同時に所有して管理できるようになりました。
* **Power Automate のコネクターの構築** - だれでも自分の Power Automate コネクターを無料で送信して、世界中で使用することができます。
* **"無駄を省いた" デザイナー** – 特定のテンプレートでは、新しいバージョンのデザイナーにより、フローの作成に必要なフィールドのみが表示されるようになり、操作が簡略化されます。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/q1-2017-update/)。

### <a name="release-2017-04-11"></a>2017 年 4 月 11 日リリース
* **テーブルと一覧を構築する新規アクション** - アイテムの一覧を処理することができる、HTML ターブルの新規作成、CSV テーブルの作成、参加のアクション (以前の Apply-to-each に代わるもの)。
* **任意の場所へのステップの挿入** - ドラッグ アンド ドロップをしなくても、ワークフローの任意の場所に新しいステップを挿入できるようになりました。
* **4 つの新しいサービス** - Power Automate では、10 から 8 のスケジュール設定、Act!、Inoreader、Computer Vision API をサポートするようになりました。 Computer Vision API を使用すると、イメージを処理してテキスト コンテンツを取得したり (OCR と呼ばれる)、コンテンツに基づいてイメージに自動的にタグ付けしたりできます。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/)。

### <a name="release-2017-04-03"></a>2017 年 4 月 3 日リリース
* **Windows Phone ベータ版** - Windows Phone アプリのベータ プログラムで、Windows Phone でアプリのプレビューを入手できるようになりました。 [詳細](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/).
* **Muhimbi PDF** - Muhimbi PDF で Microsoft Word ファイルから PDF への変換、透かしの追加、文書のマージなどができるようになりました。 [詳細](https://flow.microsoft.com/blog/convert-files-using-muhimbi/).
* **物理ボタンからフローをトリガーする** - Shortcut Labs の Flic、The Button Corporation の Bttn という物理ボタン領域の 2 つの主要製品との提携を発表しました。 [詳細](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>2017 年 3 月 22 日リリース
* **自分のフローのコピーを作成する** - フローのコピーを作成して、下書きバージョンで作業したり、過去に作成したフローを複製したりできるようになりました。
* **2 つの新しいサービス** - タスクの作成と更新により ToDo リストを管理する Toodledo、カスタマー サービスとサポート チケットのプラットフォームを提供する Zendesk のサポートが追加されました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/make-a-copy/)。

### <a name="release-2017-03-15"></a>2017 年 3 月 15 日リリース
* **ボタンを同僚と共有する** - 他のユーザーとフロー ボタンを共有することで、すべてのビジネス ユーザーが容易にクイック タスクを実行できるようになりました。
* **ホーム画面からボタンをトリガーする** - モバイル デバイスのホーム画面またはロック画面からのフロー ボタンへのショートカットにより、これまでよりも素早くフローをトリガーできます。
* **Power Automate アプリのチーム フロー** - iOS または Android 用 Power Automate アプリで、他の所有者がいるフローが表示されるようになりました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/button-sharing/)。

### <a name="release-2017-03-10"></a>2017 年 3 月 10 日リリース
* **カスタム コネクタのエクスペリエンスの向上** - Postman コレクションを使用して、カスタム コネクタの作成、動作の編集、追加、テストを行うことができるようになりました。
* **2 つの新しいサービス** - Power Apps の通知 と PivotalTracker のサポートが追加されました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/new-updates-custom-api/)。

### <a name="release-2017-02-27"></a>2017 年 2 月 27 日リリース
* **フロー ボタンのトリガー** - フロー ボタンを Power Automate から直接トリガーできるようになりました。 フローの一覧を表示したら、[...] メニューを選択し、[今すぐ実行] コマンドを選択します。
* **5 つの新しいサービス** - Oracle Database、Intercom、FreshBooks、LeanKit、WebMerge のサポートが追加されました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/trigger-flow-buttons-web/)。

### <a name="release-2017-02-21"></a>2017 年 2 月 21 日リリース
* **環境のフローを表示** - 環境の管理者は、特定の環境内のすべてのフローの詳細な一覧を表示できるほか、フローの有効化、無効化、および削除を行うことができます。
* **2 つの新しいサービス** - Azure Automation と Basecamp 2 のサポートが追加されました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/)。

### <a name="release-2017-02-16"></a>2017 年 2 月 16 日リリース
* **5 つの新しいサービス** - Azure Data Lake、Bitbucket (GIT のリビジョン管理を使用するプロジェクト用の Web ベースのホスティング サービス)、Eventbrite、Infusionsoft、Pipedrive のサポートが追加されました。
* **カスタム HTTP 認証** - フロー デザイナーでは、カスタム HTTP エンドポイントで認証を使用することが可能になりました。
* **JSON メッセージの解析** - HTTP 要求のトリガーからの JSON データ、または HTTP アクションから返された JSON データを解析できます。
* **フロー実行のフィルター処理** - 実行されているフローやキャンセルされた実行の表示を含めたより具体的なオプションにより、フロー実行のフィルター処理が向上しました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/)。

### <a name="release-2017-02-06"></a>2017 年 2 月 6 日リリース
* **チーム フロー** - チーム フローを使うと、複数のユーザーが共同でフローを所有および管理でき、だれかが組織を離れた場合でも、作成したフローは引き続き実行できます。
* **カスタム コネクタの共有** - チーム フローなどのカスタム コネクタを共有し、組織内でまとめて管理できます。
* **Gmail と LUIS のサポート** - Gmail と Azure Cognitive Services の Language Understanding Intelligent Service に接続します。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/team-flows/)。

### <a name="release-2017-01-30"></a>2017 年 1 月 30 日リリース
* **フロー ボタンの入力** - フロー ボタンが実行時にユーザー入力を受け取れるようになり、フローの作成者はボタンがタップされたときに渡される情報を定義できます。
* **Outlook のタスクと HelloSign** - Outlook Tasks のサービスを使ってタスクを管理でき、HelloSign でセキュリティで保護された電子署名が可能になります。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/button-user-inputs/)。

### <a name="release-2017-01-23"></a>2017 年 1 月 23 日リリース
* **サービスによる検索** - 各サービスのすべてのアクションを表示するためにトリガーまたはアクションを追加するときに、サービスごとに参照します。
* **ケースの切り替え** - 並列ロジックの複数の分岐を作成する切り替えブロックを追加します。
* **電子メール アクションの追加** - フラグ付きメールを処理する Office 365 Outlook および Outlook.com サービスの新しい機能です。
* **5 つの新しいサービス** - ローカルまたはネットワーク ファイル システム、支払いサービス ストライプ、IBM Informix、IBM DB2、UserVoice への接続。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/search-by-service/)。

### <a name="release-2017-01-14"></a>2017 年 1 月 14 日リリース
* **実行の再送信** - 失敗したフローを修正して再び実行したい場合は、失敗した実行を再送信できます。
* **実行のキャンセル** - フローが動かなくなった場合、実行を明示的にキャンセルできるようになりました。
* **2 つの新しいサービス** - GoToTraining と GoToWebinar のサポートが追加されました。
* **モバイル リンク** - モバイル アプリから直接テンプレートを共有できるようになりました。Web サイトの先頭にアプリをすばやくダウンロードできるリンクが追加されました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/managing-runs/)。

### <a name="release-2016-12-29"></a>2016 年 12 月 29 日リリース
Power Automate は eSignature とデジタル取引管理; Web ベース調査用 SurveyMonkey; OneNote ノート作成アプリ (ビジネス アカウントのみ) を処理するために、DocuSign をサポートするようになりました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/final-2016-services/)。

### <a name="release-2016-12-20"></a>2016 年 12 月 20 日リリース
* **今すぐ実行** - 定期的な (繰り返し) トリガーをオンデマンドで開始できるようになりました。たとえば、レポートを毎日スケジュールしているとき、そのレポートを **今すぐ** 実行することもできます。
* **6 つの新しいサービス** - MSN 天気、Medium、Google 連絡先、Buffer、Harvest、TypeForm に接続するフローを構築します。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/run-now-and-six-more-services/)。

### <a name="release-2016-12-14"></a>2016 年 12 月 14 日リリース
ボタンがトリガーされた場所、トリガーしたユーザー、時刻など、ボタン フローをトリガーするとき、貴重な情報を活用できるようになりました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/button-trigger-tokens/)。

### <a name="release-2016-12-06"></a>2016 年 12 月 6 日リリース
* **ガイド付き学習の概要** - Power Automate の豊富な高性能機能を理解するのに役立つ、動画とドキュメントを組み合わせた順番が付いた一連のコースから始めます。
* **2 つの新しいサービス** - Flow では、カスタマー サポート ソリューションの Freshdesk と、オンライン会議ツールの GoToMeeting を利用できるようになりました。
* **HTTP Webhook サポート** - フローを登録と登録解除を自動的に行う webhook のエンドポイントにできるようになりました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/guided-learning-and-two-services/)。

### <a name="release-2016-11-23"></a>2016 年 11 月 23 日リリース
* **Flow で Power BI アラートに対応** - Power BI データ アラートからフローをトリガーすることで、インサイトをアクションに転換します。
* **モバイル アプリケーションの改善** - フローを、テンプレートの既存のエクスペリエンスから作成するだけでなく、一から作成できるようになりました。 フロー実行の表示時のパフォーマンスも改善されました。
* **8 つの新しいサービス** - Azure Resource Manager、Azure キュー、Chatter、Disqus、Azure Cosmos DB、Cognitive Services Face API、HipChat、Wordpress に接続できるようになりました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/)。

### <a name="release-2016-11-15"></a>2016 年 11 月 15 日リリース
* **Power Automate パートナー プログラム** - Power Automate には認定パートナー プログラムが導入され、世界中の Power Automate とつながり、さまざまな会社の才能と経験を活用できるようになりました。
* **6 つの新しいサービス** - Asana、Campfire、EasyRedmine、JIRA、Redmine、Vimeo という 6 つのサービスも今週リリースされます。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/partner-program-six-new-services/)。

### <a name="release-2016-10-31---general-availability"></a>2016 年 10 月 31 日リリース - 一般提供
* **価格とライセンス** - 無料プランと有料プランの両方で利用でき、Office 365 と Dynamics 365 にも含まれています。
* **Power Automate 管理センター** - 新しい管理センターでエンタープライズに対応します。 管理センターでは、組織内の環境を管理できます。
* **データ損失防止ポリシー** - 管理者は、データ損失防止ポリシーを作成してサービス間のデータ フローを制御できます。
* **Android 可用性** - Power Automate 電話アプリは iOS と Android の両方で利用可能になりました。 アプリを使うと、通知を受け取り、活動を監視し、ボタンをタップしてフローを開始することができます。
* **新しいデザイナー エクスペリエンス** - ステップ間で受け渡される動的なコンテンツを検索できるようになり、必要なデータをいっそうすばやく参照できます。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/announcing-ga/)。

### <a name="release-2016-10-26"></a>2016 年 10 月 26 日リリース
* **ボタン フロー** - いつでもどこでもトリガーできる数えきれないほどの操作があります。 ボタン フローでは、モバイル デバイスからボタンをクリックするだけで実行できます。
* **環境の通知** - 環境は、組織のフローを格納して管理するための個別のスペースです。 環境は地理を考慮して配置されるので、環境で保持されるフロー、アプリ、ビジネス データは、その環境があるリージョンに存在します。
* **6 つの新しいサービス** - Bit.ly、Cognitive Services Text Analytics、Dynamics NAV、Dynamics 365 for Financials、Instapaper、Pinterest のサポートの追加。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/environments-for-makers/)。

### <a name="release-2016-10-16"></a>2016 年 10 月 16 日リリース
* **カスタム コネクタでさらに多くの認証の種類がサポートされるようになりました** - カスタム コネクタで API キー認証がサポートされるようになり、OAuth 2.0 仕様全体をサポートするあらゆるサービスに対して認証できるようになりました。
* **3 つの新しいサービスがサポートされるようになりました** - Basecamp 3、Blogger、PagerDuty のサポートが追加されました。
* **デザイナーの機能強化** - パフォーマンスが向上したほか、すべてのアクションで [...] メニューから接続を更新および修正できるようになりました。また、フローの実行を終了するための "終了" と呼ばれる新しいステップが追加されました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/early-october-updates/)。

### <a name="release-2016-09-25"></a>2016 年 9 月 25 日リリース
携帯電話でフローを作成できるようになりました。 テンプレートが豊富に取り揃えられたギャラリーを閲覧したり、サービスの一覧を検索したり、テンプレート カテゴリを選択して詳細を絞り込んだりできます。 このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/mobile-creation/)。

### <a name="release-2016-09-22"></a>2016 年 9 月 22 日リリース
* **Microsoft Graph ユーザー ピッカー** - 新しい Microsoft Graph のユーザー ピッカーが Power Automate UI に直接統合され、適切な連絡先またはメール アドレスを選択できるようになりました。
* **Microsoft Dynamics AX のサポート** - フロー内から、Dynamics AX Online の操作データに対して操作 (レコードの新規作成からデータの照会まで) が可能になりました。
* **パートナーによる 2 つの新しいサービス** - フローから appFigures または Insightly を使用できるようになりました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/more-september-updates/)。

### <a name="release-2016-09-14"></a>2016 年 9 月 14 日リリース
* **Web サイトまたはアプリへの埋め込み** - 開発者は、Power Automate を アプリまたは Web サイトに直接埋め込むことができるようになり、ユーザーに個人的または専門的なタスクを自動化する簡単な方法提供します。
* **HTTP エンドポイントとしてのフローの使用** - フロー自体を HTTP API として使用できるようになりました。 フロー内には "要求" と呼ばれるトリガーがあり、"応答" カードを追加することで、着信要求に応答できます。
* **Todoist のサポート** - Todoist を使用すると、職場や家庭のすべてのプロジェクト全体を把握することができます。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/extend-web-site-application/)。

### <a name="release-2016-09-01"></a>2016 年 9 月 1 日リリース
Power Automate はだれでも利用できるようになりました - 当初は、Office 365 Business または Office 365 Enterprise で使用されているような、職場または学校から提供されたメール アドレスのみにプレビューを公開していました。 本日、プレビューが公式に利用可能になり、どのようなメール アドレスを使用しているかにかかわらず、すべてのユーザーが自由に使用できるようになったことをお知らせいたします。 このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/available-for-everyone/)。

### <a name="release-2016-08-31"></a>2016 年 8 月 31 日リリース
* **条件の入れ子** - 1 つの条件内に 2 番目の条件 (3 番目の条件...) を追加できるようになりました。
* **それぞれに適用** - "それぞれに適用" ループを使用すると、繰り返しの対象となるリストを制御できます。
* **Do until** - "Do until" ループを使用すると、特定の条件が満たされるまでステップを繰り返すことができます。
* **配列のフィルター処理** - リスト内のすべての項目が定義した式と一致することを確認できる単一のネイティブ フィルター ステップがあります。
* **文字列変数の作成** - 文字列変数を作成できるようになりました。
* **スコープ** - スコープは、複数のアクションをグループ化するための簡単な方法です。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/build-advanced-flows/)。

### <a name="release-2016-08-27"></a>2016 年 8 月 27 日リリース
* **ステップに関するコメント** - コメントにより、個々のアクションに簡単に注釈を付けることができるため、フローに必要なことを容易に思い出すことができます
* **Smartsheet のサポート** - 今週、Smartsheet に接続するためのサポートを追加しました。 Smartsheet は、クラウド上のシートでの共同作業を容易にするサービスです。
* **フロー作成時の UI の改善** - フロー名を前面中央に配置し、保存ボタンをページの上部に移動してアクセスしやすくしました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/add-comments-smartsheet/)。

### <a name="release-2016-08-18"></a>2016 年 8 月 18 日リリース
Power Automate の統合を含む新しい SharePoint Online の最新のリスト機能をプレビューできるようになりました。 このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/)。

### <a name="release-2016-08-13"></a>2016 年 8 月 13 日リリース
* **Visual Studio チーム サービス** - Power Automate を使用して、O365 のメール、Slack、Trello、Wunderlist などのさまざまなサービスに VSTS を接続できるようになりました。
* **SharePoint の機能強化** - SharePoint リストは、単純なオブジェクト (単一行のテキスト、日付と時刻など) から複雑なオブジェクト (ユーザー、グループ、参照、選択肢など) まで、幅広いデータ型をサポートします。
* **O365 Outlook 接続のテスト** - ユーザーが新しい O365 Outlook 接続を作成するたびに、接続がテストされ、接続が使用できる状態であるかどうかが確認されます。
* **ブール値コントロール** - さらに、ブール値入力フィールドに入力する値を明確にするために、ブール値コントロールも追加されました (たとえば、[新しいメールが届いたとき] トリガーの [添付ファイルあり])。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/)。

### <a name="release-2016-08-08"></a>2016 年 8 月 8 日リリース
Power Automate に統合された Common Data Service のパブリック プレビュー。 このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/flow-and-common-data-model/)。

### <a name="release-2016-08-05"></a>2016 年 8 月 5 日リリース
* **オンプレミスの SharePoint** - SharePoint Online と同様に、事前に定義済みのテンプレートを使用するかテンプレートを一から作成することで、オンプレミスの SharePoint のリストとドキュメント ライブラリに関するフローを作成できます。
* **デザイナーの情報バブル** - 各トリガーとアクションの機能の詳細を表示するために、フローの各ステップの上に情報バブルを追加しました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/)。

### <a name="release-2016-07-15"></a>2016 年 7 月 15 日リリース
* **4 つの新しいサービスの追加** - Google カレンダー、Google Tasks、YouTube、SparkPost に接続します。
* **アクションの名前変更** - アクションの名前変更により、異なるアクションを区別できるようになりました。
* **異なる期間の遅延** - 秒、分、時、または日の任意の数を選択できるようになりました。
* **使いやすいフォルダー ブラウザー** - フォルダー ブラウザーを簡略化しました。左側で選択すると、そのフォルダーが選択され、右側で選択すると、そのフォルダーが開き、その内のサブフォルダーを選択できるようになります。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/new-google-services-rename-more/)。

### <a name="release-2016-07-08"></a>2016 年 7 月 8 日リリース
オンプレミスのデータ ゲートウェイを使用した、Power Automate のためのオンプレミスの接続。 これにより、SQL Server に対するセキュリティで保護された接続を確立してフローと統合できます。 このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/on-premises-data-gateway/)。

### <a name="release-2016-07-02"></a>2016 年 7 月 2 日リリース
* **Google Sheets のサポート** - これまでの機能では Google ドライブと Excel の両方を使用することができましたが、今週ｍGoogle Sheets のネイティブ サポートが追加されましした。
* **テンプレートを使ってすばやく開始** - また、テンプレートから開始できるように最適化を行いました。 テンプレートに使用するアカウントをテンプレート ページで選択できるようになりました。
* **SharePoint と Office 365 の権限が失効しない** - Power Automate によって Azure Active Directory ベースのサービスへのアクセスが自動的に更新されるようになったため、すべてのフローはパスワードが変更されても正しく動作します。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/more-june-updates/)。

### <a name="release-2016-06-20"></a>2016 年 6 月 20 日リリース
* **Power Automate の新しいモバイル アプリの導入** - 本日、もう 1 つの主要なサービスについてお知らせします: 自動化されたワークフローをいつでもどこでも管理、追跡、参照できるモバイル アプリが iOS 向けにダウンロード可能になりました (Android 向けアプリも近いうちにダウンロード可能になる予定です)。  
* **シングル サインオン** - シングル サインオンが実装され、Office 365 のような他の Microsoft サービスと共に Power Automate への認証を行うことができます。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/)。

### <a name="release-2016-06-18"></a>2016 年 6 月 18 日リリース
* **新しいメール サービス** - Power Automate 内で個人または会社のメール アカウントに接続する必要なく、Power Automate から直接メールを送信できるようになりました。
* **ポータルでの通知** - フローに問題が発生したときにポータルの上部に通知が表示されるようになりました。
* **ポータルのすべてのアクティビティ** - フローの Web サイトで新しい [アクティビティ] タブをクリックすることで、すべてのフローのアクティビティを表示できるようになりました。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/mail-and-all-activity/)。

### <a name="release-2016-05-27"></a>2016 年 5 月 27 日リリース
* **サービス別のテンプレートを参照する** - サポートされているすべてのサービスを (ログインせずに) 表示できるようになりました。 このページで各サービスの説明を読み、そのサービス用に提供されているテンプレートを確認できます。
* **カスタム コネクタの作成と使用** - Power Apps でカスタム コネクタを作成できるのと同様に、flow.microsoft.com で独自の API に接続することもできます:
* **完成前のフローのテスト** - 開始アクションを実行した場合、フローを保存するたびに、フローの実行結果をページ内で直接確認できます。

このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/)。

### <a name="release-2016-05-07"></a>2016 年 5 月 7 日リリース
Microsoft Project Online と Mandrill by Mailchimp の 2 つの新しいサービスを追加しました。 このリリースに関する [詳細や質問についてはこちらをご覧ください](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/)。

### <a name="release-2016-04-27---public-preview"></a>2016 年 4 月 27 日リリース - パブリック プレビュー
[Microsoft Power Apps](https://powerapps.microsoft.com) の一環として Logic フローを使用すると、Power Automate プレビュー リリースの新機能をいくつか使用できます:

* 多数のテンプレートのギャラリーを参照して、人気度、名前、または発行日順に並べ替えることができます。
* フローをカスタマイズした後、ギャラリーに [独自のテンプレートを発行](publish-a-template.md) できます。
* フローのチェックと実行すべてについて、履歴を確認することができます。
* フローを保存するときに、トリガー アクションを実行するだけで、[実行中のフローを即座に確認](see-a-flow-run.md) できます。
* Power Automate または [自分のアイデアを提出](https://go.microsoft.com/fwlink/?LinkID=787474) するための [新しいコミュニティ](https://go.microsoft.com/fwlink/?LinkID=787467) があります。

>[!NOTE]
>リリース計画は、[こちら](https://docs.microsoft.com/dynamics365/release-plans/) から追跡できるようになりました。

## <a name="next-steps"></a>次の手順
このリリース ノート、または [よく寄せられる質問](frequently-asked-questions.md) に記載されていない問題がある場合は、[コミュニティに参加](https://go.microsoft.com/fwlink/?LinkID=787467) して質問するか、[サポートにお問い合わせください](https://go.microsoft.com/fwlink/?LinkID=787479)。

