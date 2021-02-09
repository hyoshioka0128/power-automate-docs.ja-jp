---
title: バックグラウンド ワークフロー プロセスの管理に関するベスト プラクティス | MicrosoftDocs
description: ワークフローを使用するための推奨の方法を理解する
ms.custom: ''
ms.date: 07/27/2020
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
author: Mattp123
ms.assetid: 34e34c33-003a-494f-858c-3d34aacb308c
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c61d9ccd6fd3b35771073c4deadf6467cea00108
ms.sourcegitcommit: dbe05fc5136f724705e66ad795a9391ec47414e1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "3973137"
---
# <a name="best-practices-for-background-workflow-processes"></a>バックグラウンド ワークフロー プロセスのベスト プラクティス


このトピックは、バックグラウンド ワークフロー プロセスの作成と管理のためのベスト プラクティスを紹介します。  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>無限ループの回避  
無限ループを開始する、バックグラウンド ワークフローのロジックを作成する可能性があります。無限ループは、サーバーのリソースを消費し、パフォーマンスに影響を及ぼします。 無限ループが発生する可能性のある一般的な状態は、属性が更新されたときに開始し、ワークフローのロジックでその属性を更新するように構成されている、バックグラウンド ワークフローがある場合です。 更新アクションがレコードを更新する同じバックグラウンド ワークフローをトリガーし、バックグラウンド ワークフローを何回も反復して開始します。  
  
作成するワークフローには、無限ループを検出して停止するためのロジックが含まれます。 バックグラウンド ワークフローのプロセスが、短時間に特定のレコードに対して一定回数以上実行された場合、以下のエラーで失敗します : **このワークフロージョブは、開始したワークフローに無限ループが含まれていたため、キャンセルされました。ワークフローのロジックを修正して、もう一度やり直してください。** 回数の上限値は 16 です。  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-background-workflow-templates"></a>バックグラウンド ワークフロー テンプレートを使用する  
同様なワークフローが存在し、同じパターンに従ったワークフローをさらに作成する予定の場合、バックグラウンド ワークフローをワークフロー テンプレートとして保存します。 このように、同様なワークフローを次回作成する必要があるときに、テンプレートを使用してバックグラウンド ワークフローを作成すると、一からすべての条件とアクションを入力する必要がなくなります。  
  
**プロセスの作成** ダイアログ ボックスで、**既存テンプレートからのプロセスの新規作成 (一覧から選択)** を選択します。  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>子ワークフローの使用  
別のワークフローでまたは条件分岐で同じロジックを適用する場合、ロジックを子ワークフローと定義すると、各バックグラウンド ワークフローまたは条件分岐でそのロジックを手動で複製する必要がなくなります。 これにより、ワークフローの維持が容易になります。 同じロジックを適用する可能性のある多くのワークフローを調べるのではなく、1 つのワークフローを更新するだけとなります。  
  
## <a name="automatically-delete-completed-background-workflow-jobs"></a>完了したバックグラウンド ワークフロー ジョブを自動的に削除する
バックグラウンド (非同期) のワークフローでは、バックグラウンド ワークフロー定義で **完了したワークフロー ジョブを自動的に削除する (ディスク容量の確保)** オプションをオンにすることを推奨します。 このチェック ボックスを選択すると、成功した実行のバックグラウンドのワークフロー ログを削除してスペースを節約することができます。 失敗したバックグラウンド ワークフロー実行のログは、トラブルシューティングのために常に保存されます。  

![ワークフロー ジョブの保持](media/workflow-job-retention.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>同じエンティティを更新するワークフローの数を制限する
同じエンティティを更新するバックグラウンド ワークフローが複数実行していると、リソース ロック問題が発生することがあります。 各営業案件の更新プログラムが関連取引先企業に対して更新をトリガーしている状況で実行している複数のワークフローを考えてみてください。 同時に同じ取引先企業レコードを更新するよう、実行および試行するこれらのワークフローの複数のインスタンスにリソース ロック問題が発生する場合があります。 バックグラウンド ワークフローの失敗が発生すると、**SQL タイムアウト: リソース _リソース名_ のロックを取得できません** などのエラー メッセージが記録されます。 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>変更の追跡にメモを使用  
ワークフローを編集するときは、メモ タブを使用して、実行した内容と実行した理由を入力する必要があります。 これにより、加えた変更点を他のユーザーが理解することができます。  
  
## <a name="next-steps"></a>次の手順  
<!-- [Workflow processes overview](workflow-processes.md)    -->
[バックグラウンド ワークフロー プロセスの構成](configure-workflow-steps.md)   
[バックグラウンド ワークフロー プロセスの監視と管理](monitor-manage-processes.md)
   
