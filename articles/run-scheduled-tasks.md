---
title: スケジュールに従ったフローの実行 | Microsoft Docs
description: 毎日、毎時間などのスケジュールに従ってフローを実行して、定期的なタスクを自動化します。
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/29/2020
ms.author: nijemcevic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: cb5c1d522a522aa1ef2dce2bc0757e4efa3fcc42
ms.sourcegitcommit: 71dd515fb482312e2878c3eb8642441780290cb5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "3742430"
---
# <a name="run-flows-on-a-schedule"></a>スケジュールに従ったフローの実行

1 つ以上のタスクを実行するフローを作成します (例: メールによるレポートの送信):

* 1 日、1 時間、または 1 分につき 1 回
* 指定した日付に
* 指定した日数、時間数、分数の経過後に

## <a name="create-a-recurring-flow"></a>定期的なフローの作成

1. [Power Automate](https://flow.microsoft.com) にサインインし、左側のナビゲーション ウィンドウで **マイ フロー** を選択します。
1. **+ 新規** を選択した後、**+ スケジュール-空白から作成** を選択します。
    ![フローを白紙から作成します](./media/run-scheduled-tasks/create-flow.png)
1. **開始** ボックスを編集してフローを開始するタイミングを指定し、**繰り返し間隔** ボックスを編集してフローの繰り返しを指定し、**作成** を選択します。
    ![定期的なアイテムの設定](./media/run-scheduled-tasks/select-recurrence.png)

## <a name="configure-advanced-options"></a>詳細設定オプションの構成

1. 前のセクションの手順に従います。 次に **定期的なアイテム** > **詳細オプションの表示** を選択します。

    ![詳細な定期的なアイテムオプションの表示](./media/run-scheduled-tasks/select-recurrence1.png)

   > [!NOTE]
   > このオプションは、**間隔** と **頻度** に設定された値に基づいて変更されます。 表示されている画面が、下図と異なる場合は **間隔** と **頻度** が下図と同じ値に設定されていることを確認してください。
1. **タイム ゾーン** を選択し、**開始時刻** を指定する際にローカル タイム ゾーン、協定世界時 (UTC) などを反映するようにします。
1. **開始時刻** を次の形式で指定します:
   <br>YYYY-MM-DDTHH:MM:SSZ
1. **頻度** で **日** を指定した場合は、フローを実行する時刻を指定します。
1. **頻度** で **週** を指定した場合は、フローを実行する曜日 (1 日または複数の曜日) とフローを実行する時刻 (1 回または複数の実行時刻) を指定します。

    たとえば、図のオプションのように、2018 年 1 月 1 日、月曜日の正午 (太平洋標準時) になったらすぐにフローを開始し、このフローを 2 週間に 1 回、火曜日の午後 5:30 (太平洋標準時) に実行するように設定します。

    ![詳細なオプションを指定する](./media/run-scheduled-tasks/advanced-options.png)
1. [ゼロからフローを作成](get-started-logic-flow.md) に関する記事に従って、フローで実行するアクションを追加します。

## <a name="learn-more"></a>詳細はこちら

[詳細オプション](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) とその構成方法の詳細をご覧ください。
