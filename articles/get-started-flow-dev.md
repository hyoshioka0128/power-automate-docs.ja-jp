---
title: カスタム コネクタの作成とフローの埋め込み | Microsoft Docs
description: カスタム コネクタの作成と共有、クラウド フローの埋め込みなどを行います。
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
ms.date: 11/22/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5a4a0bfb4a1ab3b28e260616c20549efc707fcc8
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4709543"
---
# <a name="start-to-build-with-power-automate"></a>Power Automate のビルドを開始する


Power Automate を使用してアプリケーションを拡張する方法をいくつか次に示します：

* カスタム コネクタを作成して接続します。
* すべての Power Automate ユーザーとカスタム コネクタを共有します。
* アプリ内からフロー エクスペリエンスを埋め込みます。
* ユーザーが Power Automate  を自身に最適な方法で操作できるようにすべてのカスタム コネクタを強調表示します。

## <a name="prerequisites"></a>前提条件

* [Power Automate](https://flow.microsoft.com)のアカウント。

## <a name="create-a-custom-connector"></a>カスタム コネクタの作成

Power Automate から接続したい Web サービスがある場合は、最初に、カスタム コネクタを作成する必要があります。 カスタム コネクタを登録すると、必要な認証、サポートされるトリガーとアクション、アクションごとのパラメーターと出力など、Web サービスの特性が Power Automate に提供されます。

このチュートリアルで、[カスタム コネクタを登録して使用する](https://powerapps.microsoft.com/tutorials/register-custom-api/) 方法を理解してください。 カスタム コネクタの登録後は、テストのために組織内で共有することができます。

## <a name="share-a-custom-connector-with-all-power-automate-users"></a>すべての Power Automate ユーザーとカスタム コネクタを共有します

カスタム コネクタを完全にテストしたら、 [レビュー プロセス](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) を開始して、他のすべての Power Automate ユーザーと共有するために Microsoft からの承認を受けてください。

レビュー プロセスに必要なものを次に示します。

* API と認証情報を表す OpenAPI ファイルです。
* コネクタのアイコンです。
* コネクタの説明です。
* テンプレートによって、コネクタがどのように他のユーザーに役立つかに関する約 10 個のアイデアです。

この情報の送信後に、Power Automate  と Microsoft Power Apps で API の機能の評価が開始されます。

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>Web サイトまたはアプリにフロー エクスペリエンスを埋め込む

アプリ内に Power Automate  を[埋め込み](developer/embed-flow-dev.md) して、ご利用のアプリと Power Automate でサポートされる他のすべてのサービスをコンテキスト内で深く統合することができます。 たとえば、以下を実行できます。

* サービスに関連するすべてのテンプレートを参照し、ユーザーがテンプレートを選択できるようします。
* ユーザーがアプリに関連付けたフローを管理します。

## <a name="next-steps"></a>次の手順

アプリに Power Automate を [埋め込む](developer/embed-flow-dev.md) 方法を説明します。
