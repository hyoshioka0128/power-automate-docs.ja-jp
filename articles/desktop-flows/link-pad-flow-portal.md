---
title: Power Automate Desktop フローを別のフローからトリガーする | Microsoft Docs
description: Power Automate Desktop フローとPower Automate ポータルのクラウド フローをリンクする
author: olegmelnykov
ms.service: flow
ms.topic: article
ms.date: 09/22/2020
ms.author: olmelnyk
ms.reviewer: olmelnyk
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f5068f207ea54cff6b62bc98fbbbc4aca33031c5
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711648"
---
# <a name="trigger-a-power-automate-desktop-flow-from-another-flow"></a>Power Automate Desktop フローを別のフローからトリガーする



1. **flow.microsoft.com** にアクセスし、資格情報を使用してサインインします。 Power Automateでは、**マイ フロー** を選択します。 **+ 新規フロー** を選択し、ドロップダウンから **インスタント クラウド フロー** を選択します。

   ![マイ フロー インスタント ブランク](\media\link-pad-flow-portal\my-flows-instant-blank.png)

1. クラウドフローの名前を入力します。名前を入力しない場合は、名前が自動的に生成されます。 **フローを手動でトリガーする** を選択し、**作成** を選択します。

   ![手動でフローをトリガーする](\media\link-pad-flow-portal\manually-trigger-flow.png)

1. **+ 新規ステップ** を選択します。

   ![新しいステップ](\media\link-pad-flow-portal\new-step.png)

1. **アクションを選択する** プロンプトの検索フィールドに、**Power Automate Desktop** を入力します。 **アクション** 配下で、**Power Automate Desktop で構築したフローの実行** を実行します。

   ![アクションの検索](\media\link-pad-flow-portal\action-search.png)

1. アクション パラメーターで、実行モードを **有人-ログイン時に実行** に設定します。そしてデスクトップ フローのドロップダウンで **新しいデスクトップ フローを作成** を選択します。

   ![デスクトップ フロー Power Automate Desktop アクション プロパティを実行する](\media\link-pad-flow-portal\run-desktop-flow-v2-action-properties.png)

1. デスクトップ フローの名前を入力し、**アプリの起動** を選択します。

   ![デスクトップ フローのダイアログを作成する](\media\link-pad-flow-portal\build-desktop-flow-dialog.png)

1. ブラウザから、flow.microsoft.com でアプリケーションを開くことを許可するかどうかを尋ねるメッセージが表示される場合があります。 このアクションが Power Automate  Desktop で継続することを許可します。

   ![ブラウザーでのアプリケーションの起動](\media\link-pad-flow-portal\browser-open-application.png)

1. Power Automate コンソールは、選択した名前でデスクトップフローを作成し、フロー デザイナーを開いて新しいフローを編集します。

   ![ブランクのフロー デザイナー](\media\link-pad-flow-portal\flow-designer-blank.png)

1. オプションで、入出力変数を作成して、Power Automate から Power Automate Desktop にデータを前後に渡すことができます。 変数ペインで **+** を選択して、入出力変数を追加します。

   ![新規入出力変数](\media\link-pad-flow-portal\new-input-output-var.png)

1. 入力変数やは出力変数を作成するには、変数の編集ダイアログボックスで以下のようにフィールドを入力する必要があります。
   * 変数タイプ - 入力または出力
   * 変数名 - フローデザイナーにおけるの変数の名前
   * 既定値 - 何も割り当てられていない場合に変数が保持する値
   * データ型 - 変数の型 (整数、文字列、日時など)
   * 外部名称 - フロー デザイナーの外部で使用する名称。 この名前は Power Automate に表示されます。
   * 説明 - 変数の説明者です。 この必須フィールドは Power Automate に表示されます

   ![新規入力変数の追加](\media\link-pad-flow-portal\add-new-input-var.png)

1. Power Automate から Power Automate Desktop にデータを渡すための入力変数を作成します。 この変数は、デスクトップ フローのどこでも使用できます。

1. Power Automate Desktop から Power Automate にデータを渡すには、出力変数を作成します。

1. Power Automate に戻ると、入力変数は UI アクションのフィールドとして表示されます。

   ![デスクトップ フロー Power Automate Desktop アクション プロパティを実行する 2](\media\link-pad-flow-portal\run-desktop-flow-v2-action-properties-2.png)

1. Power Automate Desktop からの出力変数は、他の Power Automate アクションで使用することができます。


