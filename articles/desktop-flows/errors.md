---
title: エラー | Microsoft Docs
description: エラー
author: georgiostrantzas
ms.service: flow
ms.topic: article
ms.date: 09/22/2020
ms.author: getrantz
ms.reviewer: ''
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 425ebe5ecdb879928b42955a186cb56535a7517d
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711654"
---
# <a name="manage-errors"></a>エラーを管理する



フローを開発して実行している間に、**デザイン時** エラーや **ランタイム** エラーの 2 つの異なるエラーが発生する場合があります。

**デザイン時** エラーは、展開されたアクションの構成に関連するものです。 フローの開発中にこのエラーが発生し、実行できなくなります。 空の必須フィールドや未定義の変数を使用すると、このようなエラーが発生する場合があります。

![設計時間エラー。](media\errors\design-time-error.png)

フリーの実行中に、**ランタイム** エラー、または例外が発生します。 これらのエラーは、例外処理の動作が設定されていない限り、フロー失敗の原因となります。 無効なファイルパスを指定すると、このようなエラーが発生する場合があります。 

![ランタイム エラー。](media\errors\run-time-error.png)

アクションによってエラーがスローされると、プラットフォームはその横にエラー アイコンを表示し、関連するエラー情報のポップアップ ペインを表示します。 

**エラー** ペインは 3 つのカラムに分割されます:

- **サブフロー**: エラーの原因となったアクションを含むサブフローの名前です。
- **アクション**: エラーを発生させたアクションの行番号です。
- **エラー**: エラー メッセージです。

発生したエラーが **デザイン時** エラーである場合、プラットフォームでアクション内にエラーの短い説明を表示します。 

![アクション内のエラーの説明です。](media\errors\error-action.png)

## <a name="the-error-detail-view"></a>エラー詳細表示

スローされた例外の詳細情報を確認するには、**エラー** ペインに移動し、それぞれのエラーをダブル クリックします。 すると、**エラーの詳細** ダイアログボックスが表示されます。 ダイアログ ボックスでは次の情報が表示されます:

1. **場所**: サブフローとエラーをスローしたアクション。
2. **エラー メッセージ**: エラー メッセージです。
3. **エラーの詳細**: エラーについての詳細な説明です。 これらの詳細は、エラーの発生理由と、その原因はについて明確な情報を伝えます。

![エラーの詳細ダイアログ ボックス](media\error-detail-view\error-details.png)