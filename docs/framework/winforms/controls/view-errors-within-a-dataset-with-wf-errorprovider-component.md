---
title: '方法: Windows フォーム ErrorProvider コンポーネントで DataSet 内のエラーの表示'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 48f333fbae816748813b370bccc559cea2714fa5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694049"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a>方法: Windows フォーム ErrorProvider コンポーネントで DataSet 内のエラーの表示
Windows フォームを使用する<xref:System.Windows.Forms.ErrorProvider>データセットまたは他のデータ ソース内の列のエラーを表示するコンポーネント。 <xref:System.Windows.Forms.ErrorProvider>フォームのデータのエラーを表示するコンポーネントにすることはありません、コントロールに直接関連付けられています。 データ ソースにバインドされていると、同じデータ ソースにバインドされている任意のコントロールの横にエラー アイコンを表示できます。  
  
> [!NOTE]
>  エラー プロバイダーの変更した場合<xref:System.Windows.Forms.ErrorProvider.DataSource%2A>と<xref:System.Windows.Forms.ErrorProvider.DataMember%2A>実行時にプロパティを使用する必要がある、<xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A>競合を回避する方法。  
  
### <a name="to-display-data-errors"></a>データ エラーを表示するには  
  
1.  コンポーネントをデータ テーブル内の特定の列にバインドします。  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
    ```  
  
2.  設定、<xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>プロパティをフォームにします。  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3.  列のエラーを含む行を現在のレコードの位置を設定します。  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a>関連項目
- [ErrorProvider コンポーネントの概要](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)
- [方法: Windows フォーム ErrorProvider コンポーネントを使用してフォーム検証のエラー アイコンを表示します。](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
