---
title: UI オートメーションを使用したコントロールの呼び出し
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking controls
- UI Automation, invoking controls
- controls, invoking
ms.assetid: 5ee2de3f-256c-43ec-b64c-62ace91f9983
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: b4ee4b4929d5aa80ccfb91d07031b4ab195d311e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654777"
---
# <a name="invoke-a-control-using-ui-automation"></a>UI オートメーションを使用したコントロールの呼び出し
> [!NOTE]
>  このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。 に関する最新情報については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を参照してください[Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)します。  
  
 このトピックでは、次のタスクを実行する方法について示します。  
  
-   ターゲット アプリケーションの [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ツリーのコントロール ビューを調べて、特定のプロパティ条件に一致するコントロールを検索する。  
  
-   各コントロールに対して <xref:System.Windows.Automation.AutomationElement> を作成する。  
  
-   <xref:System.Windows.Automation.InvokePattern> コントロール パターンをサポートする [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 要素から <xref:System.Windows.Automation.InvokePattern> オブジェクトを取得する。  
  
-   <xref:System.Windows.Automation.InvokePattern.Invoke%2A> を使用して、クライアントのイベント ハンドラーからコントロールを呼び出す。  
  
## <a name="example"></a>例  
 この例では、 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> クラスの <xref:System.Windows.Automation.AutomationElement> メソッドを使用して <xref:System.Windows.Automation.InvokePattern> オブジェクトを生成し、 <xref:System.Windows.Automation.InvokePattern.Invoke%2A> メソッドを使用してコントロールを呼び出します。  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a>関連項目
- [InvokePattern および ExpandCollapsePattern メニュー項目のサンプル](https://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)
