このトピックでは、**繰り返し** トリガーを使ってスケジュール済みのフローを実行する方法を説明します。  Contoso のマーケティング チーム用に、OneDrive 上の Excel テーブルから顧客のメール アドレスを自動的にプルするクラウド フローを構築します。 そして、1 日に 1 回、スプレッドシートに追加された新しいメール アドレスを MailChimp の顧客リストに追加するように、フローを構成します。 

## <a name="create-a-scheduled-flow"></a>予定フローを作成する
1. **Power Automate** を開き、**マイ フロー**、**一から作成** の順に選択します。 
   
    ![](./media/learning-recurrence/flow-create-blank.png)
2. **多数のコネクタやトリガーを検索する** を選択します。
3. **スケジュール** サービスを探して選び、**スケジュール - 繰り返し** トリガーを選びます。
   
    ![](./media/learning-recurrence/flow-recurrence-trigger.png)
4. **頻度** を **日** に、**間隔** を **1** に設定します。 **新しいステップ** を選び、**アクションの追加** を選びます。 
   
    ![](./media/learning-recurrence/frequency-interval.png)
5. **Excel** を検索して **Excel** サービスを選び、**Excel – 複数の行の取得** アクションを選びます。 
   
    ![](./media/learning-recurrence/excel-get-rows.png)
   
    **注**: **行の取得** ではなく、**複数の行の取得** を必ず選択してください。 
6. **ファイル名** を選び、ファイルの場所に移動します。 **テーブル名** を選び、スプレッドシートで目的のテーブルを選びます。 
   
    ![](./media/learning-recurrence/excel-get-file.png)
7. 新しいアクションを追加します。 
   
    ![](./media/learning-recurrence/new-step.png)
8. **MailChimp** サービスを検索し、**MailChimp - メンバーをリストに追加する** アクションを選びます。
   
    ![](./media/learning-recurrence/select-mailchimp.png)
   
    **注:** MailChimp は *Premium* コネクタです。 ご利用の Power Automate ライセンスによっては、このコネクタを使用するために試用版へのサインアップが必要な場合があります。
9. ドロップダウン メニューから **リスト ID** および **状態** フィールドを追加します。
   
   * **リスト ID** – 目的の MailChimp メーリング リストを選びます
   * **状態** – **加入済み** を選びます 
     
     ![](./media/learning-recurrence/mailchimp-id-status.png)
10. **メール アドレス** で、動的コンテンツ機能を使って、**ContactEmail** フィールドを追加します。 
    
     ![](./media/learning-recurrence/mailchimp-address.png)
    
     フローで追加ステップが自動的に作成されるはずです。 フローは、追加アクションが必要なアクションの設定が行われていることを検出します。 フローで新しいメール アドレスが読み取られるたびに、各行の新しいアクションも作成されます。 
    
     ![](./media/learning-recurrence/mailchimp-for-each.png)
11. 動的コンテンツを使って、**名** フィールドと **姓** フィールドを設定します。
    
    * **名** – FirstName
    * **姓** – LastName
      
      ![](./media/learning-recurrence/mailchimp-names.png)

これでこのフローは、1 日に 1 回実行し、Excel テーブルから新しい行を取得してメール アドレスと名前を抽出し、それらを使って MailChimp Contoso のメール リストを設定するようになり、時間とコストを節約できます。 

