---
title: '方法: Windows フォーム DataGridView 行にバインドされたオブジェクトへのアクセス'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object binding [Windows Forms], accessing bound objects
- data grids [Windows Forms], accessing bound objects
- DataGridView control [Windows Forms], accessing objects bound to rows
ms.assetid: 0e05748f-4403-4eb8-8b2f-b098108181b5
ms.openlocfilehash: 2a4c5cc052ce8c44d36c43daf11d91c798dd741f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54679449"
---
# <a name="how-to-access-objects-bound-to-windows-forms-datagridview-rows"></a>方法: Windows フォーム DataGridView 行にバインドされたオブジェクトへのアクセス
場合によっては、ビジネス オブジェクトのコレクションに格納されている情報のテーブルを表示すると便利です。 <xref:System.Windows.Forms.DataGridView> コントロールをそのようなコレクションにバインドすると、<xref:System.ComponentModel.BrowsableAttribute> によって参照不可にマークされない限り、各パブリック プロパティが独自の列に表示されます。 たとえば、`Customer` オブジェクトのコレクションに**名前**や**アドレス**などの列が含まれるようになります。  
  
 アクセスする追加情報とコードがこれらのオブジェクトに含まれている場合は、行オブジェクトを介してアクセスできます。 次のコード例では、ユーザーが複数の行を選択し、ボタンをクリックすると、対応する顧客のそれぞれに請求書を送信できます。  
  
### <a name="to-access-row-bound-objects"></a>行にバインドされたオブジェクトにアクセスするには  
  
-   <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType> プロパティを使用します。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#10)]  
  
## <a name="example"></a>例  
 完全なコード例には、単純な `Customer` 実装が含まれ、<xref:System.Windows.Forms.DataGridView> を `Customer` オブジェクトがいくつか含まれる <xref:System.Collections.ArrayList> にバインドします。 <xref:System.Windows.Forms.Button?displayProperty=nameWithType> の <xref:System.Windows.Forms.Control.Click> イベント ハンドラーは、行を介して `Customer` オブジェクトにアクセスする必要があります。これは、<xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> イベント ハンドラーの外部で、顧客のコレクションにアクセスできないためです。  
  
 [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#00)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
-   System アセンブリおよび System.Windows.Forms アセンブリへの参照。  
  
 コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。 新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。  参照してください[方法。Visual Studio を使用して、完全な Windows フォームのコードの例をコンパイルして](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))します。  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>
- [Windows フォーム DataGridView コントロールでのデータの表示](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [方法: オブジェクトを Windows フォーム DataGridView コントロールにバインドします。](../../../../docs/framework/winforms/controls/how-to-bind-objects-to-windows-forms-datagridview-controls.md)
