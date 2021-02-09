---
title: Windowsレコーダー (V1)から Power Automate Desktop に移行する | Microsoft Docs
description: Windowsレコーダー (V1)から Power Automate Desktop に移行する。
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
ms.date: 12/17/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 63bf063d2a91c7c8ce0e985912e9f389c04b6f34
ms.sourcegitcommit: c9151fb52a7017f731c29cb74879e166322d6291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/18/2020
ms.locfileid: "4779501"
---
# <a name="migrate-from-windows-recorder-v1-to-power-automate-desktop"></a>Windows レコーダー (V1 )から Power Automate Desktop に移行する

従来の Windowsレコーダー (V1) で作成したデスクトップ フローを、 Power Automate Desktop フローにわずか数ステップで移行できます。

次の手順に従って、古いデスクトップ フローを移行します。

1. Power Automate にサインインします。
1. **マイ フロー** > **デスクトップ フロー** を選択します。
1. Power Automate Desktop に移行するデスクトップ フローを選択します。
1. **移行 (プレビュー版)** デスクトップ フローの詳細ページを選択します。

   ![デスクトップ フローの移行オプションを表示するスクリーンショット](media/migrate-win-recorder/migrate-button.png)

   移行ウィザードが起動します。

1. **移行** を選択します。

   ![移行ボタンを表示するスクリーンショット](media/migrate-win-recorder/migrate-wizard.png)
   
   プロセスが完了すると、デスクトップ フローのコピーが現在の環境に保存されます。 結果のデスクトップ フローは、Power Automate Desktop デザイナーを使用して編集できます。 元の Windows レコーダーのデスクトップ フローは変更されません。

   ![移行されたデスクトップ フローを表示するスクリーンショット](media/migrate-win-recorder/migrated-flow.png)

   >[!NOTE]
   >移行は、Windows レコーダー (V1) で構築されたデスクトップ フローでのみ使用できます。 SeleniumIDE で構築されたデスクトップ フローではサポートされていません。

新しいデスクトップ フローをテストした後は、既存のクラウド フローに移動して、UI のオートメーション アクションを置き換えることができます。 **Power Automate Desktop で構築されたデスクトップ フローを実行する** アクションを実行し、新しく作成されたデスクトップ フローを使用する必要があります。

## <a name="known-issues-and-limitations"></a>既知の問題と制限事項

- 移行では、 **WinAutomationを実行する** または **リモートデスクトッププロトコル (RDP)** アクションを含む Windows レコーダー (V1) フローはサポートされていません。

- 配列入力のあるフローはサポートされていません。

- ネイティブの SAP レコーディングを使用している Windows レコーダー (V1) デスクトップ フローはサポートされていません。 たとえば、**プロパティを設定する** または **呼び出しメソッド** アクションを含むデスクトップ フローはサポートされていません。 

>[!TIP]
>Windows レコーダー (V1) デスクトップ フローにアプリケーションを閉じる手順が含まれている場合は、変換されたデスクトップフ ローに **アプリケーションを閉じる** エラー処理手順を追加します。 このアクションの **エラー時** の条件を **フローを継続する** > **次のアクションに進む** に構成することができます。

>[!TIP]
>変換したデスクトップ フローの再生速度を変更するには、さまざまな **待機** アクションに適用する時間を更新します。 UI オートメーションの実行を成功させるには、十分な待機時間を確保するようにしてください。
