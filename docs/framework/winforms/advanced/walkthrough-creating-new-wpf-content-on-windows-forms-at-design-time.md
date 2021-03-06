---
title: 'チュートリアル: デザイン時に Windows フォームで新しい WPF コンテンツを作成します。'
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: 9414eb8edc839b109aafa0c98fa3ed74a34a7d62
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500500"
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a>チュートリアル: デザイン時に Windows フォームで新しい WPF コンテンツを作成します。

このトピックでは、Windows フォーム ベースのアプリケーションで使用する Windows Presentation Foundation (WPF) コントロールを作成する方法を示します。

このチュートリアルでは次のタスクを実行します。

- プロジェクトを作成する。

- 新しい WPF コントロールを作成する。

- 新しい WPF コントロールを Windows フォームに追加する。 WPF コントロールは <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを実行するには、次のコンポーネントが必要です。

- Visual Studio 2017

## <a name="creating-the-project"></a>プロジェクトの作成

まず、Windows フォーム プロジェクトを作成します。 Visual Studio を開き、新しい作成**Windows フォーム アプリ (.NET Framework)** Visual Basic または Visual c# のという名前でプロジェクト`HostingWpf`します。

> [!NOTE]
> WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。

## <a name="creating-a-new-wpf-control"></a>新しい WPF コントロールの作成

新しい WPF コントロールを作成し、プロジェクトに追加するのは、プロジェクトへの他の項目の追加と同じくらい簡単です。 Windows フォーム デザイナーがという名前のコントロールの特定の種類を連携*複合コントロール*、または*ユーザー コントロール*します。 WPF ユーザー コントロールの詳細については、「<xref:System.Windows.Controls.UserControl>」を参照してください。

> [!NOTE]
> WPF の <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> の種類は、同じ <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType> という名前を持つ、Windows フォームで提供されるユーザー コントロールの種類とは区別されます。

### <a name="to-create-a-new-wpf-control"></a>新しい WPF コントロールを作成するには

1. **ソリューション エクスプ ローラー**、新しい追加**WPF ユーザー コントロール ライブラリ (.NET Framework)** プロジェクトがソリューションにします。 このコントロール ライブラリの既定の名前である `WpfControlLibrary1` を使用します。 既定のコントロールの名前は `UserControl1.xaml` です。

     新しいコントロールを追加すると、次の効果があります。

    - ファイル UserControl1.xaml が追加されます。

    - ファイル UserControl1.xaml.cs または UserControl1.xaml.vb のいずれかが追加されます。 このファイルには、イベント ハンドラーとその他の実装のための分離コードが含まれています。

    - WPF アセンブリへの参照が追加されます。

    - ファイル UserControl1.xaml が [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] で開きます。

2. デザイン ビューで `UserControl1` が選択されていることを確認します。 詳細については、「[方法 :選択し、デザイン サーフェイス上の要素の移動](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474)します。

3. **プロパティ**ウィンドウで、設定の値、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティ**200**します。

4. **ツールボックス**、ドラッグ、<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>コントロールをデザイン画面。

5. **プロパティ**ウィンドウで、設定の値、<xref:System.Windows.Controls.TextBox.Text%2A>プロパティを**ホストするコンテンツの**します。

    > [!NOTE]
    > 一般的には、もう少し高度な WPF コンテンツをホストしてください。 ここでは、説明する目的でのみ <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> コントロールを使用しています。

6. プロジェクトをビルドします。

## <a name="adding-a-wpf-control-to-a-windows-form"></a>WPF コントロールを Windows フォームに追加する

新しい WPF コントロールは、フォームで使用可能な状態です。 Windows フォームを使用して、 <xref:System.Windows.Forms.Integration.ElementHost> WPF コンテンツをホストするコントロール。

### <a name="to-add-a-wpf-control-to-a-windows-form"></a>WPF コントロールを Windows フォームに追加するには

1. Windows フォーム デザイナーで `Form1` を開きます。

2. **ツールボックス**、というラベルのタブを見つける**WPFUserControlLibrary WPF ユーザー コントロール**します。

3. `UserControl1` のインスタンスをフォームにドラッグします。

    - WPF コントロールをホストするためのフォームの上に、<xref:System.Windows.Forms.Integration.ElementHost> コントロールが自動的に作成されます。

    - <xref:System.Windows.Forms.Integration.ElementHost>コントロールの名前は`elementHost1`し、**プロパティ**ウィンドウに、表示できるその<xref:System.Windows.Forms.Integration.ElementHost.Child%2A>プロパティに設定されて**UserControl1**。

    - WPF アセンブリへの参照がプロジェクトに追加されます。

    - `elementHost1` コントロールに、使用可能なホスティング オプションを示すスマート タグ パネルがあります。

4. **ElementHost タスク**スマート タグ パネルで、**親コンテナーにドッキング**します。

5. **F5** キーを押してアプリケーションをビルドし、実行します。

## <a name="next-steps"></a>次の手順

Windows フォームと WPF は異なるテクノロジですが、密接に相互運用するよう設計されています。 高度な外観とをアプリケーションでの動作を提供するには、次を試してください。

- WPF ページで Windows フォーム コントロールをホストします。 詳細については、「[チュートリアル:WPF でのフォーム コントロールのホストを Windows](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)します。

- WPF コンテンツに Windows フォームの視覚スタイルを適用します。 詳細については、「[方法 :ハイブリッド アプリケーションで視覚スタイルを有効にする](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)します。

- WPF コンテンツのスタイルを変更します。 詳細については、「[チュートリアル:WPF コンテンツのスタイル設定](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)します。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [移行と相互運用性](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
- [WPF コントロールの使用](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)
- [Visual Studio で XAML をデザインする](/visualstudio/designers/designing-xaml-in-visual-studio)
