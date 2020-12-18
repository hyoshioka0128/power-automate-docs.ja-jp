---
title: 'サンプル: 業務プロセス フローの使用 | MicrosoftDocs'
description: このサンプルでは、エンティティ レコードの業務プロセス フロー インスタンスの取得、業務プロセス フロー インスタンスとそのプロセス ステージのアクティブパスの取得、アクティブ ステージの変更などの業務プロセス フローをプログラムで処理する方法を示します。
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
ms.assetid: 7d378504-b4b2-4a09-838c-69ee094072ef
caps.latest.revision: 15
author: msftman
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 90afbd14d09e937dcabdb0eabbfbba01479dc65f
ms.sourcegitcommit: df7fb20065cfafc153b4bc4019dff2c94f4ef567
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "4553244"
---
# <a name="sample-work-with-business-process-flows"></a>サンプル: 業務プロセス フローの使用

[!INCLUDE[cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

このサンプルでは、エンティティ レコードの業務プロセス フロー インスタンスの取得、業務プロセス フロー インスタンスとそのプロセス ステージのアクティブパスの取得、アクティブ ステージの変更などの業務プロセス フローをプログラムで処理する方法を示します。 これらの概念については、[Work with business process flows using code (コードを使用して業務プロセス フローを操作する) ](business-process-flows-code.md)を参照してください  

 このサンプルは [サンプル : ビジネス プロセス フローを使って作業する](https://go.microsoft.com/fwlink/p/?LinkId=846108) からダウンロードできます。  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>前提条件  
 サンプルを実行するには:  

1. Microsoft Dataverse 環境にアクセスできる。  

2. このサンプルで使用されている潜在顧客、営業案件、ワークフロー エンティティおよび業務プロセス フロー定義エンティティ レコードに関する適切な権限があります。  

3. サンプルを実行するために Visual Studio 2015 以降がある。  

4. インターネットに接続し、サンプル プロジェクトをダウンロードし、サンプル プロジェクトで使用されている NuGet パッケージを復元します。  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>このサンプルの概要  

1.  サンプルの潜在顧客レコードを作成します。 これにより、潜在顧客レコードに対して、「潜在顧客から営業案件への営業プロセス」の業務プロセス フローのインスタンスが自動的に作成されます。  

2.  潜在顧客レコードから営業案件レコードに変換します。  


4.  `RetrieveProcessInstances` メッセージを使用して、「営業案件」レコードに関連付けられた業務プロセス フロー インスタンスを取得します。 返されたコレクションの最初のレコードは、営業案件レコードのアクティブな業務プロセス フロー インスタンスで、この場合では、「リードから営業案件への営業プロセス」です。  

5.  `RetrieveActivePath` メッセージを使用して、「リードから営業案件への営業プロセス」インスタンスのアクティブ パスとプロセス ステージを取得します。  

6.  「リードから営業案件への営業プロセス」インスタンスの現在アクティブなステージを取得し、次のステージに移動するかどうかをユーザーに確認します。 移動することを確認すると、アクティブ パスの次のステージを、「リードから営業案件への営業プロセス」インスタンスのアクティブ ステージとして設定します。  

7.  最後に、 サンプルの実行で作成したレコードを削除するかどうかユーザーに確認します。  

     以下がサンプルの出力です:  

    ![サンプル出力](media/work-with-bpf-sample-output.png "サンプル出力")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>サンプルの実行  

1. WorkWithBPF Visual Studio サンプル プロジェクトを [ダウンロード](https://go.microsoft.com/fwlink/p/?LinkId=846108) し、コンピューター上のフォルダーに展開します。  

2. 展開されたフォルダで `WorkWithBPF.sln` ファイルを検索し、Visual Studio で開きます。  

3. サンプル プロジェクトでは、サンプルを実行する前に復元する必要のある NuGet パッケージを使用します。 NuGet パッケージの自動復元が Visual Studio で有効になっていることを確認します。 詳細: [NuGet パッケージの復元の有効化および無効化](https://go.microsoft.com/fwlink/?linkid=846106)  

    また、**プロジェクト** > **NuGet パッケージの管理** の順に選択してから、**復元** を選択し、サンプルで使用するパッケージを手動で復元します。  

4. F5 キーを押すか、または **デバッグ** > **デバッグ開始** の順に選択します。  

5. これまでどのサンプルも実行したことがない場合は、コードを実行するために情報を入力する必要があります。実行したことがある場合は、以前に設定したいずれかのインスタンスの番号を入力します。  


   |                                 プロンプト                                  |                                                                                             内容                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Dynamics 365 Server の名前とポート [crm.dynamics.com] を入力してください       | Dynamics 365 Server の名前を入力します。 北米では、既定は Dynamics 365 (online)  (crm.dynamics.com) です。<br /><br /> 例:  <br />crm5.dynamics.com |
   | この組織は Microsoft Online Services でプロビジョニングされていますか (y/n) [n] |                                                 Microsoft Online Services でプロビジョニングされている組織の場合は、**y** を入力します。 その他の場合、**n** を入力します。                                                  |
   |                          domain\username を入力してください                          |                                                                                    Microsoft アカウントを入力します。                                                                                     |
   |                             パスワードを入力してください                              |                      パスワードを入力します。 文字はウィンドウに “\*” で表示されます。 パスワードは、後で再利用できるように Microsoft Credential Manager で安全に保存されます。                       |
   |                組織番号を指定してください (1-n) [1]                 |                      組織の一覧から、所属する組織に該当する番号を入力します。 既定値は 1 です。これは一覧の最初の組織を示します。                       |


6. このサンプルでは、「[このサンプルの概要](#what-this-sample-does)」で説明されている操作を実行します。また、追加オプションの入力が求められる場合があります。  

7. サンプルが完了したら、[Enter] を押して、コンソール ウィンドウを閉じます。  

