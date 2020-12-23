---
title: Power Automate オートメーションのテスト用ツール | Microsoft Docs
description: この記事では、フローをチェックし、オートメーションの実行時に発生するエラーを検出するために使用できるさまざまなツールを紹介します。
author: taiki-yoshida
ms.service: flow
ms.topic: conceptual
ms.custom: guidance
ms.date: 12/10/2020
ms.author: tayoshi
ms.reviewer: kathyos
ms.openlocfilehash: a97d7cc62f1feda611239bf64368090f73f1d84c
ms.sourcegitcommit: 970ad18a7ef795bff294f39ccfc8578bab9387d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "4714403"
---
# <a name="tools-to-test-your-automation"></a>オートメーションをテストするツール

この記事では、基本的なエラーのフローをチェックし、オートメーションの実行時に発生するエラーを検出するために使用できるさまざまなツールを説明します。

## <a name="flow-checker"></a>フロー チェッカー

このツールは、作成したオートメーションの問題とエラーをチェックします。 オートメーションの設定を完了した後、フロー チェッカーを実行して誤りがないか確認します。 詳細については、[フロー チェッカーでエラーを検索して修正する](../../error-checker.md) を参照します

## <a name="repair-tips"></a>修復のヒント

オートメーションが失敗した場合、オートメーションの作成者または所有者に修復のヒントが自動的に送信されます。 これらのヒントには、失敗に関する実用的な情報が含まれています。 詳細については、[フローのトラブルシューティング](../../fix-flow-failures.md) を参照します

## <a name="custom-error-notifications"></a>カスタム エラーの通知

修復のヒントがエラー通知のニーズを満たさない場合 &mdash; たとえば、所有者だけではなくさらに多くの人に失敗について通知する必要がある場合 &mdash; 前のステップが失敗した時だけ実行するアクションを設定することにより、カスタム エラー通知を設定することができます。

以下の例では、**マネージャーの取得 (V2)** アクションの実行に失敗した場合、**メール通知を送信する (V3)** アクションが実行されます。

![前のステップが失敗した後に実行するアクションを設定する](media/custom-error-notifications.png "前のステップが失敗した後に実行するアクションを設定する")

> [!div class="nextstepaction"]
> [次のステップ: デプロイと調整フェーズ](deploy-to-production.md)