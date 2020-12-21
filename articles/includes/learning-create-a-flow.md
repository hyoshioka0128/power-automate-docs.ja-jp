Power Automate のガイド付き学習にようこそ。 このレッスンでは、Power Automate の環境についてさらに説明し、**最初のフローを構築** できるようにします。

Power Automate は簡単に使い始めることができます。多数の **テンプレートから選択** して、既に使っているサービスにいっそう有意義な方法で接続できます。  

## <a name="power-automate-templates"></a>Power Automate のテンプレート
[Power Automate の Web サイト](https://ms.flow.microsoft.com)で、**テンプレート** メニューを開いてみてください。 一覧をスクロールすると、Power Automate で多くのサービスに接続できることがわかります。

![Flow Web サイト -> テンプレート一覧](./media/learning-create-a-flow/template-list.png)

## <a name="choose-a-template"></a>テンプレートを選択する
メールで **添付ファイルを探す** のは時間のかかる作業ですが、このフローを使って OneDrive のフォルダーに **メールのすべての添付ファイルを格納する** と、時間を節約できます。

**Office 365 のメールの添付ファイルを OneDrive for Business に保存する** テンプレートを選択します。

![Office 365 電子メール](./media/learning-create-a-flow/office-365-email.png)

## <a name="create-and-administer-a-cloud-flow"></a>クラウド フローを作成して管理する
これは **ワン クリック** テンプレートの 1 つであり、**フローの構築に必要な** 関連する質問に答えるだけです。

テンプレートのグラフィックには、成功するためにテンプレートが **行うことと、必要とすること** についての **説明** があります。

**Office 365 Outlook** サービスと **SharePoint** サービスの **資格情報の入力** を求められます。 両方のサービスを定期的に使っている場合は、既にサインインされています。

![Office 365 のメールを保存する](./media/learning-create-a-flow/save-flow-office-description.png)

1. **フローの作成** を選択します。
   
    ![[フローの作成] をクリックする](./media/learning-create-a-flow/click-create-flow.png)
   
    結果が表示されます。 
   
    ![作成成功](./media/learning-create-a-flow/create-successful.png)
   
    フローによって OneDrive に **フォルダーが作成** され、仕事用メール アドレスにメールで送られてきた **すべての添付ファイル** がここに自動的に格納されます。
2. **自分のフロー** を開きます。
   
    ![自分のフローを開く](./media/learning-create-a-flow/click-my-flows.png)
3. **作成したフロー** を選択し、動作を確認します。
   
    ![フローを選択する](./media/learning-create-a-flow/click-the-flow.png)
4. **緑のチェック マーク** が表示されます。これは、**フローが成功した** ことを示します。 **成功** を選択すると、実行履歴と結果が表示されます。
   
    ![フローの成功](./media/learning-create-a-flow/flow-successful.png)
   
    **フローのすべての部分** が正常に実行されました。 
   
    ![実行履歴](./media/learning-create-a-flow/run-history.png)

## <a name="important-concepts-in-power-automate"></a>Power Automate の重要な概念
フローを構築するときに知っておく必要のあることがいくつかあります。 すべてのフローには 2 つの主要部分があります。**トリガー** と、**1 つまたは複数のアクション** です。 

**トリガー** は、フローの開始アクションと考えることができます。この例での **新しいメールを受信したとき** や、SharePoint を使っている場合の **新しい項目が追加されたとき** などです。 **繰り返し** トリガーを使うと、固定スケジュールにすることもできます。繰り返しについては後で説明します。

**トリガーが呼び出された** ときに実行する **アクティビティがアクション** です。 たとえば、**ファイルの作成** は OneDrive にファイルを再作成します。

![新しいメールの着信時のアクション](./media/learning-create-a-flow/trigger-or-action.png)

その他にも、**メール** の送信、**ツイート** の投稿、**承認** の開始など、多くのアクションがあります。
これらはすべて、後で一から独自のフローを作成すると、動作するようになります。 

## <a name="next-lesson"></a>次のレッスン
次のレッスンでは、Power Automate モバイル アプリとその機能について説明します。 

