---
title: Power Automate と Web サイトおよびアプリを統合する | Microsoft Docs
description: Web サイトまたはアプリに Power Automate エクスペリエンスを埋め込む。
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/29/2020
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 8ff34fc4190f5a0285e15c55779885016108c22b
ms.sourcegitcommit: 741ae960b733c4569236089a1f00114508bbb451
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "3905078"
---
# <a name="integrate-power-automate-with-websites-and-apps"></a>Power Automate と Web サイトおよびアプリを統合する
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

*フロー ウィジェット*  を使用してアプリまたは Web サイトに Power Automate を埋め込むことで、ユーザーは簡単に個人的なタスクや仕事のタスクを自動化できるようになります。

フロー ウィジェットは、ホスト ドキュメント内にある iframe です。 このドキュメントは Power Automate デザイナー内のページを指します。 フロー ウィジェットによって Power Automate の特定の機能がサードパーティ製アプリケーションに統合されます。

ウィジェットはシンプルにすることができます。 たとえば、ホストと iframe の間で通信せずにテンプレートの一覧をレンダリングするようなウィジェットです。 ウィジェットは複雑にすることもできます。 たとえば、テンプレートからフローをプロビジョニングし、ホストとウィジェットの間の双方向通信によってフローをトリガーするようなウィジェットです。

## <a name="prerequisites"></a>前提条件

- **Microsoft アカウント** または
- 職場または学校アカウント

## <a name="use-the-unauthenticated-widget"></a>認証されていないウィジェットを使用する
認証されていないテンプレート ウィジェットを使用するには、iframe を使用してホスト アプリケーションに直接埋め込みます。 JS SDK やアクセス トークンは必要ありません。 

### <a name="show-templates-for-your-scenarios"></a>シナリオに応じたテンプレートの表示
開始するには、次のコードを追加し、Web サイトに Power Automate テンプレートを表示します：

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}&category={category}"></iframe>
```

| パラメーター | 内容 |
| --- | --- |
| ロケール |テンプレート ビューを表す 4 文字の言語と地域コード。 たとえば、`en-us` は米国英語を表し、`de-de` はドイツ語を表します。 |
| 検索語句 |ビューに表示するテンプレートの検索語句。 たとえば、SharePoint のテンプレートを表示するには、`SharePoint` を検索します。 |
| テンプレートの数 |ビューに表示するテンプレートの数。 |
| destination |ユーザーがテンプレートを選択したときに開くページ。 テンプレートの詳細を表示するには  `details` と入力し、Power Automate デザイナーを開くには `new` と入力します。 |
| カテゴリ |フィルター処理で所与のテンプレート カテゴリに絞り込みます。 | 
| parameters.{name} |フローに渡す追加のコンテキスト。 |

宛先パラメーターが `new` の場合、ユーザーがテンプレートを開くと、 Power Automate デザイナーが開きます。 ユーザーはデザイナーでフローを作成できます。 ウィジェットをフルに活用したい場合は、次のセクションをご覧ください。

### <a name="passing-additional-parameters-to-the-flow-template"></a>フロー テンプレートに追加のパラメーターを渡す

ユーザーが Web サイトやアプリで特定のコンテキストにいる場合、そのコンテキストをフローに渡すことができます。 たとえば、ユーザーが SharePoint で特定のリストを見ながら、*項目が作成されたとき* のテンプレートを開くとします。 次の手順に従って、リスト ID を *パラメーター* としてフローに渡します。

1. フロー テンプレートを発行する前に、そのテンプレートでパラメーターを定義します。 パラメーターは、`@{parameters('parameter_name')}` のような形式にします。
1. iframe src のクエリ文字列でパラメーターを渡します。 たとえば、**listName** というパラメーターがある場合は、`&parameters.listName={the name of the list}` を追加します。

### <a name="full-sample"></a>完全なサンプル

ドイツ語の SharePoint テンプレートを上位 4 つ表示し、**myCoolList** でユーザーを開始するには、次のコードを使用します:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=sharepoint%20&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="use-the-authenticated-flow-widgets"></a>認証済みのフロー ウィジェットを使用する

次の表は、ユーザー認証アクセス トークンを使用し、ウィジェットの全機能をサポートする Power Automate ウィジェットの一覧です。 Power Automate の Javascript Software 開発者キット (JS SDK) を使用し、ウィジェットを埋め込み、必要なユーザー アクセス トークンを提供する必要があります。

| ウィジェットの種類    | サポートされる機能                                                                                                                  | 
|----------------|------------------------------------------------------------------------------------------------------------------------------------| 
| フロー          | 個人フローと共有フローについて、タブにフローの一覧を表示します。 既存のフローを編集するか、テンプレートまたは白紙から新しいフローを作成します。 | 
| flowCreation   | ホスト アプリケーションが提供するテンプレート ID からフローを作成します。                                                                | 
| ランタイム        | ホスト アプリケーションが提供する手動またはハイブリッド トリガーのフローをトリガーします。                                                        | 
| approvalCenter | 承認要求と送信済み承認を埋め込みます。                                                                                        | 
| テンプレート      | テンプレートの一覧を表示します。 ユーザーは 1 つ選択し、新しいフローを作成します。                                                                         | 

認証済みの Flow SDK を使用すると、ユーザーは Web サイトまたはアプリから直接フローを作成して管理できます (Power Automate に移動する必要はありません)。 認証済み SDK を使用するには、ユーザーをその Microsoft Account または Azure Active Directory でサインインする必要があります。

> [!NOTE]
> ウィジェットを使用するとき、Power Automate ブランドを非表示にする方法はありません。

## <a name="widget-architecture"></a>ウィジェット アーキテクチャ

Power Automate ウィジェットは、 Power Automate を参照する iFrame をホスト アプリケーションに埋め込むことで動作します。 Power Automate ウィジェットから要求されるアクセス トークンはホストから提供されます。 Power Automate の JS SDK によって、ホスト アプリケーションはウィジェットのライフサイクルを初期化し、管理できます。

![ウィジェット アーキテクチャ](../media/embed-flow-dev/Architecture.png)

### <a name="js-sdk-details"></a>JS SDK の詳細

Power Automate チームから、サードパーティ製アプリケーションに Flow ウィジェットを統合する目的で JS SDK が提供されます。 Flow JS SDK は Flow サービスの公開リンクとして利用でき、ホスト アプリケーションはがウィジェットからのイベントを処理したり、ウィジェットにアクションを送信することで Flow アプリケーションとやり取りできます。 ウィジェットのイベントとアクションはウィジェットの種類に固有です。

### <a name="widget-initialization"></a>ウィジェット初期化

Flow JS SDK 参照は、ウィジェットを初期化する前にホスト アプリケーションに追加する必要があります。

```html
<script src="https://flow.microsoft.com/Content/msflowsdk-1.1.js"></script>
```

任意の hostName とロケール値を JSON オブジェクトに渡すことで、JS SDK インスタンスを作成します。

```javascript
var sdk = new MsFlowSdk({
    hostName:'https://flow.microsoft.com',
    locale:'en-US'
}); 
```

| 件名     | 必須/任意 | 内容                                                    | 
|----------|-------------------|----------------------------------------------------------------| 
| `hostName` | 任意          | Power Automate ホスト名、例:  https://flow.microsoft.com        | 
| `locale`   | 任意          | ウィジェットのクライアント ロケール (指定されていない場合の既定値は `en-Us`) | 


JS SDK インスタンスが作成されると、Power Automate ウィジェットを初期化し、ホスト アプリケーションの親要素に埋め込むことができます。 これを行うには、HTML div を追加します:

```html
<div id="flowDiv" class="flowContainer"></div>
```

続いて、`renderWidget()` メソッドを使用して、Power Automate ウィジェットを初期化します。 必ずウィジェットの種類と対応する設定を指定してください。

```javascript
var widget = sdk.renderWidget('<widgettype>', {
        container: 'flowDiv',
        flowsSettings: {},
        templatesSettings: {},
        approvalSettings: {},
        widgetStyleSettings: {}
});
```

ホスト アプリケーションのディメンションに合わせて変更できるコンテナーのサンプル スタイルです。

```html
<head>
    <style>
        .flowContainer iframe {
            width: 400px;
            height: 1000px;
            border: none;
            overflow: hidden;
    }
    </style>
</head>
```

`renderWidget()` のパラメーターは次のようになります: 

| パラメーター        | 必須/任意 | 内容                                                                                 | 
|------------------|-------------------|---------------------------------------------------------------------------------------------| 
| `container`        | 必要な領域          | ウィジェットが埋め込まれるホスト ページの DIV 要素の ID。                   | 
| `environmentId`    | 任意          | ウィジェットには環境 ID が必要です。Id を指定しない場合、既定の環境が使用されます。 | 
| `flowsSettings`    | 任意          | Power Automate 設定オブジェクト                                                                        | 
| `templateSettings` | 任意          | テンプレート設定オブジェクト                                                                    | 
| `approvalSettings` | 任意          | 承認設定オブジェクト                                                                    | 

### <a name="access-tokens"></a>アクセス トークン

`renderWidget()` の実行後、JS SDK によって iFrame が初期化され、それが Power Automate ウィジェットの URL を指し示します。 この URL には、クエリ文字列パラメーターのすべての設定が含まれています。 ホスト アプリケーションは、ウィジェットを初期化する前に、ユーザーの Power Automate アクセス トークン (Azure Active Directory JWT と対象ユーザー https://service.flow.microsoft.com) を取得する必要があります。 ウィジェットは、`GET_ACCESS_TOKEN` イベントを発生させ、ホストからのアクセス トークンを要求します。 ホストはイベントを処理し、トークンをウィジェットに渡す必要があります。

```javascript
widget.listen("GET_ACCESS_TOKEN", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
        token:  '<accesstokenFromHost>'
    });
});
```

ホスト アプリケーションは、トークンを保守し、要求されたとき、トークンと有効期限をウィジェットに渡す役割を担います。 ウィジェットを開いている時間が長くなった場合、ホストはトークンの有効期限が切れていないか確認し、必要であれば、ウィジェットに渡す前にトークンを更新する必要があります。

### <a name="detecting-if-the-widget-is-ready"></a>ウィジェットの準備状態を検出する

初期化に成功すると、ウィジェットの準備ができたことを通知するイベントをウィジェットは発生させます。 ホストは `WIDGET_READY` イベントをリッスンし、追加のホスト コードを実行できます。

```javascript
widget.listen("WIDGET_READY", function() {
    console.log("The flow widget is now ready.");
    // other host code on widget ready
});
 ```

## <a name="widget-settings"></a>ウィジェット設定

### <a name="flowssettings"></a>FlowsSettings 

FlowsSettings を使用し、Power Automate ウィジェットの機能をカスタマイズできます。

```javascript
flowsSettings?: {
    createFromBlankTemplateId?: string;
    flowsFilter?: string;sc
    tab?: string;
};
 ```

| パラメーター | 必須/任意 | 内容 | 
|-----------|-------------------|-------------| 
| `createFromBlankTemplateId` | 必要な領域 | ユーザーが Flow ウィジェットで **一から作成** ボタンを選択したとき、テンプレートの GUID を使用します | 
| `flowsFilter` | 任意 | Power Automate ウィジェットは、フローを一覧表示するとき、指定されたフィルターを適用します。 たとえば、特定の SharePoint サイトを参照するフローを表示します。 <br /> ```flowsFilter: "operations/any(operation: operation/sharepoint.site eq 'https://microsoft.sharepoint.com/teams/ProcessSimple' )"   ``` |                 
| `tab` | 任意 | Power Automate ウィジェットに表示するようにアクティブ タブを既定値に設定します。 <br /> たとえば、 <br /> ```tab:'sharedFlows' ``` は、[チーム] タブを表示し<br /> ``` tab:'myFlows' ``` は、[マイ フロー] タブを表示します。 |   

### <a name="templatessettings"></a>TemplatesSettings 

これは、Flows、FlowCreation、Templates ウィジェットなど、テンプレートからフローを作成できるすべてのウィジェットに適用されます。

```javascript
templatesSettings?: {
    defaultParams?: any;
    destination?: string;
    pageSize?: number;
    searchTerm?: string;
    templateCategory?: string;
    useServerSideProvisioning?: boolean;
    enableDietDesigner?: boolean;
};
 ```

| パラメーター |必須/任意 | 内容                                                                        
|-----------|-------------------|-----------------| 
|`defaultParams` | 任意          | テンプレートからフローを作成するときに使用するデザイン時パラメーター、例: <br /> ``` defaultParams: {'parameters.sharepoint.site': 'https://microsoft.sharepoint.com/teams/ProcessSimple', 'parameters.sharepoint.list': 'b3a5baa8-fe94-44ca-a6f0-270d9f821668'   } ```| 
| `destination` | 任意          | 有効な値は "new" または "details" です。 "details" に設定されると、テンプレートからフローを作成するとき、詳細ページが表示されます。     |
| `pageSize` | 任意          | 表示するテンプレートの数。 既定のサイズ = 6 | 
| `searchTerm` | 任意          | 指定された検索語句に一致するテンプレートを表示します| 
| `templateCategory` | 任意          | 特定のカテゴリのテンプレートを表示します| 
 
### <a name="approvalcentersettings"></a>ApprovalCenterSettings

ApprovalCenter ウィジェットに適用されます。

 ```javascript
 approvalCenterSettings?: {
    approvalsFilter?: string;
    tab?: string;but
    autoNavigateToDetails?: boolean;
    showSimpleEmptyPage? boolean;
    hideLink?: boolean
};
 ```
| パラメーター | 必須/任意 | 内容 | 
|------------|-------------------|--------------| 
| `hideLink`| 任意 | `true` に設定されると、ウィジェットは送受信済みの承認リンクを非表示にします | 
| `autoNavigateToDetails`| 任意 | `true` に設定されると、承認が 1 つだけ存在するとき、ウィジェットによって承認詳細が自動的に開きます | 
| `approvalsFilter`| 任意 | 承認ウィジェットは、承認を一覧表示するときに、指定の承認フィルターを適用します。例:    承認ウィジェットは、承認を一覧表示するときに、指定の承認フィルターを適用します。例: <br/> ``` approvalsFilter: 'properties/itemlink eq \'https://microsoft.sharepoint.com/teams/ProcessSimple/_layouts/15/listform.aspx?PageType=4&ListId=737e30a6-5bc4-4e9c-bcdc-d34c5c57d938&ID=3&ContentTypeID=0x010010B708969A9C16408696FD23801531C6\'' ```  <br/> <br/>``` approvalsFilter: 'properties/itemlinkencoded eq \'{Your base64 encoded item link url} \'' ```|
| `tab`| 任意 | Flow ウィジェットに表示するようにアクティブ タブを既定値に設定します。 <br/> 有効な値 : "receivedApprovals"、"sentApprovals" | 
| `showSimpleEmptyPage`| 任意 | 承認がないとき、空のページが表示されます | 
| `hideInfoPaneCloseButton` | 任意 | 情報ウィンドウの [閉じる] ボタンを非表示にします (あるいは、ホストに [閉じる] ボタンが既にあります) | 

<!-- why isn't this: hideInfoPaneCloseButton listed in the approvalCenterSettings? call since other optionals are there -->

## <a name="widget-events"></a>ウィジェット イベント

Power Automate ウィジェットは、ホストがウィンドウのライフサイクル イベントを待ち受けることを許可するイベントに対応しています。 Power Automate ウィジェットは、2 種類のイベントに対応しています: 一方向通知イベント (Widget\_Ready など) と、ウィジェットから発生し、ホストからデータを取得するイベント (Get\_Access\_Token)。 ホストは widget.listen() メソッドを使用し、ウィジェットから発生する特定のイベントをリッスンする必要があります。

### <a name="usage"></a>使用法

```javascript
widget.listen("<WIDGET_EVENT>", function() {
    console.log("The flow widget raised event");
});
```

### <a name="supported-events-by-widget-type"></a>ウィジェットの種類別サポートされるイベント

| ウィジェットのイベント      | 詳細                                                         | 
|-------------------|-----------------------------------------------------------------| 
| `WIDGET_READY`      | ウィジェットが正常にロードされた                                      | 
| `WIDGET_RENDERED`   | ウィジェットがロードされ、UI レンダリングが完了した                      | 
| `GET_ACCESS_TOKEN`  | 埋め込みユーザー アクセス トークンのウィジェット要求                      | 
| `GET_STRINGS`       | ウィジェットに表示される一連の UI 文字列をオーバーライドすることをホストに許可する | 

### <a name="runtime-widget"></a>ランタイム ウィジェット

| ウィジェットのイベント                    | 詳細                                     | データ​​                                              | 
|---------------------------------|---------------------------------------------|-----------| 
| `RUN_FLOW_STARTED`                | トリガーされ、フロー実行が開始された      |           | 
| `RUN_FLOW_COMPLETED`              | フロー実行が正常にトリガーされた             |           | 
| `RUN_FLOW_DONE_BUTTON_CLICKED`    | フロー実行でユーザーが [完了] ボタンを選択した       |           | 
| `RUN_FLOW_CANCEL_BUTTON_CLICKED`  | フロー実行でユーザーが [キャンセル] ボタンを選択した     |           | 
| `FLOW_CREATION_SUCCEEDED`         | フローが正常に作成された           |`{ flowUrl: string, flowId: string, fromTemplate: string } `|
| `WIDGET_CLOSE`                    | ホストがウィジェットを閉じると発生 |       | 

### <a name="flow-creation-widget"></a>フロー作成ウィジェット

| ウィジェットのイベント             | 詳細                                  | データ​​  | 
|--------------------------|------------------------------------------|-------| 
| `FLOW_CREATION_FAILED`     | フローの作成失敗                     |       | 
| `WIDGET_CLOSE`             | ホストがウィジェットを閉じると発生  |       | 
| `TEMPLATE_LOAD_FAILED`     | テンプレートのロードに失敗              |       | 
| `FLOW_CREATION_SUCCEEDED`  | フローが正常に作成された        |` { flowUrl: string, flowId: string,fromTemplate?: string } `| 

### <a name="approval-widget"></a>承認ウィジェット

| ウィジェットのイベント                      | 詳細                             | 
|-----------------------------------|-------------------------------------| 
| `RECEIVED_APPROVAL_STATUS_CHANGED`  | 受信承認ステータスが変更された  | 
| `SENT_APPROVAL_STATUS_CHANGED`      | 送信承認ステータスが変更された      | 

**GET\_STRINGS** イベントを使用すると、ウィジェットに表示される UI 要素のテキストの一部をカスタマイズできます。 次の文字列をカスタマイズできます:

| 文字列キー                     | ウィジェットでの使用                                                                                                                  | 
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------| 
| `FLOW_CREATION_CREATE_BUTTON`    | フロー作成とランタイム ウィジェットの両方でフロー作成ボタンに表示されるテキスト                                                | 
| `FLOW_CREATION_CUSTOM_FLOW_NAME` | フロー作成ウィジェットのフロー名に使用する初期値。 allowCustomFlowName 設定が有効なときにのみ使用。 | 
| `FLOW_CREATION_HEADER`           | フロー作成とランタイム ウィジェットの両方でフローの作成時に使用するヘッダー                                                    | 
| `INVOKE_FLOW_HEADER`             | ランタイム ウィジェットでフローを呼び出すときに使用するヘッダー                                                                           | 
| `INVOKE_FLOW_RUN_FLOW_BUTTON`    | ランタイム ウィジェットでフローを呼び出す/実行するために使用されるボタンに表示されるテキスト                                                       | 

### <a name="example"></a>例

文字列キーとテキストのキーと値のペアを持つ JSON オブジェクトを渡して `widgetDoneCallback` を呼び出し、既定値をオーバーライドします。

```javascript
widget.listen("GET_STRINGS", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
         "FLOW_CREATION_HEADER": "<string override would go here>",
        "INVOKE_FLOW_RUN_FLOW_BUTTON":  "<string override would go here>"
    });
});
```

## <a name="widget-actions"></a>ウィジェットのアクション

ホストはウィジェットのアクションを使用し、特定のアクションまたはメッセージをウィジェットに送信します。 ウィジェット JS SDK は、メッセージまたは JSON ペイロードをウィジェットに送信する `notify()` メソッドを提供します。 各ウィジェット アクションでは、特定のペイロード署名をサポートします。

### <a name="usage"></a>使用法

```javascript
widget.notify('<WIDGET_ACTION>', parameterMatchingParameterInterface)
    .then(result => console.log(result))
    .catch(error => console.log(error))
 ```

### <a name="example"></a>例 

次のコマンドをランタイム ウィジェットに送信し、フローを呼び出します 

```javascript
widget.notify('triggerFlow', { flowName: flowName, implicitData:implicitData });  
 ```

### <a name="runtime-widget"></a>ランタイム ウィジェット

| ウィジェットのアクション                               | 詳細                                                      | パラメーター インターフェイス  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `triggerFlow`                                 | フロー実行をトリガーする                                          | `{ flowName: string, implicitData?: string } `| 
| `triggerFlowByTemplate`                       | テンプレートによってフロー実行をトリガーする                              | `{ templateId: string, implicitData?: string, designTimeParameters?: Record<string, any> }` |
| `getTriggerSchema`                            | フローのトリガー スキーマを取得する                               | `{   flowName: string, }` | 
| `closeWidget`                                 | 保留中のアクティビティをキャンセルし、WIDGET_CLOSE イベントを発生させる |                      | 

### <a name="flow-creation-widget"></a>フロー作成ウィジェット

| ウィジェットのアクション                               | 詳細                                                      | パラメーター インターフェイス  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `createFlowFromTemplate`                      | 選択したテンプレートのフローを作成する                     | `{ templateName: string, designTimeParameters?: Record<string, any> }`| 
| `createFlowFromTemplateDefinition`            | 選択したテンプレート定義のフローを作成する          | `{ templateDefinition: string }` | 
| `closeWidget`                                 | 保留中のアクティビティをキャンセルし、WIDGET_CLOSE イベントを発生させる |                      | 

### <a name="approval-widget"></a>承認ウィジェット

| ウィジェットのアクション  | 詳細                                           | パラメーター インターフェイス  | 
|----------------|---------------------------------------------------|----------------------| 
| `closeInfoPane`  | 承認詳細を表示している情報ウィンドウを閉じる  | なし                  | 

## <a name="configuring-your-client-application"></a>クライアント アプリケーションを構成する

Flow サービス スコープ (委任されたアクセス許可) でクライアント アプリケーションを構成する必要があります。 ウィジェット統合に使用される Azure Active Directory (AAD) アプリで "コード付与" 認可フローが使用される場合、AAD アプリは、Power Automate でサポートされている委任されたアクセス許可で事前構成する必要があります。 これにより委任されたアクセス許可が与えられ、アプリケーションに次のことが許可されます:

-   承認を管理する
-   承認を読み取る
-   アクティビティを読み取る
-   フローを管理する
-   フローを読み取る

次の手順に従って 1 つ以上の委任されたアクセス許可を選択します:

1.  https://portal.azure.com に移動 
2.  **Azure Active Directory** を選択します。
3.  **管理** で **アプリの登録** を選択します。
4.  Flow サービス スコープに対して構成するサード パーティ製アプリケーションを入力します。
5.  **設定**を選択します。
      ![ウィジェット アーキテクチャ](../media/embed-flow-dev/AAD-App-Settings.png)
6. **API アクセス**/ 配下で **必要なアクセス許可** を選択します
7. **追加** を選択します。
8. **API を選択します**を選択します。
      ![ウィジェット アーキテクチャ](../media/embed-flow-dev/AAD-App-Select-an-API.png)
9. **Power Automate サービス** を探して選択します。 注意：Power Automate サービスを表示するには、テナントで少なくとも 1 人の AAD ユーザーが Flow ポータル (<https://flow.microsoft.com>) にサイン インしている必要があります
10. アプリケーションに必要な Flow スコープを選択し、**保存** を選択します。
      ![ウィジェット アーキテクチャ](../media/embed-flow-dev/AAD-App-DelegatedPermissions.png)

これで、JWT トークンに \'scp' クレームの委任されたアクセス許可が含まれる Flow サービス トークンがアプリケーションに与えられます。

## <a name="sample-application-embedding-flow-widgets"></a>フロー ウィジェット埋め込みのサンプル アプリケーション 

リソース セクションにはサンプル JavaScript Single Page Application (SPA) があり、ホスト ページでフロー ウィジェットの埋め込みを試してみることができます。 サンプル アプリケーションを使用するには、暗黙的な許可フローを有効にして AAD アプリケーションを登録する必要があります。

### <a name="registering-an-aad-app"></a>AAD アプリを登録する

1.  [Azure ポータル](https://portal.azure.com/)にサインインします。
2.  左のナビゲーション ウィンドウで、**Azure Active Directory** を選択し、[**アプリの登録**  (プレビュー) \> 新規登録] を選択します。
3.  **アプリケーションの登録** ページが表示されたら、アプリケーションの名前を入力します。
4.  **サポートされているアカウントの種類** で、任意の組織ディレクトリの **アカウント** を選択します。
5.  **リダイレクト URL** セクションの配下で、Web プラットフォームを選択し、Web サーバーに基づいてアプリケーション\' URL に値を設定します。  この値を http://localhost:30662/ に構成し、サンプル アプリを実行します。
6.  **登録**を選択します。
7.  アプリの **概要** ページで、アプリケーション (クライアント) ID 値をメモします。
8.  このサンプルでは、[暗黙的な許可フロー](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow) を有効にする必要があります。 登録したアプリケーションの左のナビゲーション ウィンドウで、**認証** を選択します。
9.  **詳細設定** の **暗黙的な許可** で **ID トークン** と **アクセス トークン** チェックボックスの両方をオンにします。 このアプリではユーザーをサインインし、Flow API を呼び出す必要があるため、ID トークンとアクセス トークンが必要になります。
10. **保存**を選択します。

### <a name="running-the-sample"></a>サンプルの実行
<!-- todo where should I download from? -->
1.  サンプルをダウンロードし、それをデバイスのローカル フォルダーにコピーします。
2.  FlowSDKSample フォルダーで index.html ファイルを開き、`applicationConfig` を変更し、先に登録したアプリケーション ID に `clientID` を更新します。
    ![ウィジェット アーキテクチャ](../media/embed-flow-dev/SampleApp-ApplicationConfig.png)
3.  サンプル アプリは、Flow スコープの **Flows.Read.All** と **Flow.Manage.All** を使用するように構成されています。 **applicationConfig** オブジェクトの **flowScopes** プロパティを更新することで、追加のスコープを構成できます。
4.  次のコマンドを実行して、依存関係をインストールし、サンプル アプリを実行します。
    > \> npm install \> node server.js
5. ブラウザーを開き、http://localhost:30662 と入力します
6. **サインイン** ボタンを選択し、AAD に認証し、フロー アクセス トークンを取得します。
7. **アクセス トークン** テキスト ボックスにアクセス トークンが含まれます。
    ![ウィジェット アーキテクチャ](../media/embed-flow-dev/SampleApp-AccessToken.png)
8. **Load Flows widget (フロー ウィジェットを読み込む)** または **Load Templates widget (テンプレート ウィジェットを読み込む)** を選択し、対応するウィジェットを埋め込みます。
    ![ウィジェット アーキテクチャ](../media/embed-flow-dev/SampleApp-TemplatesWidget.png)

サンプル アプリケーションの [ダウンロード リンク](https://procsi.blob.core.windows.net/docs/FlowWidgetSampleApp.zip)。

## <a name="resources"></a>リソース

### <a name="widget-test-pages"></a>ウィジェットのテスト ページ

ウィジェットの統合と設定に関する詳細は次の場所で確認できます:

- テンプレート ウィジェット: <[https://flow.microsoft.com/test/templateswidget/](https://flow.microsoft.com/test/templateswidget/)>
- FlowCreation ウィジェット: <[https://flow.microsoft.com/test/flowcreationwidget/](https://flow.microsoft.com/test/flowcreationwidget/)>
- ランタイム ウィジェット: <[https://flow.microsoft.com/test/runtimewidget/](https://flow.microsoft.com/test/runtimewidget/)>
- 承認センター ウィジェット: <[https://flow.microsoft.com/test/approvalcenterwidget/](https://flow.microsoft.com/test/approvalcenterwidget/)>
- フロー ウィジェット: <[https://flow.microsoft.com/test/managewidget/](https://flow.microsoft.com/test/managewidget/)>

### <a name="supported-widget-locales"></a>サポートされているウィジェット ロケール

頭文字で表記されているロケールが一覧にない場合、Flow は、サポートされている最寄りのロケールを既定値に設定します。

| ロケール     | Language                   | 
|------------|----------------------------| 
| bg-bg      | ブルガリア語 (ブルガリア)       | 
| ca-es      | カタルニア語 (カタルニア)            | 
| cs-cz      | チェコ語 (チェコ共和国)     | 
| da-dk      | デンマーク語 (デンマーク)           | 
| de-de      | ドイツ語 (ドイツ)           | 
| el-gr      | ギリシャ語 (ギリシャ)             | 
| en-Us      | 英語 (米国)    | 
| es-es      | スペイン語 (カスティーヤ語)        | 
| et-ee      | エストニア語 (エストニア)         | 
| eu-es      | バスク語 (バスク)             | 
| fi-fi      | フィンランド語 (フィンランド)          | 
| fr-fr      | フランス語 (フランス)            | 
| gl-es      | ガリシア語 (ガリシア)           | 
| hi-HU      | ハンガリー語 (ハンガリー)        | 
| hi-in      | ヒンディー語 (インド)              | 
| hr-hr      | クロアチア語 (クロアチア)         | 
| id-Id      | インドネシア語 (インドネシア)     | 
| it-It      | イタリア語 (イタリア)            | 
| jp-Jp      | 日本語 (日本)           | 
| kk-kz      | カザフ語 (カザフスタン)        | 
| ko-kr      | 韓国語 (韓国)             | 
| lt-LT      | リトアニア語 (リトアニア)     | 
| lv-lv      | ラトビア語 (ラトビア)           | 
| ms-my      | マレー語 (マレーシア)           | 
| nb-no      | ノルウェー語 (ブークモール)         | 
| nl-nl      | オランダ語 (オランダ)        | 
| pl-pl      | ポーランド語 (ポーランド)            | 
| pt-br      | ポルトガル語 (ブラジル)        | 
| pt-pt      | ポルトガル語 (ポルトガル)      | 
| ro-ro      | ルーマニア語 (ルーマニア)         | 
| ru-ru      | ロシア語 (ロシア)           | 
| sk-sk      | スロバキア語 (スロバキア)          | 
| sl-si      | スロベニア語 (スロベニア)       | 
| sr-cyrl-rs | セルビア語 (キリル、セルビア) | 
| sr-latn-rs | セルビア語 (ラテン、セルビア)    | 
| sv-se      | スウェーデン語 (スウェーデン)           | 
| th-th      | タイ語 (タイ)            | 
| tr-tr      | トルコ語 (トルコ)           | 
| uk-ua      | ウクライナ語 (ウクライナ)        | 
| vi-vn      | ベトナム語 (ベトナム)      |
