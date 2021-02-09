---
title: OneDrive for Business の起動パネルからフローを作成する | Microsoft Docs
description: OneDrive for Business の起動パネルからフローを作成する。
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/06/2020
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 405c725f949c3b0be7870c5b08b3855633cc2f74
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709231"
---
# <a name="create-flows-from-the-onedrive-for-business-launch-panel"></a>OneDrive for Business の起動パネルからフローを作成する


SharePoint の Power Automate [起動パネルと同様に](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/)、OneDrive for Business の特定のファイルに対してフローを実行できます。 

この機能によりフローの実行ユーザーが自分の資格情報を使用でき、これは特に IT 部門が作成したフローに適しています。 

ユーザーは **承認者** や **メッセージ** のようなランタイム入力のプロンプトを利用でき、これはテキスト、ファイル、メール、ブール値、数値のいずれかです。

このチュートリアルでは、多くの  [OneDrivefor Business テンプレート](https://flow.microsoft.com/search/?q=OneDrive) の 1 つを使用して、要求元の上司によるファイルの承認を要求するシンプルなフローを作成します。

## <a name="create-a-cloud-flow-that-requests-manager-approval-for-a-file-in-onedrive-for-business"></a>OneDrive for Business のファイルに対して上司の承認を要求するクラウド フローを作成する

1. OneDrive for Business にサインインします。
1. フローを作成するファイルを見つけて選択します。
1. **アクションの表示** リンク (3 つのドット) を選択します。
1. **自動化** > **Power Automate** > **フローの作成** を選択します。

     ![フローの作成](./media/onedrive-launch-panel/create-flow.png) 

1. テンプレートの 1 つを選択します。

    この例では **選択したファイルに対してマネージャーに承認を要求する** テンプレートを選択します。

     >[!TIP]
     >サインインが必要なすべてのコネクタにサインインします。

1. **続行** を選択します。
1. 必要な変更をテンプレートに加えてから、覚えやすい名前でフローを保存します。

## <a name="run-the-flow"></a>フローを実行する

1. OneDrive for Business にサインインします。
1. マネージャーに承認を要求するファイルを見つけて選択します。
1. **アクションの表示** リンク (3 つのドット) を選択します。
1. **フロー** を選択します。 先ほど作成したフローを確認します。
1. 先ほど作成したフローを選択します。

     ![フローを実行する](./media/onedrive-launch-panel/run-flow.png)


>[!TIP]
>このチュートリアルでは、テンプレートからクラウド フローを作成する方法について示しますが、一からクラウド フローを作成して、Power Automate で使用可能な多くのコネクタを使用することもできます。

## <a name="learn-more"></a>詳細情報を見る

- [Power Automate の概要](getting-started.md) 
- [複数ステップのフローを作成する](multi-step-logic-flow.md)
