---
title: ComboBox のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- ComboBox [WPF], styles and templates
- states [WPF], ComboBox
- ControlTemplate [WPF], ComboBox
- styles [WPF], ComboBox
- templates [WPF], ComboBox
- parts [WPF], ComboBox
ms.assetid: b0662fa1-16d7-4320-b26b-c1804e565a44
ms.openlocfilehash: 5cca162137b603f36dffb044d5954c3947964cf9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712851"
---
# <a name="combobox-styles-and-templates"></a>ComboBox のスタイルとテンプレート
このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.ComboBox>コントロール。 既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。 詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)」を参照してください。  
  
## <a name="combobox-parts"></a>ComboBox パーツ  
 次の表に、名前付きパーツ、<xref:System.Windows.Controls.ComboBox>コントロール。  
  
|パーツ|型|説明|  
|-|-|-|  
|PART_EditableTextBox|<xref:System.Windows.Controls.TextBox>|テキストを含む、<xref:System.Windows.Controls.ComboBox>します。|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|コンボ ボックス内の項目を含むドロップダウン リスト。|  
  
 作成するときに、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.ComboBox>、テンプレートが含まれます、<xref:System.Windows.Controls.ItemsPresenter>内、 <xref:System.Windows.Controls.ScrollViewer>。 (、<xref:System.Windows.Controls.ItemsPresenter>内の各項目が表示されます、 <xref:System.Windows.Controls.ComboBox>、<xref:System.Windows.Controls.ScrollViewer>コントロール内でスクロールできます)。  場合、<xref:System.Windows.Controls.ItemsPresenter>の直接の子ではない、<xref:System.Windows.Controls.ScrollViewer>を付ける必要があります、<xref:System.Windows.Controls.ItemsPresenter>名、`ItemsPresenter`します。  
  
## <a name="combobox-states"></a>コンボ ボックスの状態  
 次の表に、状態、<xref:System.Windows.Controls.ComboBox>コントロール。  
  
|VisualState 名|VisualStateGroup 名|説明|  
|-|-|-|  
|標準|CommonStates|既定の状態です。|  
|無効|CommonStates|コントロールが無効になっています。|  
|MouseOver|CommonStates|マウス ポインターが上、<xref:System.Windows.Controls.ComboBox>コントロール。|  
|フォーカスされている|FocusStates|コントロールにフォーカスがあります。|  
|フォーカスされていない|FocusStates|コントロールにフォーカスがありません。|  
|FocusedDropDown|FocusStates|ドロップダウン リスト、<xref:System.Windows.Controls.ComboBox>にフォーカスがあります。|  
|有効|ValidationStates|コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。|  
|編集可能です|EditStates|<xref:System.Windows.Controls.ComboBox.IsEditable%2A> プロパティが `true` です。|  
|編集不可|EditStates|<xref:System.Windows.Controls.ComboBox.IsEditable%2A> プロパティが `false` です。|  
  
## <a name="comboboxitem-parts"></a>や ComboBoxItem パーツ  
 <xref:System.Windows.Controls.ComboBoxItem>コントロールには、名前付きパーツはありません。  
  
## <a name="comboboxitem-states"></a>や ComboBoxItem 状態  
 次の表に、状態、<xref:System.Windows.Controls.ComboBoxItem>コントロール。  
  
|VisualState 名|VisualStateGroup 名|説明|  
|-|-|-|  
|標準|CommonStates|既定の状態です。|  
|無効|CommonStates|コントロールが無効になっています。|  
|MouseOver|CommonStates|マウス ポインターが上、<xref:System.Windows.Controls.ComboBox>コントロール。|  
|フォーカスされている|FocusStates|コントロールにフォーカスがあります。|  
|フォーカスされていない|FocusStates|コントロールにフォーカスがありません。|  
|選択済み|SelectionStates|項目が現在選択されています。|  
|未選択|SelectionStates|この項目は選択されていません。|  
|SelectedUnfocused|SelectionStates|この項目は選択されていますが、フォーカスがありません。|  
|有効|ValidationStates|コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。|  
  
## <a name="combobox-controltemplate-example"></a>コンボ ボックス ControlTemplate の例  
 次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.ComboBox>コントロールと関連する型。  
  
 [!code-xaml[ControlTemplateExamples#ComboBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#combobox)]  
  
 前の例では、次のリソースの 1 つ以上を使用します。  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [コントロールのスタイルとテンプレート](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [コントロールのカスタマイズ](../../../../docs/framework/wpf/controls/control-customization.md)
- [スタイルとテンプレート](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
