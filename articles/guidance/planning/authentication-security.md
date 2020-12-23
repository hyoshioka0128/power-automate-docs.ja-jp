---
title: Power Automate プロジェクト計画のための認証とセキュリティ | Microsoft Docs
description: さまざまな自動化のシナリオでは、Power Automate がさまざまな認証方法を使用するよう要求されます。 この記事では、それらについて説明しています。
author: taiki-yoshida
ms.service: flow
ms.topic: conceptual
ms.custom: guidance
ms.date: 12/10/2020
ms.author: tayoshi
ms.reviewer: kathyos
ms.openlocfilehash: 85bc23d9603a72eeafe3db6bbf0a0a111849fe1b
ms.sourcegitcommit: 970ad18a7ef795bff294f39ccfc8578bab9387d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "4714409"
---
# <a name="authentication-and-security"></a>認証とセキュリティ

自動化は、ユーザーにログインを要求することで保護されているデータやシステムにアクセスする可能性があります。 さまざまな自動化のシナリオでは、Power Automate がさまざまな認証方法を使用するよう要求されます。

自動化を設定する前に、手動でタスクを実行するために、システムまたはコンピューターに現在どのようにサインインしているかを自問する必要があります。 以下は、Power Automate での自動化の際に使用できるさまざまなタイプの認証 (サインイン) の例です。

![さまざまな種類の自動化](media/automation-types.png "さまざまな種類の自動化")

自動化を設定するには、必要な認証 (サインイン) 情報が用意されていることを確認してください。 この情報は、自動化を設定するために[新しい接続を作成する](../../add-manage-connections.md) とき、[オンプレミス データ ゲートウェイを介してデータにアクセスする](../../add-manage-connections.md#connect-to-your-data-through-an-on-premises-data-gateway) とき、または[デスクトップ フロー](../../desktop-flows/introduction.md) を使用するときに必要になります。

## <a name="on-premises-data-gateway"></a>オンプレミス データ ゲートウェイ

デスクトップ オートメーションおよび Web サイト オートメーションでは、オンプレミスのコンピューターにインストールされたプログラム (たとえば、ブラウザの拡張機能や Power Automate Desktop) に Power Automate のクラウドベースのサービスからアクセスできるように、オンプレミス データ ゲートウェイが必要です。 詳細 : 「[オンプレミス データ ゲートウェイのインストール](/data-integration/gateway/service-gateway-install)」

## <a name="authentication-by-using-microsoft-365-and-azure-ad"></a>Microsoft 365 および Azure AD を使用した認証

これは、Microsoft サービスで使用する自動化の認証です。 自動化が実行されると、最初に自動化を設定したユーザーではなく、自動化を実行しているユーザーに代わって実行されます。

![Azure AD サインイン画面](media/azure-ad-login.png "Azure AD サインイン画面")

## <a name="authentication-by-using-a-username-and-password"></a>ユーザー名とパスワードを使用した認証

この種類の認証は、Microsoft 365 と Azure Active Directory (Azure AD) で使用されているシステムとは別の独立したシステムがあり、ユーザー名とパスワードが異なるシステムとサービスで使用されます。 Google や Facebook、Twitter などのサービスへのサインインには、すべて独自の認証方法があります。 一部のエンタープライズ システムでは、[シングル サインオン (SSO)](/azure/active-directory/manage-apps/what-is-single-sign-on) を提供しています。

![ブラウザーのサインイン ポップアップ ウィンドウ](media/browser-login.png "ブラウザーのサインイン ポップアップ ウィンドウ")

経費報告の例では、オンライン バンキング システムには独自のサインイン ID とパスワードがあります。

## <a name="authentication-by-using-an-on-premises-system-or-windows-sign-in"></a>オンプレミスのシステムまたは Windows サインインを使用した認証

この種類の認証は、Power Automate Desktop アプリケーションまたはデスクトップ フローで自動化することを計画している場合に必要になります。 Microsoft 365 または Azure AD とは異なります。 コンピューターが社内ネットワークに接続されている場合、Windows Server Active Directory を使用している可能性が高くなります。

![Windows サインイン画面](media/windows-login.jpg "Windows サインイン画面")

## <a name="authentication-by-using-a-shared-key"></a>共有キーを使用した認証

この認証は通常、オンライン サービスに使用され、サービスが会社全体で共有されるシステム間 (API) の自動化に使用されます。 これは通常、コネクタが共有されている IT 部門によって提供および設定されます。

![Azure ポータルの API キー](media/azure-api-key.png "Azure ポータルの API キー")

> [!div class="nextstepaction"]
> [次のステップ : 入力と出力を定義する](define-input-output.md)