---
title: 古いリリース バージョンの UI フロー アプリと接続を更新する |Microsoft Docs
description: 古いリリース バージョンの UI フロー アプリと接続を更新します。
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
ms.date: 03/03/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 674dece31458f5e4930c7e77a3bd3545ba3fadca
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711681"
---
# <a name="upgrade-ui-flows-app-and-connections-from-previous-releases"></a>古いリリース バージョンの UI フロー アプリと接続を更新する

2 月のリリースでは、いくつかの基礎となるコンポーネントが修正されており、無人サポートのいくつかの機能を追加しています。 これらの新機能 (無人機能を含む) を使用するには、ローカル UI フロー アプリとゲートウェイ接続を更新する必要があります。

### <a name="what-does-it-mean-for-my-existing-ui-flows"></a>既存の UI フローはどうなりますか？

UI フローアプリを更新するか、ゲートウェイへの接続を更新するまでアクションは必要ありません。 同時に両方を更新する必要があります。

### <a name="how-do-i-upgrade"></a>アップグレードするには?

1.  [最新の UI フロー アプリ](https://go.microsoft.com/fwlink/?linkid=2102613&clcid=0x409)をダウンロードし、ご利用のデバイスにインストールします。

1.  UI フロー アプリがインストールされているデバイスごとに、次の手順に従います :

    1. [Power Automate](https://powerautomate.microsoft.com) にサインインする。
    1. 画面左側の **データ** を展開します。
    1. **接続** を選択します。
    1. デバイスをターゲットとする UI フロー接続を編集します。
    1. 接続する資格情報を入力して保存します。

    >[!IMPORTANT]
    >[UI フローの接続とマシンの資格情報を設定する](setup.md#setup-desktop-flows-connections-and-machine-credentials)で説明されているように、適切な資格情報を使用するようにしてください。 正しい資格情報を使用することで、接続が更新され、一般的に利用可能な UI フローのコード パスが使用されるようになります。

## <a name="next-steps"></a>次の手順

- [UI フローの設定](setup.md)方法についての詳細情報。 
- ワークフローを自動化するために使用可能な [さまざまな種類のフロー](..\flow-types.md) の詳細についての詳細情報。


