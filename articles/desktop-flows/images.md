---
title: イメージ | Microsoft Docs
description: イメージ ペインを使用して、デスクトップ フローの画像を管理します。
author: olegmelnykov
ms.service: flow
ms.topic: article
ms.date: 09/22/2020
ms.author: olmelnyk
ms.reviewer: olmelnyk
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c88c66da2811a386c1c186f30a8deb904be2c96f
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711651"
---
# <a name="automate-using-images"></a>画像を使用して自動化する



右側のペインで、**イメージ** タブを選択します。

![イメージ ペイン](\media\images\images-pane.png)

**イメージをキャプチャする** を選択すると、虫眼鏡付きの十字線が表示されます。 虫眼鏡を使ってピクセル精度を上げ、クリック/ドラッグして画像をキャプチャします。

![イメージのキャプチャ](\media\images\capture-image.png)

さらに、**イメージのキャプチャ** ボタンの矢印を選択すると、タイマーで画像をキャプチャすることができます。 秒数を選択し、新しい値を入力してタイマーを調整します。

![遅延キャプチャ](\media\images\delay-capture.png)

画像をキャプチャした後、ダイアログ ボックスで画像の名前を指定し、**OK** を選択してフローに追加します。

![イメージ名称](\media\images\image-name.png)

**新しいフォルダーの追加** を選択し、名前を指定してイメージにフォルダを作成します。 特定のフォルダが開いているときに画像をキャプチャして、フォルダに画像を並べ替えます。 **ホーム** をクリックして戻ります。

イメージやフォルダーの名前を変更、削除するには、アイテムを右クリックして適切な機能を選択します。 イメージのサムネイルを選択して開き、表示します。

![イメージの名前の変更/削除](\media\images\rename-delete-images.png)

### <a name="known-issues-and-limitations"></a>既知の問題と制限事項

- **問題**: 場合によっては、イメージの名前を変更すると、変更したイメージを使用したアクションが期待通りに動作しなくなる可能性があります。


- **回避策**: イメージを使用するアクションのいずれかを開いて保存すると、問題が解決されます


