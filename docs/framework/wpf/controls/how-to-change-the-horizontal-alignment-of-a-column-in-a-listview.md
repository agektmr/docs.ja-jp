---
title: '方法: ListView の列の水平方向の配置を変更する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: 07d5fd0830f98032e76b963cb32b35fd18b50475
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605226"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>方法: ListView の列の水平方向の配置を変更する
既定で各列のコンテンツを<xref:System.Windows.Controls.ListViewItem>は左揃えにします。 提供することで各列の配置を変更することができます、<xref:System.Windows.DataTemplate>と設定、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>プロパティ内の要素を<xref:System.Windows.DataTemplate>します。 このトピックでは、方法、<xref:System.Windows.Controls.ListView>既定で 1 つの列の配置を変更する方法とそのコンテンツを配置、<xref:System.Windows.Controls.ListView>します。  
  
## <a name="example"></a>例  
 次の例では、データ、`Title`と`ISBN`列を左揃え。  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 配置を変更する、`ISBN`列、ことを指定する必要があります、<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>の各プロパティ<xref:System.Windows.Controls.ListViewItem>は<xref:System.Windows.HorizontalAlignment.Stretch>いるため、各要素<xref:System.Windows.Controls.ListViewItem>にまたがるまたは各列の幅全体に合わせて配置します。 <xref:System.Windows.Controls.ListView>がバインドされているデータ ソースには、スタイル設定を作成する必要があります、<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>します。 次に、使用する必要があります、<xref:System.Windows.DataTemplate>を使用する代わりにコンテンツを表示する、<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>プロパティ。 表示する、`ISBN`テンプレートごとの<xref:System.Windows.DataTemplate>だけ含めることができます、<xref:System.Windows.Controls.TextBlock>を持つその<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>プロパティに設定<xref:System.Windows.HorizontalAlignment.Right>します。  
  
 次の例は、スタイルを定義および<xref:System.Windows.DataTemplate>ために必要な`ISBN`右揃えの列と変更、<xref:System.Windows.Controls.GridViewColumn>参照に、 <xref:System.Windows.DataTemplate>。  
  
 [!code-xaml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>関連項目
- [データ バインディングの概要](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [データ テンプレートの概要](../../../../docs/framework/wpf/data/data-templating-overview.md)
- [XMLDataProvider と XPath クエリを使用して XML データにバインドする](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [ListView の概要](../../../../docs/framework/wpf/controls/listview-overview.md)
