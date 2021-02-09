---
title: 組織における Power Automate サインアップの Q&A | Microsoft Docs
description: Office 365 テナントで Power Automate にサインアップするライセンス、管理、ユーザーに関するよくある質問と回答。
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
ms.date: 08/18/2020
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 103e2f9ca0bcd781407eaad78767ae2fb74804e0
ms.sourcegitcommit: 83e22ff7d539b02573548df5ca2a8bc41ea48227
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "4477255"
---
# <a name="power-automate-in-your-organization-qa"></a>組織の Power Automate に関する Q&A

[!INCLUDE[cc-data-platform-banner](./includes/cc-data-platform-banner.md)]

このトピックでは、組織内のユーザーが Power Automate を使用する方法と、Power Automate サービスを制御する方法について説明します。

## <a name="signing-up-for-power-automate"></a>Power Automate へのサインアップ

### <a name="what-is-power-automate"></a>Power Automate とは

Power Automate は、個人やチームを支援するパブリック クラウド サービスです。お気に入りのアプリとサービスの間のワークフローを自動化し、同期、通知の受信、データ収集などを行うことができます。 

### <a name="how-can-i-sign-up-for-power-automate"></a>どうすれば Power Automate にサインアップできますか?

[flow.microsoft.com](https://flow.microsoft.com) にアクセスして、画面の右上にある **無料試用版** 選択し、情報を入力して、サインアップ プロセスを完了します。

詳しくは、[Power Automate にサインアップする](sign-up-sign-in.md)をご覧ください。

### <a name="what-is-the-power-automate-free-license"></a>Power Automate Free ライセンスとは?

Power Automate Free ライセンスは追跡目的でのみ使用されます。 これを有効化または無効化しても、フローを作成するユーザーの機能に影響はありません。 Power Automate Free ライセンスを無効にした場合、ユーザーがログインするともう一度これが有効になります。 これは想定どおりの動作です。

### <a name="can-i-block-another-person-from-signing-up-for-power-automate"></a>Power Automate で他の人の登録を禁止できますか？

Power Automate は完全なパブリック クラウド サービスです。世界中のすべてのユーザーが Flow にサインアップし、Flow を使って日常のタスクを自動化できます。 Power Automate の使用に際して、Office 365 アカウントの作成や使用をする必要はありません。 このため、現時点では、他のユーザーが Power Automate を使うのを禁止するメカニズムはありません (世界中のすべてのユーザーがメール アドレスに関係なく使用できます)。

ただし、Power Automate に新規登録したユーザーが、組織内ではサポートしないことを選択した場合、そのユーザーが会社に費用を負担させることはできません。 個人が Power Automate にサインアップすると、その関係は、Bing、OneDrive、Outlook.com のような Microsoft の他のクラウド サービスと同様に、個人と Microsoft 間の関係になります。 Power Automate を個人で利用する場合は、組織がサービスの提供者として解釈されることは決してありません。

最後になりますが、会社が Power Automate 内の組織専用データの使用を制限する場合、[データ損失防止 (DLP) ポリシー](https://docs.microsoft.com/power-platform/admin/wp-data-loss-prevention)でそれを実行できます。

### <a name="how-can-people-gain-access-to-the-paid-features-of-power-automate"></a>どうすれば Power Automate の有料機能にアクセスできますか？

個人が Power Automate の有料機能を利用するには、3 つの方法があります。

1. Power Automate Free ライセンスに 90 日間無料で個別にサインアップすることができます。
2. [Microsoft 365 管理センター](https://admin.microsoft.com/) 内で、ユーザーに Power Automate ライセンスを割り当てることができます。
3. ユーザーには、Power Automate へのアクセスを含む Microsoft 365 および Dynamics 365プラン が割り当てられています。 Power Automate 機能を含む Office 365 および Dynamics 365 プランのリストについては、[Power Automate 価格設定ページ](https://flow.microsoft.com/pricing/) を参照してください。

### <a name="can-i-block-another-person-from-using-the-paid-features-of-power-automate"></a>Power Automate の有料機能を他の人が利用することを禁止できますか？

個人は誰でも Power Automate  の有料機能を 90 日間無料で試すことができます。コストは発生しません。 ただし、Office 365 管理ポータルを利用すれば、組織内の永久有料ライセンスの割り当てを完全管理できます。

無料提供と同様に、個人と Microsoft の間の直接的な関係である試用版に個人がサインアップすることを選択した場合、必ずしも会社が推奨する必要はありません。

## <a name="administration-of-power-automate"></a>Power Automate の管理

### <a name="why-has-the-power-automate-icon-appeared-in-the-office-365-app-launcher"></a>なぜ Power Automate のアイコンが Office 365 アプリ起動ツールに表示されるのですか?

8 月に発表されたように、Power Automate は Office 365 スイートの基本構成要素となりました。 この発表から 3 か月後、 Power Automate  は、すべての既存 の Office 365 でサービスとして有効になりました。 世界中のユーザーが Power Automate を利用できるようになったため、アプリ起動ツールに表示されています。

既定でアプリ起動ツールから Power Automate タイルを削除する方法については、次のセクションをご覧ください。

### <a name="how-do-i-remove-power-automate-from-the-app-launcher-for-my-organization"></a>組織のアプリ起動ツールから Power Automate を削除するにはどうすればよいですか？

ユーザーに Power Automate ライセンスが割り当てられている場合、次の手順でライセンスをユーザーから削除することができ、アプリ起動ツールから Power Automate アイコンが削除されます:

1. [Office 365 管理ポータル](https://admin.microsoft.com/) に移動します。
1. 左側のナビゲーション バーで、**ユーザー** > **アクティブ ユーザー** の順に選択します。
1. ライセンスを削除するユーザーを検索して、その名前を選択します。
1. ユーザーの詳細ペインで、**ライセンスとアプリ** タブを選択し、Power Automate のライセンスのチェックを外します。 
1. ペインの下部にある **変更の保存** を選択します。

ライセンスの一括削除も PowerShell から可能です。 詳細な例については、[Office 365 PowerShell でユーザー アカウントからライセンスを削除する](https://technet.microsoft.com/library/dn771774.aspx) を参照してください。   最後に、ライセンス内でのサービス一括削除に関するより詳細なガイダンスは、[Office 365 PowerShell でサービスへのアクセスを無効にする](https://technet.microsoft.com/library/dn771769.aspx) にあります。

組織のユーザーの Power Automate ライセンスまたはサービスを削除すると、そのユーザーの次の場所から Power Automate アイコンが削除されます:

>[!NOTE]
>このアクションにより、既定で Power Automate タイルが削除されます。 ユーザーは引き続き個人として Power Automate の使用を選択できます。

### <a name="why-did-10000-licenses-for-power-automate-show-up-in-my-office-365-tenant"></a>私の Office 365 テナントに、Power Automate のための 10,000 のライセンスが表示されました。

Power Automate Free を 90 日間試用でき、これらの試用版ライセンスは、テナント内の新規 Power Automate ユーザーの使用可能なキャパシティを表します。 これらのライセンスに対する料金は発生しません。

テナントの少なくとも 1 人のユーザーが、**Microsoft Power Automate 無料** ライセンスにサインアップしている場合、組織用として **請求** > **ライセンス** に 10,000 ライセンス (割り当てられたものを除く) が表示されます。

Office 365 ポータルから追加ライセンスをユーザーに自分で割り当てることができますが、それは Power Automate の試用版ライセンスであり、ユーザーに割り当ててから 90 日後に期限が切れることに注意してください。

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>これは無料ですか? これらのライセンスに料金は発生しますか?

明示的な同意なしにユーザーが組織にコストを発生させることはありませんので、無料ライセンスと試用版ライセンスのいずれも、組織に何の料金も発生させません。 また、実行クォータなど、クォータも使用しません。

### <a name="i-removed-the-power-automate-free-license-and-users-can-still-access-it"></a>Power Automate の無料版ライセンスを削除したが、ユーザーが引き続きアクセスできてしまう。

Power Automate の 無料ライセンスは、追跡目的でのみ使用されます。 最初のセクションで説明したように、他のユーザーが個人として Power Automate の使用を禁止することはできません。 そのため、Power Automate の無料ライセンスは実際にはいかなる機能も付与、または削除することはありません。

### <a name="why-cant-i-see-all-power-automate-licenses-in-the-office-365-admin-portal"></a>Office 365 管理ポータルにすべての Power Automate ライセンスが表示されないのはなぜですか？

Power Automate  は、個人または組織の一員として利用できます。 組織レベルのライセンスは Office 365 ポータルに常に表示されます。 しかしながら、個人として試用版に新規登録した場合、Office 365 の管理対象外となるため、ポータルには表示されません。

### <a name="how-does-an-individual-find-out-what-plan-they-are-on"></a>個人のプランを確認する方法はありますか?

[https://flow.microsoft.com/pricing](https://flow.microsoft.com/pricing) の Power Automate 価格ページでご自分のプランをご確認いただけます。 現在利用しているプランまたは試用版が表示されます。

### <a name="will-power-automate-sign-up-impact-the-identities-in-my-organization"></a>Power Automate を新規登録すると組織の ID に影響を与えますか？

組織に Office 365 環境が既にあり、組織のすべてのユーザーが Office 365 のアカウントを持っている場合、ID 管理に影響はありません。

もし組織に既存の Office 365 環境があるものの、すべてのユーザーが Office 365 アカウントを持っていない場合、テナントにユーザーが作成され、ユーザーの職場または学校の電子メール アドレスに基づいてライセンスが割り当てられます。 これは、組織内のユーザーがサービスにサインアップする度に、その時点で管理しているユーザーの数が増えるということを意味します。

もし組織に電子メール ドメインと接続された Office 365 環境がない場合、ID を管理する方法に変更はありません。 新しいクラウド専用ユーザー ディレクトリにユーザーが追加され、テナント管理者としてそれらを引き継ぎ管理することができます。

### <a name="a-new-tenant-was-created-by-power-automate-how-do-i-manage-this"></a>新しいテナントが Power Automate で作成されましたが、どのように管理すればよいですか？

Power Automate によって作成された新規テナントが作成された場合は、次の手順を使用して、当該テナントを要求し、管理することができます：

1. 管理したいテナント ドメインと一致する電子メール アドレスのドメインを使って Power Automate にサインアップし、テナントに参加します。 たとえば、Microsoft が contoso.com のテナントを作成した場合、@contoso.com で終わる電子メール アドレスを使ってテナントに参加します。
1. ドメインの所有権を検証することにより管理コントロールを要求します。テナントに入った後は、ドメインの所有権を検証することにより、自身を管理者ロールに昇格させることができます。 これを行うには、以下の手順に従ってください。    

   1. [https://admin.microsoft.com](https://admin.microsoft.com/Start?sku=flow_free) に移動します。
   1. 左上のアプリ起動ツール アイコンを選んで、[管理者] を選びます。
   1. **管理者になる** ページの指示を参照し、**はい、管理者になります** を選択します。  

       >[!TIP]
       >このオプションが表示されない場合は、Office 365 管理者は既に存在しています。

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>複数のドメインを持っている場合、ユーザーが追加された Office 365 テナントを制御することはできますか?

もし何もしないなら、各ユーザーの電子メール ドメインおよびサブドメインに対してテナントが作成されます。

メール アドレスの拡張に関係なく、すべてのユーザーを同じテナントにする場合は、事前にターゲット テナントを作成するか、既存のテナントを使用できます。 そのテナントで統合したいすべての既存のドメインおよびサブドメインを追加します。 そうすると、それらのドメインおよびサブドメインで終わる電子メール アドレスを持つすべてのユーザーは、サインアップすると自動的にターゲット テナントに参加します。

>[!IMPORTANT]
>テナント間でユーザーを移動するためのサポートされている自動化された方法はありません。 ドメインを 1 つの Office 365 テナントに追加することについては、[Office 365 にユーザーとドメインを追加する](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-ffdb2216-330d-4d73-832b-3e31bcb5b2a7) を参照してください。

### <a name="how-can-i-restrict-my-users-ability-to-access-my-organizations-business-data"></a>組織のビジネス データにアクセスするユーザーの機能を制限するにはどうすればよいですか?

以下に示すように、Power Automate を使用してビジネス データとビジネス以外のデータのデータ ゾーンを作成します。 いったんこれらのデータ消失防止ポリシーが実装されると、ユーザーはビジネスおよびビジネス以外のデータを組み合わせる Power Automate を作成したり実行したりすることができません。 詳細については、[データ消失防止 (DLP) ポリシー](prevent-data-loss.md) を参照してください。

  ![データ損失防止イメージ](./media/organization-q-and-a/data-loss-prevention-policy.png "データ損失防止イメージ")
