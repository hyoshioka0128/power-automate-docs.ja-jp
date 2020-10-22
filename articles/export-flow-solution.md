---
title: ソリューション対応フローをエクスポートする方法の詳細情報 | Microsoft Docs
description: ソリューション対応フローをエクスポートする方法の詳細情報。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
ms.service: flow
ms.topic: article
ms.date: 10/06/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d359f1c065db1c089fb367d5b9ba1188da1e47a3
ms.sourcegitcommit: 1ae0dc87353b2ddec8c639d8a3514b7119401977
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "3968286"
---
# <a name="export-a-solution"></a>ソリューションのエクスポート


次の手順に従ってソリューションとその依存関係を新しい環境に移動します。

1. ナビゲーション バーから **ソリューション** を選択します。
1. エクスポート対象のアンマネージド ソリューションを選択してから **エクスポート** を選択します。 マネージド ソリューションはエクスポートできません。 詳細: [管理ソリューションとアンマネージド ソリューション](/power-platform/alm/solution-concepts-alm#managed-and-unmanaged-solutions)
1. **エクスポートする前に** が右側に表示されます。 以下のオプションを選んだ後で、 **次へ** を選択してください。  
    - **すべての変更を公開する**。 アンマネージド ソリューションをエクスポートすると、公開されたコンポーネントのみがエクスポートされることに注意してください。 **すべての変更を公開** を選択して、すべてのコンポーネントがエクスポートされたソリューションに含まれていることを確認することをお勧めします。 
    - **問題を確認する**。 ソリューションに対してソリューション チェッカーを実行して、パフォーマンスと安定性の問題を検出します。
1. **このソリューションをエクスポートする** が右側に表示されます。 次のオプションを入力または選択してから、**エクスポート**を選択してください。  
    - **バージョン ナンバー**：Power Automate現在のバージョンを表示し、ソリューションのバージョンを自動的にインクリメントします。 既定のバージョンを受け入れるか、独自のバージョンを入力できます。 
    - **エクスポート方式**:  **管理** 、または **非管理** のパッケージ タイプを選択します。 詳細: [管理ソリューションとアンマネージド ソリューション](/power-platform/alm/solution-concepts-alm#managed-and-unmanaged-solutions)

 エクスポートが完了するまでに数分かかる場合があります。 終了後、エクスポートされた zip ファイルは、Web ブラウザーで指定されたダウンロード フォルダーで使用可能になります。

> [!NOTE]
> 組織に正常なアプリケーション ライフサイクル管理 (ALM) を実装するには、ソース管理システムを使用してソリューションを格納およびコラボレーションし、ソリューションのエクスポート プロセスを自動化することを検討してください。 詳細: Power Platform ALMガイドの [ALMの基本](/power-platform/alm/basics-alm)。

## <a name="learn-more"></a>詳細情報を見る


* [ソリューションの作成](./overview-solution-flows.md)
* [ソリューションにフローを作成する](./create-flow-solution.md)
* [ソリューションのインポート](./import-flow-solution.md)
* [ソリューション対応フローを編集する](./edit-solution-aware-flow.md)
