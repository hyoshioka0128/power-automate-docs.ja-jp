---
title: Microsoft 365 メールと Power Automate の概要 | Microsoft Docs
description: Microsoft 365 メールと Power Automate の概要。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f7e623cc15297c369be172b1c53bcef2c9f5535c
ms.sourcegitcommit: 83f74a9693056aad121481ecf38691b999441104
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "4513153"
---
# <a name="overview-of-office-365-outlook-email-use-with-power-automate"></a>Power Automate との Office 365 Outlook メールの使用に関する概要

コネクタは、接続するサービスを表します。 たとえば、OneDrive、SharePoint、または Twitter のコネクタを使用してこれらのサービスを使用できます。 メールを送受信するためのフローで使用される最も一般的なコネクタの 1 つは、[Outlook.com コネクタ](https://docs.microsoft.com/connectors/outlook/) と [Office 365 Outlook](https://docs.microsoft.com/connectors/office365/#connector-in-depth) コネクタです。 どちらのコネクタも同様の操作を提供し、メール、カレンダー、取引先担当者を管理できます。 これらの両コネクタを使用して、メールの送信、会議のスケジュール設定、取引先担当者の追加などのアクションを実行できます。

## <a name="outlookcom-or-office-365-outlook-which-connector-should-i-use"></a>Outlook.com または Office 365 Outlook: どのコネクタを使用すべきですか? 

職場または学校のメール アカウントを使用している場合は、Office 365 Outlook コネクタを使用します。 個人 (Microsoft アカウント) アカウントを使用している場合は、Outlook.com コネクタを使用します。 この記事では、Office 365 Outlook [トリガー](https://docs.microsoft.com/connectors/office365/#triggers) と [アクション](https://docs.microsoft.com/connectors/office365/#actions) のみを参照します。 Outlook.com コネクタにも同じ手法を使用できます。

## <a name="triggers"></a>トリガー

**トリガー** とは、フローを開始するイベントのことです。 例えば、**新しいメールが届いたとき (V2)** はメールが受信ボックスに到着したときにフローを開始するトリガーです。 これが、フローを開始するために使用できる [Office 365 Outlook トリガー](https://docs.microsoft.com/connectors/office365/#triggers) の完全リストです。 [メールのプロパティに基づいてフローをトリガーする](https://docs.microsoft.com/power-automate/email-triggers) 記事を使用して、メールのプロパティに基づいてフローをトリガーする方法の詳細をご覧ください。

これが Office 365 Outlook トリガーの部分的なリストです:

   ![一部の Office 365 Outlook トリガーのスクリーンショット](./media/email/email-triggers.png)


## <a name="actions"></a>アクション​​

**アクション** は、トリガー イベントが行われた *後* にフローに実行させたいイベントです。 たとえば、誰かが私にメールを送信したら、それを OneDrive に保存します。 これが、フローを開始するために使用できる [Office 365 Outlook トリガー](https://docs.microsoft.com/connectors/office365/#actions) の完全リストです。

これが Office 365 Outlook アクションの部分的なリストです:

   ![一部の Office 365 Outlook アクションのスクリーンショット](./media/email/email-actions.png)


## <a name="more-information"></a>詳細情報

- [メールを管理するフロー](create-email-flows.md) を作成します。
- [フロー内のメールをカスタマイズします](email-customization.md)。
- 上位の [メール シナリオ](email-top-scenarios.md) を表示します。


