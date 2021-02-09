---
title: プロセスと記録に関する操作 (プレビュー) | Microsoft Docs
description: Process Advisor でプロセスを作成して操作する方法。
services: ''
suite: flow
documentationcenter: na
author: nijemcevic
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2020
ms.author: tatn
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3a301c0e2c58a0c44e29a345146a242156bc6281
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711664"
---
# <a name="work-with-processes-and-recordings-preview"></a>プロセスと記録に関する操作 (プレビュー)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Process Advisor を使用してプロセスを視覚化および分析する前に、次のことを行う必要があります。

- Process Advisor でプロセスを作成する。
- プロセスを構成する活動を Process Advisor レコーダーに記録する。
- 分析用の記録を準備する。

## <a name="create-a-process"></a>プロセスの作成

一般に、非効率または反復的であると思われるプロセスは、分析するのに適切な候補になります。 また、1 人のユーザーに限定する必要があり、複数の個人が関与する複雑なビジネス プロセスには適していません。

1. [Power Automate](https://powerautomate.microsoft.com/) にサインインします。
1. 左側のナビゲーション ウィンドウで、**Process Advisor (プレビュー)** を選択します。
1. **Process Advisor (プレビュー)** にある **作成** を選択します。
1. **新しいプロセスを作成** のタイルを選択します。
1. プロセスに名前を説明を付し、**作成** を選択します。

プロセス作成に関するショート ビデオ: [プロセスを作成する](https://go.microsoft.com/fwlink/?linkid=2147540)

## <a name="record-your-process"></a>プロセスを記録する

次の 3 つの方法のいずれかで記録を作成します。

- Process Advisor の **作成** 画面から
- プロセス作成直後
- プロセス詳細ページから

プロセスの記録に関するショート ビデオ: [プロセスを記録する](https://go.microsoft.com/fwlink/?linkid=2147725)

### <a name="create-a-recording-from-the-create-screen"></a>「作成」画面から記録を作成する

1. **Process Advisor (プレビュー)** > **作成** 画面から、**新しい記録を追加** を選択します。
1. **プロセス** 画面で、記録するプロセスを選択します。
1. **レコーダーを開く** を選択します。
    >[!NOTE]
    >ドロップダウンにプロセスが表示されない場合は、プロセスが正しく共有されていることを確認してください。

### <a name="create-a-recording-right-after-process-creation"></a>プロセス作成直後に記録を作成する

1. プロセスが作成された後、作成が成功したモーダルが次のステップとしていくつかのオプションとともに表示されます。
1. **記録の追加** を選択します。

### <a name="create-a-recording-from-the-process-details-page"></a>プロセスの詳細ページから記録を作成する

1. **Process Advisor (プレビュー)** > **プロセス** ページから、リスト ビューから記録するプロセスを選択します。
1. プロセスの名前を選択して、プロセスの詳細ページに移動します。
1. コマンド バーから **新しい記録** を選択します。
1. **レコーダーを開く** を選択します。

### <a name="launching-the-recorder-in-power-automate-desktop"></a>Power Automate Desktop でレコーダーを起動する

1. 上記の方法のいずれかを使用すると、Power Automate Desktop に **レコーダーを起動** するメッセージが表示されます。
    > [!NOTE]
    > 開始する前に、[Power Automate Desktop をダウンロード](https://go.microsoft.com/fwlink/?linkid=2102613)しておく必要があります。 ただし、**今すぐアプリを入手** を選択して、インストールすることもできます。
1. Power Automate Desktop をインストールした後、**Power Automate Desktop** ブラウザーのポップアップ ウィンドウが表示されます。  それを選択してアプリを開きます。
1. Power Automate Desktop はインストールされているものの、正しく開かない場合は、**もう一度開く** を選択してください。

## <a name="power-automate-desktop-recorder"></a>Power Automate Desktop レコーダー

1. デスクトップ レコーダー画面で、**記録の開始** を選択します。
1. 記録する操作を実行してから、レコーダー ウィンドウの下部にある **終了** を選択します。
1. 記録が正常に保存されたら、**OK** を選択してメッセージを閉じます。
1. ブラウザーで Web ポータルに戻り、**記録を表示する** を選択します。

> [!NOTE]
> 記録の長さによっては、操作ができるようになるまでに時間がかかる場合があります。

### <a name="recorder-features"></a>レコーダーの機能

- アクションを記録すると、アクションの説明がレコーダー ウィンドウに一覧表示されます。 ごみ箱アイコンをクリックして、記録からアクションを削除できます。
- 記録中はいつでも **記録の一時停止** を選択できます。 
- 一時停止したところから記録を再開するには、**記録を再開** を選択します。
- 記録されたすべてのアクションを消去して最初からやり直すには、**記録のリセット** を選択します。

### <a name="recording-tips"></a>記録のヒント

- 記録の読みやすさを改善するために、アクションを系統立ったものにしてください。 少し遅れがありますので、操作対象のアイテムに赤いボックスがフォーカスを設定するのを待ってから選択してください。
- ミスクリックがあった場合は、レコーダー ウィンドウでアクションを削除します。

## <a name="prepare-a-recording-for-analysis"></a>分析用の記録を準備する

記録が完了すると、記録の詳細ページで記録されたアクションを表示できます。 重要なのは、分析用に記録を準備することです。 具体的な変更点

- 記録されたアクションは非常に細かくすることができます。 それらを活動にグループ化します。 これらは、分析を通じて作成されるプロセス マップの構成要素になります。
- 記録から機密情報を削除します。  [詳細](process-advisor-protect.md)。

分析用の記録の準備に関するショート ビデオ: [分析用の記録を準備する](https://go.microsoft.com/fwlink/?linkid=2147425)

### <a name="grouping-actions-into-activities"></a>アクションを活動にグループ化する

1. **グループの追加** を選択し、グループ ヘッダーを追加します。 グループ ヘッダーの下で、次のグループ ヘッダーの前にあるすべてのアクションは、グループの一部と見なされます。
1. グループ ヘッダーをアクション リストの上下に移動して、グループ化を開始する場所に移動します。
1. 画面の右側でグループに名前を付けます。
1. ドロップダウン メニューを使用して、プロセスにすでに存在するグループ名を検索するか、独自のグループ名を作成します。
1. 間違いがあり、グループを削除したい場合は、グループ名の横にあるゴミ箱アイコンを使用してください。
1. 随時、右上の **保存** を選択して作業を保存します。
1. 分析するには、少なくとも 2 つのグループが必要です。 さもなければ、プロセス マップはあまり意味がありません。
1. グループ化が終了したら、**保存** の横にある **分析の準備完了** を設定します。
1. **閉じる** を選択して、プロセスの詳細ページに戻ります。

### <a name="remove-sensitive-information"></a>機密情報を削除する

1. 削除する情報が含まれているステップを選択します。
1. ステップの名前や説明を編集して、銀行口座番号やパスワードなどの機密情報を削除します。
1. 機密情報を含むスクリーンショットをすべて削除します。

### <a name="grouping-tips"></a>グループ化のヒント

- 可能な限り既存のグループ名を使用すると、より一貫性のある正確なプロセス マップが作成されます。
- グループ名は、記録が保存されるたびにドロップダウン リストに表示されます。 そのグループ名を使用したすべての記録から削除された後にドロップダウン リストからグループ名を削除するには、記録を分析する必要があります。
