---
title: 変数ペインの管理 | Microsoft Docs
description: 変数ペインを管理する
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
ms.openlocfilehash: f49b15e4f8deb773581be0d0450f8dbcf89a0357
ms.sourcegitcommit: b043b7e8c29afee4f4f25bbf0d5a662d9af9272c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "4711647"
---
# <a name="manage-variables-and-the-variables-pane"></a>変数と変数ペインを管理する



**変数** ペインには、Power Automate Desktop との間で渡される入出力変数が表示されます。 また、 **フロー変数s** の配下に現在のフローで使用されているすべての変数が表示されます。 
<!--note from editor: We should not use bold on the name. -->

![変数ペイン。](media\variables-pane\variables-pane.png)

**変数** ペインでは、変数の検索、名前の変更、使用率を確認し、タイプ別にフィルターできます。 

フローが実行されると、各変数の名前の横に現在の値が表示されます。 無効化されたアクションの変数は省略されています。

![変数ペインに表示される現在の変数の値です。](media\variables-pane\variables-pane-run-values.png)

## <a name="renaming-a-desktop-variable"></a>デスクトップ変数の名前を変更する

デスクトップ フロー変数の名前を変更するには、 **変数** ペインで名前を右クリックし、**名前の変更** を選択します。 変数の名前は、その発生するすべての場所で更新されます。

![フロー変数の名前変更オプションです。](media\renaming-variables\rename-flow-variabe.png)

アクションを通して変数名を手動で更新することができますが、名前はこれらの特定のアクションでのみ変更され、グローバルには変更されません。 

入出力変数の名前をグローバルに更新するには、**変数** ペインでその名前を右クリックし、**編集** を選択します。

![入出力変数の名前を変更します。](media\renaming-variables\rename-external-variabe.png)

**変数の編集** ダイアログ ボックスで、内部変数名と外部変数名で使用する **変数名** フィールドと **外部名** フィールドを入力します。 

![変数を編集するダイアログ ボックス](media\renaming-variables\edit-variable-window.png)

## <a name="input-and-output-variables"></a>入出力変数

Power Automate Desktop では、入力変数と出力変数を使って  Power Automate プラットフォームとのデータ交換を可能にします。
<!--note from editor: We do not use bold font on names like this. -->

これらの変数は Power Automate Desktop との間でやり取りされ、高度なフローを作成することができます。 Power Automate では、入力変数はすべてフィールドとして UI アクションに追加されます。 Power Automate Desktop と Power Automate 間のデータの受け渡しについては、[クラウド フローを使用して Power Automate Desktop フローをリンクする](link-pad-flow-portal.md)で詳しく解説されています。
<!--note from editor: Suggest for this previous sentence "You can find more information about passing data between Power Automate Desktop and Power Automate in <add article title as a link>."-->

入出力変数を作成するには、[**変数**](manage-variables.md)ペインで **+** ボタンを選択し、それぞれのオプションを選択します。
<!--note from editor: Instead of using the + button, use the name that appears when you hover over the + sign and possibly put the plus sign after it like this <name of button> (+). -->

![変数ペインのプラス ボタンをクリックすると、新しい入力変数と出力変数が作成されます。](media\input-output-variables\create-input-output-variable.png)

  
**新しい入力変数の追加** ダイアログ ボックスで、次のフィールドに入力します:
- **変数の型** : 変数が入力か出力かを定義します。
- **変数名**: フローにおけるの変数の名前です。
- **既定値** : Power Automate Desktop フロー デザイナーまたは Power Automate Desktop コンソールからフローを実行する際の既定の値です。
- **データ型** : 数値、テキスト、日付などの変数の型です。
- **外部名称**: フロー デザイナーの外部で使用する名称です。 外部名は Power Automate に表示される名前です。
- **説明**: 変数の説明です。 このフィールドは必須であり、Power Automate に表示されます。

![新しい入力変数の追加ダイアログ ボックス](media\input-output-variables\Add-new-input-variable-window.png)

![新しい出力変数の追加ダイアログ ボックス](media\input-output-variables\Add-new-output-variable-window.png)


