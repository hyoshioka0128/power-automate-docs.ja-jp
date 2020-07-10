---
title: Power Automate のデータ グループ | Microsoft Docs
description: Microsoft Power Apps と Power Automate で使用するデータ グループの概要。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/26/2016
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 4624fac246eaac29e9c67590e3253e993173e8c2
ms.sourcegitcommit: aec3a74472b4e6eb70ed4554d14b57a7324d123d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "3498440"
---
# <a name="learn-all-about-data-groups"></a>データ グループについて詳しく学ぶ

## <a name="what-is-a-data-group"></a>データ グループとは
データ グループは、[データ損失保護 (DLP) ポリシー](https://docs.microsoft.com/power-platform/admin/wp-data-loss-prevention) 内でサービスを分類するための簡単な方法です。 **ビジネス データのみ**グループおよび**ビジネス データは許可しない**グループの、2 つのデータ グループが使用可能です。 組織は、どのサービスを具体的なデータ グループに配置するか、自由に決定することができます。 サービスを分類する良い方法は、組織への影響に基づいてグループに配置することです。 既定では、すべてのサービスは、**ビジネス データは許可しない**グループに配置されています。 管理センターから DLP ポリシーのプロパティを作成するか、または修正する時に、データ グループのサービスを管理します。

## <a name="how-data-is-shared-between-data-groups"></a>データ グループ間でデータを共有する方法
異なるグループにあるサービス間でデータを共有することはできません。 たとえば、**ビジネス データのみ** グループに SharePoint と Salesforce を配置し、**ビジネス データ禁止** グループに Facebook と Twitter を配置した場合は、SharePoint  と Facebook の間でデータを移動させるフローを作成することはできません。 異なるグループのサービス間でデータの共有はできませんが、特定のグループ内のサービス間ではデータを共有することができます。 そのため、前の例に戻ると、 SharePoint と Salesforce は同じデータ グループに配置されたため、エンド ユーザーが作成したフローでは SharePoint と Salesforce の間でデータを共有できます。 同様に、エンド ユーザーは Facebook と Twitter の間でデータを共有するフローや Power Apps を作成できます。 重要なポイントは、特定のグループにあるサービス間でデータの共有を行うことができ、異なるグループにあるサービス間ではデータは共有できません。  

また、1 つのデータ グループは*既定*グループに指定されている必要があります。 最初は、**ビジネス データは許可しない**グループが*既定*グループで、すべてのサービスがそのデータ グループにあります。 管理者は、既定のデータ グループを**ビジネス データのみ**グループに変更できます。 **注** フローに追加された新しいサービスは指定の *既定* グループに配置されます。 したがって、**ビジネス データは許可しない**を既定のグループにのままにし、ビジネス データを新しいサービスに共有する許可の影響を組織が検証した後に手動で**ビジネス データのみ**グループにサービスを追加することをお勧めします。

## <a name="add-services-to-a-data-group"></a>データ グループにサービスを追加します。
このチュートリアルでは、SharePoint および Salesforce をデータ損失防止 (DLP) ポリシーの**ビジネス データのみ**データ グループに追加します。 

1. DLP ポリシーの**ビジネス データのみ**グループ ボックス内にある **+ 追加**リンクを選択します。    
   ![画像の追加](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. SharePoint および Salesforce を選択し、**サービスの追加**を選択して両方をビジネス データのみグループに追加します。    
   ![サービスの追加の画像](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. 上部のメニューから**ポリシーの保存**を選択します。  
   ![ポリシーの保存](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. SharePoint Salesforce の両方がビジネス データのみグループにあります。  
   ![更新されたビジネス データ グループ](./media/introduction-to-data-groups/add-to-data-group-3.png)   

このチュートリアルでは、SharePoint および Salesforce が DLP ポリシーの**ビジネス データのみ**データ グループに追加されました。 DLP ポリシーの環境に属する人物が  SharePoint または Salesforce と **ビジネス データ禁止** データ グループのサービスの間でデータを共有するアプリを作成した場合、そのアプリの実行は許可されません。

## <a name="remove-services-from-a-data-group"></a>データ グループからサービスを削除
すべてのサービスは 1 つの使用可能なデータ グループにある必要があるので、特定のグループからサービスを削除するにはサービスを他のグループに追加してポリシーを保存します。  

## <a name="change-the-default-data-group"></a>既定のデータ グループの変更
このチュートリアルでは、既定のデータ グループを**ビジネス データは許可しない**データ グループから**ビジネス データのみ**データ グループに変更します。  

**重要** フローに追加された新しいサービスは指定の *既定* グループに配置されます。 したがって、**ビジネス データは許可しない**を既定のグループにし、**ビジネス データのみ**グループには手動でサービスを追加することをお勧めします。

1. 既定のデータ グループとして指定したいデータ グループの右上隅にある **...** を選択します。    
   ![既定のグループの変更](./media/introduction-to-data-groups/default-data-group-0.png)  
2. **既定のグループとして設定**を選択します。  
   ![既定のグループの変更](./media/introduction-to-data-groups/default-data-group-1.png)   
3. 上部のメニューから**ポリシーの保存**を選択します。  
   ![既定のグループの変更](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. データ グループが既定のデータ グループとして指定されました。  
   ![既定のグループの変更](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>次のステップ
* [デデータ損失防止 (DLP) ポリシーに関する詳細](https://docs.microsoft.com/power-platform/admin/wp-data-loss-prevention)
* [環境に関する詳細](environments-overview-admin.md)   

