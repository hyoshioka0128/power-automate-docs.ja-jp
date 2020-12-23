---
title: サインアップおよびサインイン | Microsoft Docs
description: Power Automate にサインアップおよびサインインして、このプロセスに関する問題のトラブルシューティングを行います。
services: ''
suite: flow
documentationcenter: na
author: anjlic
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/04/2017
ms.author: anjlic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6e776ccabe00d67f474432ef000322aab7cfdeb1
ms.sourcegitcommit: 970ad18a7ef795bff294f39ccfc8578bab9387d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "4714105"
---
# <a name="sign-up-and-sign-in-for-power-automate"></a>Power Automate にサインアップおよびサインインする


個人用に Power Automate の使用を開始するのは簡単です! クラウド フローを作成する前に、任意の電子メール アドレスを使用してサインアップします。 そのアドレスでオンラインの Microsoft 製品を使用したことがない場合は、少し時間を取って登録する必要があります。

<iframe width="560" height="315" src="https://www.youtube.com/embed/cRkmSZrctLc?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

## <a name="sign-up-free"></a>無料でサインアップ
他のオンライン Microsoft 製品を使用したことがない場合、サインアップが必要になります。

1. [flow.microsoft.com](https://flow.microsoft.com) で、右上隅の **無料で試す** を選択します。
2. 電子メール アドレスを入力します。
3. 右矢印を選択します。

    ![サインアップ リンク](./media/sign-up-sign-in/signup.png)

## <a name="sign-in"></a>サインイン
仕事または個人で他のオンライン Microsoft 製品を使用したことがある場合、サインインするだけでかまいません。

1. [flow.microsoft.com](https://flow.microsoft.com) で、右上隅の **サインイン** をクリックまたはタップします。

    ![サインイン リンク](./media/sign-up-sign-in/signin.png)
2. 電子メール アドレスを入力します。
3. サインイン ページで、電子メール アドレスとパスワードを入力します。

## <a name="using-paid-features"></a>有料機能の使用
どなたでもサインアップして Power Automate の無料プランをご利用いただけます。 所属する組織で Office 365 または Dynamics 365 を購入しているようであれば、Power Automate のその他の機能を使用できる可能性があります。 有料の機能を使用したい場合は、90 日間無料試用版を開始するか、Power Automate Plan 1 または Plan 2 をご購入いただくこともできます。 [請求の詳細について](billing-questions.md) をご覧ください。

管理情報については、[組織の Q&A のフロー](organization-q-and-a.md) をご覧ください。

## <a name="troubleshooting"></a>トラブルシューティング​​
ほとんどの場合、このトピックで説明した簡単なプロセスで Power Automate に登録できます。 場合によっては、登録できないこともあります。この表では、サインアップできない場合の最も一般的な原因と、その回避策について説明します。


|                                                                                                                                                                                       現象/エラー メッセージ                                                                                                                                                                                        |                                                                                                                                                                              理由と回避策                                                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                       **Microsoft アカウントが作成されていない** <br> サインアップ中に電子メール アドレスを入力した後、次のようなメッセージが表示されます。<br><br> *その Microsoft アカウントは存在しません。別のアカウントを入力するか、新しいアカウントを取得してください。*                                                                                       |                                              Microsoft アカウントが作成されていない電子メール アドレスでサインアップしました。 そのページの **今すぐサインアップ** のリンクを選択すると、お使いの電子メール アドレスに対応する新しい Microsoft アカウントを作成できます。 既存の電子メール アドレスを使用して Microsoft アカウントを作成できます。                                               |
|                                                  **.gov または .mil の電子メール アドレス**<br>サインアップ中には次のようなメッセージが表示されます:<br><br>*Power Automate 利用不可: Power Automate は現時点では .gov または .mil の電子メール アドレスを持つユーザーは利用できません。別の職場の電子メール アドレスを使用するか、後でもう一度確認してください。*                                                  |                                                                                            現在、.gov または .mil のアドレスで Power Automate にサインアップすることはできません。 代わりに、*\@outlook.com* アドレスなど、任意の Microsoft アカウント電子メール アドレスを使ってサインインできます。                                                                                             |
| **セルフ サービス サインアップが無効になっている**<br><br>サインアップ中には次のようなメッセージが表示されます:<br>*サインアップを完了できません。IT 部門によって Power Automate のサインアップが無効になっています。IT 部門に連絡して、サインアップを完了させてください。* <br>or<br> *サインアップを完了できません。Microsoft Power Automate は現在、職場または学校では利用できないようです。* |                                                                                        **サインイン** ではなく **サインアップ** を選択しました。 ホーム ページ上部の **サインイン** を選択すると、Power Automate にアクセスできるようになります。                                                                                        |
|                                                   **電子メール アドレス は Office 365 ID ではありません**<br><br>サインアップ中には次のようなメッセージが表示されます:<br>*contoso.com であなたを見つけることができません。職場や学校で別の ID を使用していますか? それでサインインしてみて、うまくいかない場合は、IT 部門にお問い合わせください。*                                                    | 組織では ID を使用して、Office 365 やその他の Microsoft サービスにサインインしますが、それらの ID は電子メール アドレスとは異なります。 たとえば、ユーザーの電子メール アドレスは Nancy.Smith@contoso.com ですが、ID は nancys@contoso.com であることがあります。 サインアップを完了するには、Office 365 または他の Microsoft サービスにサインインするために組織が割り当てた ID を使用します。 |

## <a name="next-steps"></a>次の手順
* [テンプレートの使用を開始します](get-started-logic-template.md) は、設定済みの事前に構築されたフローです。
* 既にプロセスが決まっており、そのプロセスに合ったテンプレートが見つからない場合は、[空白から開始](get-started-logic-flow.md) を使用してください。
* [クラウド フロー プロジェクト](./guidance/planning/introduction.md) の計画に関するヘルプを参照します。

