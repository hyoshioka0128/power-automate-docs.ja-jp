[Power Automate](https://flow.microsoft.com) でワークフローを構築する際に利用できる[サービス](https://flow.microsoft.com/services)の数が増えると、SharePoint や Salesforce のような企業サービスに保存されている企業の重要な機密データを守る必要がでてきます。 会社の機密データを Twitter や Facebook のような消費者向けサービスに公開しないためのポリシーを作成する必要があります。 Power Automate を使用すると、[**データ損失防止** (DLP)](https://docs.microsoft.com/power-platform/admin/prevent-data-loss) ポリシーを簡単に作成できます。ユーザーがフローを作成するとき、会社のデータが共有される消費者向けサービスを厳重に管理できます。  

## <a name="terms-you-should-get-familiar-with"></a>重要な用語

| 用語 | 説明 |
| --- | --- |
| **DLP** |これは Data Loss Prevention (データ損失防止) の省略形です。 DLP ポリシーを作成し、**サービス**間のデータ共有を管理します。 |
| **サービス** |[サービス](https://flow.microsoft.com/services)とは、Salesforce、SharePoint、Twitter のようなアプリケーションのことです。 フローの作成時に、このようなサービスやその他多くのサービスが利用されます。 |
| **データ グループ** |サービスを論理的にグループにしたものです。 データを共有できるサービスを同じデータ グループに配置します。 **ビジネス データのみ**と**ビジネス データ禁止**という 2 つのデータ グループがあります。 |
| **環境** |DLP は[環境](../environments-overview-admin.md)に適用されます。 環境にはユーザーが含まれます。 |
| **ユーザー** |ユーザーは組織のメンバーであり、環境内でのメンバーシップに基づいて DLP ポリシーが適用される対象です。 |
| **フロー** |フローは、利用可能なサービスを組み合わせて使用するワークフロー アプリです。 |

## <a name="all-about-how-dlp-policies-work"></a>DLP ポリシーの動作の概要
DLP ポリシーとは、簡単に言えば、相互排他的な 2 つのデータ グループの 1 つに各サービスを配置するルールに名前を付けたものです。 このルールが環境に適用されます。 環境はユーザーを論理的にグループにしたものです。 ユーザーは、異なるデータ グループに配置したサービス間でデータを共有するフローを作成できません。 つまり、ユーザーが作成できるのは、**1 つ**のデータ グループ内のサービス間でデータを共有するフローだけです。 データ グループをまたいだ共有はできません。  

| **データ グループ名** | **データ グループの説明** |
| --- | --- |
| **ビジネス データのみ** |このグループのすべてのサービスが互いにデータを共有できます。 **ビジネス データ禁止**データ グループとデータを共有することはできません。 |
| **ビジネス データ禁止** |このグループのすべてのサービスが互いにデータを共有できます。 **ビジネス データのみ**データ グループとデータを共有することはできません。 |

**注**: 1 つのデータ グループにサービスを追加すると、もう一方のデータ グループからそのサービスが自動的に削除されます。 たとえば、Twitter が現在、**ビジネス データのみ**データ グループに読み込まれているとき、ビジネス データを Twitter と共有しない場合、Twitter サービスを**ビジネス データ禁止**データ グループに追加します。 **ビジネス データのみ**データ グループから Twitter が削除されます。

## <a name="heres-what-you-need-to-create-a-dlp"></a>DLP を作成するために必要なもの
* Power Automate [Power Platform 管理センター](https://admin.powerplatform.microsoft.com/)へのアクセス  
* 環境管理者ロールのアカウント  
* 環境とそれに割り当てられたユーザー  

## <a name="create-a-dlp-policy"></a>DLP ポリシーを作成する
DLP ポリシーの作成方法は次のようになります。  

1. ポリシーに名前を付ける
2. ポリシーを適用する環境を選択する
3. 2 つのデータ グループのいずれかにサービスを追加する 特定のグループに配置されているサービスのみがデータを共有できます。2 つのデータ グループに配置されているサービス間でデータを共有するフローを作成すると、保存したときにフローが自動的にブロックされます。  

利用できる DLP ポリシーの詳細は[こちら](https://docs.microsoft.com/power-platform/admin/prevent-data-loss)でも確認できます。  

## <a name="examples"></a>例
* SharePoint、Office 365 ユーザー、Office 365 Outlook、OneDrive for Business、Dynamics 365、SQL Server、Salesforce の間だけでビジネス データを共有できるようにフローを制限するポリシーを作成すると、次のようになります。  
  ![](./media/learning-data-loss-prevention/a-few-business-centric-services.png)  
* SharePoint データを共有するフローの作成を特定の環境に属するユーザーに対して禁止するポリシーを作成すると、次のようになります。 SharePoint が**ビジネス データのみ**データ グループの唯一のサービスになっていることに注目してください。  
  ![ビジネス データのみ](./media/learning-data-loss-prevention/sharepoint-only-no-sharing-guided-learning.png)

