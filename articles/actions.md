---
title: アクションの使用 | MicrosoftDocs
description: アクションでは、作成、更新、削除、割り当て、実行などの操作を実行できます。 内部では、アクションによりカスタム メッセージが作成されます。
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e3b5d53e72cff93f853bafd89f8a51200a7e735f
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74354600"
---
# <a name="use-actions"></a>アクションを使用する
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

アクションによって、ビジネス ロジックの作成範囲が広がります。 アクションでは、作成、更新、削除、割り当て、実行などの操作を実行できます。 内部では、アクションによりカスタム メッセージが作成されます。 開発者はこのようなアクションを "メッセージ" と呼びます。 メッセージはそれぞれ、エンティティ レコードで行われたアクションに基づきます。 プロセスの目標がレコードの作成、更新、割り当ての場合、3 つの個別の手順があります。 各手順を定義するのはエンティティの機能であり、必ずしもビジネス プロセスではありません。  
  
アクションによって、ビジネスに必要な操作に一致する単一の動詞 (あるいはメッセージ) を定義できます。 これらの新しいメッセージは、エンティティで実行できることではなく、プロセスやビヘイビアーによって動かされます。 これらのメッセージは、昇進、変換、日程計画、経路指定、承認など、必要なあらゆる動詞に対応させることができます。 このような動詞を追加することで語彙が増え、ビジネス プロセスをよどみなく定義できます。 クライアント内でアクションを記述することなく、クライアントや統合からこの豊富な語彙を適用できます。 また、アクション全体の成功または失敗を 1 つの単位として管理し、ログに記録できるので簡単です。  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>構成可能なメッセージ  
 アクションを定義し、有効にしたら、開発者はそのメッセージをプラットフォームから提供されるその他のメッセージのように使用できます。 ただし、大きな違いは、そのメッセージが使用されるときに行われるべきことに対して開発者ではない人が変更を適用できるということです。 ビジネス プロセスの変更に合わせ、アクションを構成して手順を変更できます。 そのメッセージを使用するカスタム コードは、プロセスの引数が変更されない限りは変更する必要がありません。  
  
 ワークフローのプロセスとプラグインは引き続き、同様の自動化定義機能を提供します。 ワークフローのプロセスからは、開発者ではない人が変更を適用するための機能が提供されます。 ただし、ビジネス プロセスの構成方法と開発者のコード記述方法に違いがあります。 アクションは、プラットフォームにより提供されるメッセージと同じレベルで作動するメッセージです。 開発者はアクションのプラグインを登録できます。  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>グローバル メッセージ 
 
 Common Data Service のワークフローや[プラグイン](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in)とは異なり、アクションを特定のエンティティに関連付ける必要はありません。 それ自体で呼び出せる "グローバル" アクションを定義できます。

## <a name="next-steps"></a>次のステップ

[カスタム アクションの作成](create-actions.md)  
  
