---
title: '方法: TileBrush を使用してさまざまなタイル パターンを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
ms.openlocfilehash: d6b6d4a20d43478131d3adb7c7d091214b3c5871
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721994"
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a>方法: TileBrush を使用してさまざまなタイル パターンを作成する
この例は、使用する方法を示します、<xref:System.Windows.Media.TileBrush.TileMode%2A>のプロパティを<xref:System.Windows.Media.TileBrush>パターンを作成します。  
  
 <xref:System.Windows.Media.TileBrush.TileMode%2A>プロパティを使用すると、指定する方法のコンテンツを<xref:System.Windows.Media.TileBrush>が繰り返されますが、出力領域を埋めるに並べて表示。 パターンを作成するに設定する、<xref:System.Windows.Media.TileBrush.TileMode%2A>に<xref:System.Windows.Media.TileMode.Tile>、 <xref:System.Windows.Media.TileMode.FlipX>、 <xref:System.Windows.Media.TileMode.FlipY>、または<xref:System.Windows.Media.TileMode.FlipXY>します。 設定する必要があります、<xref:System.Windows.Media.TileBrush.Viewport%2A>の<xref:System.Windows.Media.TileBrush>; 描画している領域よりも小さくなるようにそれ以外の場合、タイルが 1 つだけに関係なく、生成されたこの<xref:System.Windows.Media.TileBrush.TileMode%2A>設定を使用しています。  
  
## <a name="example"></a>例  
 次の例では、5 で作成します<xref:System.Windows.Media.DrawingBrush>オブジェクトはそれぞれ異なる<xref:System.Windows.Media.TileBrush.TileMode%2A>を設定して、それらを 5 つの四角形の描画に使用します。 この例では、<xref:System.Windows.Media.DrawingBrush>クラスを示すために<xref:System.Windows.Media.TileBrush.TileMode%2A>の動作、<xref:System.Windows.Media.TileBrush.TileMode%2A>プロパティのすべての動作と同様、<xref:System.Windows.Media.TileBrush>オブジェクト、つまりの<xref:System.Windows.Media.ImageBrush>、<xref:System.Windows.Media.VisualBrush>と<xref:System.Windows.Media.DrawingBrush>します。  
  
 次の図は、この例で生成される出力を示しています。  
  
 ![出力例を並べて表示する TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")  
TileMode プロパティを使用して作成されたタイル パターン  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a>関連項目
- [TileBrush のタイル サイズを設定する](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)
- [イメージ、描画、およびビジュアルによる塗りつぶし](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
