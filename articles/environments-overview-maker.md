---
title: Power Automate の環境についての説明 | Microsoft Docs
description: 環境を使ってフローを分離する方法について説明します。
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/07/2020
ms.author: sunayv
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b797fc6e4a2e7835a7322f9fc55d50c96d113031
ms.sourcegitcommit: 27ee91452be26cf5c96397c39f9f5b8bede14cdb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80862563"
---
# <a name="choosing-an-environment"></a>環境の選択

この記事で紹介する Power Automate の**環境**を使うと、フロー、ゲートウェイ、接続、その他のリソースを作成して安全に分離できます。

以下について説明します。

* 環境が提供する機能。
* 環境の切り替え。
* 適切な環境でフローを作成する方法。

## <a name="environments-overview"></a>環境の概要

フローを作成するときに、フローおよびフローが使うリソースをホストする環境を選びます。 シナリオごとに異なる環境を使うことができます。

## <a name="here-are-a-few-scenarios-for-using-environments"></a>環境を使うシナリオの例

シナリオ|推奨事項
-----|-----
Common Data Service への接続を使用するフローを作成する。|フローと Common Data Service を同じ環境に配置します。 このため、すべてのデータは環境 (分離境界) 内で分離されます。
人事部門向けのフローを作成する。 人事部門のユーザーのみがそのフローにアクセスできるようにする必要があります。|環境を作成し、人事部のユーザーのみをそこに追加します。 フローおよびフローが使う他のリソースを、この環境に置きます。
フローを使って SharePoint のデータを表示するユーザーがヨーロッパにいる。|ヨーロッパに環境を作成し、フローと SharePoint 接続をその中に作成します。 このヨーロッパの環境では、すべてのリソースがヨーロッパに存在するため (データのローカリティ)、ヨーロッパのユーザーは最高のパフォーマンスを得られます。

環境を作成するには、Power Automate 管理者である必要があります。 管理者は、環境にアクセスできるユーザーを制御します。 環境の作成と管理の方法について詳しくは、[環境の管理](environments-overview-admin.md)に関するトピックをご覧ください。

## <a name="switching-environments"></a>環境を切り替える

Power Automate では、環境を簡単に切り替えることができます。 環境を切り替えると、その特定の環境で作成された項目のみが表示されます。他の環境にある項目が表示またはアクセスされることはありません。

次に例を示します。

*Human Resources* 環境に *NewEmployee* という名前のフローを作成してあります。 [Power Automate](https://flow.microsoft.com) で、*Sales* 環境を開きます。 *NewEmployee* フローは表示されません。 *NewEmployee* フローを表示するには、*Human Resources* 環境を開きます。 接続、ゲートウェイ、フローなど、その環境で作成した他のすべての項目にも同じルールが適用されることに注意してください。

環境を切り替えるには次の手順のようにします。

1. [Power Automate](https://flow.microsoft.com) にサインインします。
1. 右上隅に、自分のプロファイルを表す画像が表示されます。

   ![プロファイルの画像](./media/environments-overview-maker/default-environment.png)

1. 画像を選びます。 ドロップダウン リストに、自分が使用できるすべての環境が表示されます。 現在サインインしている環境にはチェック マークが表示されます。

   ![環境の一覧の画像](./media/environments-overview-maker/all-environments.png)
1. 別の環境に切り替えるには、一覧でその環境を選択します。

   ![切り替え先の環境を選ぶ](./media/environments-overview-maker/select-europe.png)
1. Power Automate が新しい環境に切り替わります。

## <a name="create-flows-in-the-right-environment"></a>適切な環境でのフローの作成

フローを作成する前に、フローとそのリソースを追加する環境を選びます。

> [!NOTE]
> 正しくない環境にフローを作成した場合は、フローを削除し、適切な環境に作成しなおす必要があります。

フローをホストする環境を選ぶときは、次のことを考慮してください。

* ゲートウェイは、既定の環境にのみ作成できます。 したがって、ゲートウェイを使ってフローをオンプレミスのデータに接続する場合は、既定の環境を使う必要があります。
* Common Data Service は、特定の環境に結び付けられています。 そのため、Common Data Service を使用するフローを作成する場合は、データベースがホストされている環境にフローを作成する必要があります。
* 自分がリソースを編集できるすべての環境が表示されます。 ただし、フローを作成する必要があるすべての環境への作成者としての追加は、管理者に依頼する必要があります。

> [!NOTE]
> 既定の環境でのフローの作成は常に行うことができます。

## <a name="next-steps"></a>次の手順

* [テンプレートからフローを作成する](get-started-logic-template.md)
* [フローを作成する](get-started-logic-flow.md)
* [管理者に関する環境の概要](environments-overview-admin.md)
