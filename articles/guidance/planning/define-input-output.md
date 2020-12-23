---
title: Power Automate プロジェクトの計画時に入力と出力を定義する | Microsoft Docs
description: この記事では、Power Automate プロジェクトの入力と出力を定義する方法、および機密データを保護する方法について説明します。
author: taiki-yoshida
ms.service: flow
ms.topic: conceptual
ms.custom: guidance
ms.date: 12/10/2020
ms.author: tayoshi
ms.reviewer: kathyos
ms.openlocfilehash: 0661c4d1fa3e6cecb87bd9fac86aafcc0b2674da
ms.sourcegitcommit: 970ad18a7ef795bff294f39ccfc8578bab9387d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "4714405"
---
# <a name="defining-inputs-and-outputs"></a>入力と出力を定義する

どの自動化にも、入力と出力があります。 Power Automate でプロセスの自動化を開始する前に、これらが何であるかを定義する必要があります。 

次の例は、入力と出力を定義する方法を示しています。

経費承認シナリオでは、Abhay は、経費フォームを提出した申請者に払い戻しを行うために、次の手順を実行する必要があります。

1.  Abhay は、経費報告書の承認要求を受け取ります。

2.  Abhay は、要求を承認するか拒否するかを決定します。

3.  要求が承認されると、Abhay は従業員にメールを送信して通知します。

次の表は、このシナリオで必要な情報を示しています。

| 必要な情報       | 入力か出力か?    | 目的                                                     |
|----------------------------|---------------------|-------------------------------------------------------------|
| 従業員の名前            | 入力               | 経費が承認された場合にメールを送信するには                     |
| 従業員のメール           | 入力               | 経費が承認された場合にメールを送信するには                     |
| 従業員の従業員番号 | 入力               | 従業員管理システムで銀行番号を検索する方法。 |
| 承認結果            | 出力              | 経費が承認された場合にメールを送信するには                     |
| 承認者名            | 出力              | 経費が承認された場合にメールを送信するには                     |
| 承認者のメール           | 出力              | 経費が承認された場合にメールを送信するには                     |
| 承認の日時     | 出力              | 経費が承認された場合にメールを送信するには                     |

大変な作業に思えるかもしれませんが、入力の大部分は自動的に取得することができます。 たとえば、自動化が従業員によって手動でトリガーされた場合、従業員の名前と電子メールを取得できます。

## <a name="securing-inputs-and-outputs"></a>入力と出力をセキュリティ保護する

サインイン ID、パスワード、銀行情報などの機密データを処理している場合は、Power Automate で安全な入出力機能を使用できます。

![安全な入力と安全な出力の設定](media/secure-input-output.png "安全な入力と安全な出力の設定")

Power Automate では既定で、フローの実行履歴で入力と出力を確認できます。 安全な入力と出力を有効にすると、誰かが入力と出力を調査しようとしたときにこのデータを保護し、代わりに「セキュリティ構成のためコンテンツが表示されません」というメッセージを表示できます。

![安全な入力と出力を有効にした実行履歴のサンプル](media/sample-run-history.png "安全な入力と出力を有効にした実行履歴のサンプル")

> [!div class="nextstepaction"]
> [次のステップ : 機密テキストの処理](../../desktop-flows/run-desktop-flow.md#use-sensitive-text-inputs)