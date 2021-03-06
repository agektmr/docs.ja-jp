---
title: 長時間のワークフロー サービスの作成
ms.date: 03/30/2017
ms.assetid: 4c39bd04-5b8a-4562-a343-2c63c2821345
ms.openlocfilehash: b3c5cd8a64f32a199932a40ed2d94b0a545b0dc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585403"
---
# <a name="creating-a-long-running-workflow-service"></a>長時間のワークフロー サービスの作成
ここでは、実行時間の長いワークフロー サービスを作成する方法について説明します。 実行時間の長いワークフロー サービスは、長期間にわたって実行できます。 ワークフローでは、いくつかの追加情報を待つ間アイドル状態になることがあります。 アイドル状態になると、ワークフローは SQL データベースに永続化され、メモリから削除されます。 追加情報が使用可能になると、ワークフロー インスタンスがメモリに読み込み直されて、実行を継続します。  このシナリオでは、非常に簡略化された注文システムを実装します。  クライアントは、最初のメッセージをワークフロー サービスに送信して注文を開始します。 ワークフロー サービスは、注文 ID をクライアントに返します。 この時点で、ワークフロー サービスは、クライアントからの別のメッセージを待機しており、アイドル状態に入って、SQL Server データベースに永続化されます。  クライアントが次のメッセージを送信して項目を注文すると、ワークフロー サービスはメモリに読み込み直されて、注文の処理を終了します。 次のコード例では、項目が注文に追加されたことを示す文字列を返します。 このコード例は、テクノロジの実際の適用を意図するものではなく、実行時間の長いワークフロー サービスを示す簡単な例です。 このトピックでは、Visual Studio 2012 プロジェクトとソリューションの作成方法を知っていると仮定します。

## <a name="prerequisites"></a>必須コンポーネント
 このチュートリアルを使用するには、次のソフトウェアがインストールされている必要があります。

1.  Microsoft SQL Server 2008

2.  Visual Studio 2012

3.  Microsoft [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]

4.  WCF と Visual Studio 2012 に精通し、プロジェクト/ソリューションを作成する方法を理解します。

### <a name="to-setup-the-sql-database"></a>SQL データベースを設定するには

1.  ワークフロー サービス インスタンスが永続化されるようにするには、Microsoft SQL Server をインストールして、永続化ワークフロー インスタンスを保存するようにデータベースを設定する必要があります。 クリックして、Microsoft SQL Management Studio を実行、**開始**ボタンをクリックして**すべてのプログラム**、 **Microsoft SQL Server 2008**、および**Microsoft SQLManagement Studio**します。

2.  をクリックして、 **Connect** SQL Server インスタンスにログオンする ボタン

3.  右クリックして**データベース**クリックし、ツリー ビューで**新しいデータベース.** という新しいデータベースを作成する`SQLPersistenceStore`します。

4.  SQLPersistenceStore データベースの C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en ディレクトリにある SqlWorkflowInstanceStoreSchema.sql スクリプト ファイルを実行して、必要なデータベース スキーマを設定します。

5.  SQLPersistenceStore データベースの C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en ディレクトリにある SqlWorkflowInstanceStoreLogic.sql スクリプト ファイルを実行して、必要なデータベース ロジックを設定します。

### <a name="to-create-the-web-hosted-workflow-service"></a>Web ホスト ワークフロー サービスを作成するには

1.  空の Visual Studio 2012 ソリューションを作成、名前を付けます`OrderProcessing`します。

2.  `OrderService` という新しい WCF ワークフロー サービス アプリケーション プロジェクトをソリューションに追加します。

3.  プロジェクトのプロパティ ダイアログ ボックスで、 **Web**タブ。

    1.  **開始動作**選択**特定のページ**指定`Service1.xamlx`。

         ![ワークフロー サービス プロジェクトの Web プロパティ](../../../../docs/framework/wcf/feature-details/media/startaction.png "StartAction")

    2.  **サーバー**選択**使用ローカル IIS Web サーバー**します。

         ![ローカル Web サーバーの設定](../../../../docs/framework/wcf/feature-details/media/uselocalwebserver.png "UseLocalWebServer")

        > [!WARNING]
        >  この設定を行うには管理者モードでは、Visual Studio 2012 を実行する必要があります。

         次の 2 つの手順で、ワークフロー サービス プロジェクトが IIS でホストされるように設定します。

4.  開く`Service1.xamlx`いない既にを開くし、既存の削除である場合**ReceiveRequest**と**SendResponse**アクティビティ。

5.  選択、**シーケンシャル サービス**アクティビティをクリックして、**変数**リンクし、次の図に示すように変数を追加します。 こうするといくつかの変数が追加され、後でワークフロー サービスで使用されます。

    > [!NOTE]
    >  CorrelationHandle が変数の型のドロップダウン リストにない場合は、選択**型の参照**ドロップダウン リストから。 CorrelationHandle を入力、**型名**ボックスで、リスト ボックスから CorrelationHandle を選択し、をクリックして**OK**します。

     ![変数を追加](../../../../docs/framework/wcf/feature-details/media/addvariables.gif "AddVariables")

6.  ドラッグ アンド ドロップ、 **ReceiveAndSendReply**アクティビティ テンプレートを**シーケンシャル サービス**アクティビティ。 このアクティビティのセットは、クライアントからメッセージを受信して、返信を送信します。

    1.  選択、**受信**アクティビティとセットのプロパティは、次の図で強調表示されます。

         ![Receive アクティビティのプロパティのセット](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties.png "SetReceiveProperties")

         DisplayName プロパティは、デザイナーに表示される Receive アクティビティの名前を設定します。 ServiceContractName プロパティと OperationName プロパティは、Receive アクティビティで実装されるサービス コントラクトおよび操作の名前を指定します。 ワークフロー サービスでのコントラクトの使用方法の詳細については、次を参照してください。[ワークフローを使用してコントラクト](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)します。

    2.  をクリックして、**を定義しています.** のリンクを**ReceiveStartOrder**活動し、次の図に示すようにプロパティを設定します。  注意、**パラメーター**オプション ボタンを選択すると、という名前のパラメーター`p_customerName`にバインドされて、`customerName`変数。 これにより、構成、**受信**アクティビティをいくつかのデータを受信し、そのデータをローカル変数にバインドします。

         ![Receive アクティビティが受信するデータを設定](../../../../docs/framework/wcf/feature-details/media/setreceivecontent.png "SetReceiveContent")

    3.  選択、 **SendReplyToReceive**活動し、次の図に示すように強調表示されているプロパティを設定します。

         ![SendReply アクティビティのプロパティを設定](../../../../docs/framework/wcf/feature-details/media/setreplyproperties.png "SetReplyProperties")

    4.  をクリックして、**を定義しています.** のリンクを**SendReplyToStartOrder**活動し、次の図に示すようにプロパティを設定します。 注意、**パラメーター**ラジオ ボタンが選択されている; という名前のパラメーター`p_orderId`にバインドされて、`orderId`変数。 この設定により、SendReplyToStartOrder アクティビティが型文字列の値を呼び出し元に返すように指定されます。

         ![SendReply アクティビティのコンテンツ データを構成する](../../../../docs/framework/wcf/feature-details/media/setreplycontent.png "SetReplyContent")

    5.  ドラッグ アンド間に、Assign アクティビティをドロップ、**受信**と**SendReply**活動し、次の図に示すようにプロパティを設定。

         ![Assign アクティビティの追加](../../../../docs/framework/wcf/feature-details/media/addassign.png "AddAssign")

         これにより、新しい注文 ID が作成され、orderId 変数に値が配置されます。

    6.  選択、 **ReplyToStartOrder**アクティビティ。 [プロパティ] ウィンドウの省略記号ボタンをクリックします。 **CorrelationInitializers**します。 選択、**初期化子を追加**リンクで、入力`orderIdHandle`初期化子のテキスト ボックスで、関連付けの種類のクエリ関連付け初期化子を選択し、XPATH クエリのドロップダウン ボックスの下の p_orderId を選択します。 これらの設定を次の図に示します。 **[OK]** をクリックします。  これにより、クライアントとワークフロー サービスのこのインスタンス間の相関関係が初期化されます。 この注文 ID を含むメッセージが受信されると、ワークフロー サービスのこのインスタンスにルーティングされます。

         ![関連付け初期化子を追加する](../../../../docs/framework/wcf/feature-details/media/addcorrelationinitializers.png "AddCorrelationInitializers")

7.  ドラッグ アンド ドロップ別**ReceiveAndSendReply**ワークフローの末尾にアクティビティ (外部、**シーケンス**最初を格納している**受信**と**SendReply**アクティビティ)。 これで、クライアントで送信された 2 つ目のメッセージを受信し、それに応答します。

    1.  選択、**シーケンス**、新しく追加したを格納している**受信**と**SendReply**アクティビティをクリックして、**変数**ボタンをクリックします。 次の図で強調表示されている変数を追加します。

         ![新しい変数を追加する](../../../../docs/framework/wcf/feature-details/media/addorderitemidvariable.png "AddOrderItemIdVariable")

    2.  選択、**受信**アクティビティし、次の図に示すようにプロパティを設定します。

         ![Receive アクティビティのプロパティを設定](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties2.png "SetReceiveProperties2")

    3.  をクリックして、**を定義しています.** のリンクを**ReceiveAddItem**アクティビティし、次の図に示すようにパラメーターを追加します。 注文 ID、および注文されている項目の ID の 2 つのパラメーターを受け入れるように、receive アクティビティを構成します。

         ![2 番目のパラメーターは、指定する](../../../../docs/framework/wcf/feature-details/media/addreceive2parameters.png "AddReceive2Parameters")

    4.  をクリックして、 **CorrelateOn**省略記号ボタンをクリックし、入力`orderIdHandle`します。 **XPath クエリ**ドロップダウン矢印をクリックし、選択`p_orderId`します。 これにより、2 つ目の Receive アクティビティに相関関係が設定されます。 相関関係の詳細については、次を参照してください。[相関](../../../../docs/framework/wcf/feature-details/correlation.md)します。

         ![CorrelatesOn プロパティの設定](../../../../docs/framework/wcf/feature-details/media/correlateson.png "CorrelatesOn")

    5.  ドラッグ アンド ドロップ、**場合**アクティビティの直後に、 **ReceiveAddItem**アクティビティ。 このアクティビティは、if ステートメントと同様に動作します。

        1.  設定、**条件**プロパティを `itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`

        2.  ドラッグ アンド ドロップ、**割り当てる**アクティビティを**し**セクションと、 **Else**セクションのプロパティを設定する、**割り当てる**次の図に示すように処理します。

             ![サービス呼び出しの結果を代入](../../../../docs/framework/wcf/feature-details/media/resultassign.png "ResultAssign")

             条件が場合`true`、**し**セクションが実行されます。 条件が場合`false`、 **Else**セクションが実行されます。

        3.  選択、 **SendReplyToReceive**アクティビティと設定、 **DisplayName**プロパティを次の図に示すようにします。

             ![SendReply アクティビティのプロパティを設定](../../../../docs/framework/wcf/feature-details/media/setreply2properties.png "SetReply2Properties")

        4.  をクリックして、**を定義しています.** のリンクを**SetReplyToAddItem**アクティビティの次の図に示すように構成します。 これにより、構成、 **SendReplyToAddItem**で値を返すアクティビティ、`orderResult`変数。

             ![SendReply アクティビティのデータ バインディングの設定](../../../../docs/framework/wcf/feature-details/media/replytoadditemcontent.gif "ReplyToAddItemContent")

8.  Web.config ファイルを開き、次の要素を追加、\<動作 > セクションは、ワークフローの永続化を有効にします。

    ```xml
    <sqlWorkflowInstanceStore connectionString="Data Source=your-machine\SQLExpress;Initial Catalog=SQLPersistenceStore;Integrated Security=True;Asynchronous Processing=True" instanceEncodingOption="None" instanceCompletionAction="DeleteAll" instanceLockedExceptionAction="BasicRetry" hostLockRenewalPeriod="00:00:30" runnableInstancesDetectionPeriod="00:00:02" />
              <workflowIdle timeToUnload="0"/>
    ```

    > [!WARNING]
    >  前のコード スニペットでホストと SQL Server インスタンス名を置換するようにします。

9. ソリューションをビルドします。

### <a name="to-create-a-client-application-to-call-the-workflow-service"></a>クライアント アプリケーションを作成してワークフロー サービスを呼び出すには

1.  `OrderClient` という新しいコンソール アプリケーション プロジェクトをソリューションに追加します。

2.  次のアセンブリへの参照を `OrderClient` プロジェクトに追加します。

    1.  System.ServiceModel.dll

    2.  System.ServiceModel.Activities.dll

3.  サービス参照をワークフロー サービスに追加し、`OrderService` を名前空間として指定します。

4.  クライアント プロジェクトの `Main()` メソッド内に次のコードを追加します。

    ```
    static void Main(string[] args)
    {
       // Send initial message to start the workflow service
       Console.WriteLine("Sending start message");
       StartOrderClient startProxy = new StartOrderClient();
       string orderId = startProxy.StartOrder("Kim Abercrombie");

       // The workflow service is now waiting for the second message to be sent
       Console.WriteLine("Workflow service is idle...");
       Console.WriteLine("Press [ENTER] to send an add item message to reactivate the workflow service...");
       Console.ReadLine();

       // Send the second message
       Console.WriteLine("Sending add item message");
       AddItemClient addProxy = new AddItemClient();
       AddItem item = new AddItem();
       item.p_itemId = "Zune HD";
       item.p_orderId = orderId;

       string orderResult = addProxy.AddItem(item);
       Console.WriteLine("Service returned: " + orderResult);
    }
    ```

5.  ソリューションをビルドし、`OrderClient` アプリケーションを実行します。 クライアントに次のテキストが表示されます。

    ```Output
    Sending start messageWorkflow service is idle...Press [ENTER] to send an add item message to reactivate the workflow service...
    ```

6.  ワークフロー サービスが永続化されたことを確認するに移動して、SQL Server Management Studio を起動、**開始**] メニューの [選択**すべてのプログラム**、 **Microsoft SQL Server 2008**、 **SQL Server Management Studio**します。

    1.  左側のウィンドウで次のように展開して、**データベース**、 **SQLPersistenceStore**、**ビュー**を右クリックし、 **System.Activities.DurableInstancing.Instances**選択**上位 1000 行**します。 **結果**ウィンドウが表示されている少なくとも 1 つのインスタンスを参照してくださいを確認します。 実行中に例外が発生した場合は、前の実行のその他のインスタンスがある可能性があります。 右クリックして既存の行を削除する**System.Activities.DurableInstancing.Instances**を選択して**編集上位 200 行**を**Execute**  ボタン結果ウィンドウで、すべての行を選択して、選択**削除**します。  データベースに表示されているインスタンスが、アプリケーションで作成されたインスタンスであることを確認するには、クライアントを実行する前に、Instances ビューが空であることを確認します。 クライアントが実行されると、クエリ ([上位 1000 行を選択]) を再実行し、新しいインスタンスが追加されていることを確認します。

7.  Enter キーを押して、項目の追加メッセージをワークフロー サービスに送信します。 クライアントに次のテキストが表示されます。

    ```Output
    Sending add item messageService returned: Item added to orderPress any key to continue . . .
    ```

## <a name="see-also"></a>関連項目
- [ワークフロー サービス](../../../../docs/framework/wcf/feature-details/workflow-services.md)
