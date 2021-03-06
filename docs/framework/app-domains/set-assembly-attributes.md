---
title: アセンブリ属性の設定
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- assembly binding, attributes
- assembly manifest, attributes
ms.assetid: 36a98a81-b5b5-4c19-912a-11f91eff7f4e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6c327aad129f685e44f7b456e4ceef8f99fe12b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712601"
---
# <a name="setting-assembly-attributes"></a>アセンブリ属性の設定
アセンブリの属性は、アセンブリに関する情報を提供する値です。 属性は、次のような情報に分類されます。  
  
-   アセンブリ ID 属性。  
  
-   情報属性。  
  
-   アセンブリ マニフェスト属性。  
  
-   厳密な名前の属性。  
  
## <a name="assembly-identity-attributes"></a>アセンブリ ID 属性  
 アセンブリは、名前、バージョン、およびカルチャの 3 つの属性と、適用される場合は厳密な名前によって識別されます。 これらの属性は、アセンブリの完全な名前を形成し、コード内でアセンブリを参照するときに必要になります。 属性を使用して、アセンブリのバージョンとのカルチャを設定できます。 コンパイラまたは [アセンブリ リンカー (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) は、アセンブリの作成時に、アセンブリ マニフェストを含むファイルに基づいて名前の値を設定します。  
  
 バージョン属性とカルチャ属性について次の表で説明します。  
  
|アセンブリ ID 属性|説明|  
|---------------------------------|-----------------|  
|<xref:System.Reflection.AssemblyCultureAttribute>|アセンブリがサポートするカルチャを示す列挙フィールド。 アセンブリがカルチャに依存しないように指定することもできます。その場合は、アセンブリが既定のカルチャのリソースを格納することを意味します。 **注:** ランタイムは、カルチャ属性が null に設定されていないすべてのアセンブリを、サテライト アセンブリとして扱います。 そのようなアセンブリには、サテライト アセンブリ バインディング規則が適用されます。 詳細については、「 [ランタイムがアセンブリを検索する方法](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)」を参照してください。|  
|<xref:System.Reflection.AssemblyFlagsAttribute>|アセンブリを並列で実行できるかどうかなどのアセンブリ属性を設定する値。|  
|<xref:System.Reflection.AssemblyVersionAttribute>|*major*.*minor*.*build*.*revision* 形式の数値 (たとえば、2.4.0.0)。 共通言語ランタイムは、この値を使用して、厳密な名前付きアセンブリでのバインディング操作を実行します。 **注:**<xref:System.Reflection.AssemblyInformationalVersionAttribute> 属性がアセンブリに適用されない場合、<xref:System.Reflection.AssemblyVersionAttribute> 属性によって指定されたバージョン番号が <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>、<xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType>、および <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> の各プロパティで使用されます。|  
  
 バージョン属性とカルチャ属性をアセンブリに適用する方法を次のコード例で示します。  
  
 [!code-cpp[AssemblyDelaySignAttribute#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#3)]
 [!code-csharp[AssemblyDelaySignAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#3)]
 [!code-vb[AssemblyDelaySignAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#3)]  
  
## <a name="informational-attributes"></a>情報属性  
 情報属性は、追加の会社情報または製品情報をアセンブリに指定する場合に使用できます。 アセンブリに適用できる情報属性について、次の表で説明します。  
  
|情報属性|説明|  
|-----------------------------|-----------------|  
|<xref:System.Reflection.AssemblyCompanyAttribute>|会社名を指定する文字列値。|  
|<xref:System.Reflection.AssemblyCopyrightAttribute>|著作権情報を指定する文字列値。|  
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Win32 ファイル バージョン番号を指定する文字列値。 通常、この属性の既定値はアセンブリ バージョンです。|  
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|完全な製品バージョン番号など、共通言語ランタイムによって使用されないバージョン情報を指定する文字列値。 **注:** この属性をアセンブリに適用した場合は、<xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType> プロパティを使用して、この属性で指定された文字列を実行時に取得できます。 この文字列は、<xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> プロパティと <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> プロパティによって提供されるパスとレジストリ キーにも使用されます。|  
|<xref:System.Reflection.AssemblyProductAttribute>|製品情報を指定する文字列値。|  
|<xref:System.Reflection.AssemblyTrademarkAttribute>|商標情報を指定する文字列値。|  
  
 これらの属性は、アセンブリの [Windows のプロパティ] ページに表示できます。また、独自の Win32 リソース ファイルを指定するために、 **/win32res** コンパイラ オプションを使用してこれらの属性をオーバーライドすることもできます。  
  
## <a name="assembly-manifest-attributes"></a>アセンブリ マニフェスト属性  
 アセンブリ マニフェストの属性を使用すると、タイトル、説明、既定のエイリアス、構成などの情報をアセンブリ マニフェストに指定できます。 アセンブリ マニフェスト属性について、次の表で説明します。  
  
|アセンブリ マニフェスト属性|説明|  
|---------------------------------|-----------------|  
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Retail (製品版) や Debug (デバッグ) など、アセンブリの構成を示す文字列値。 ランタイムはこの値を使用しません。|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|アセンブリの参照に使用する既定のエイリアスを指定する文字列値。 この値は、アセンブリ自体の名前がフレンドリ名ではない場合 (GUID 値の場合など) に、フレンドリ名を指定します。 この値は、完全なアセンブリ名の短い形式としても使用できます。|  
|<xref:System.Reflection.AssemblyDescriptionAttribute>|アセンブリの特性と目的を要約した短い説明を指定する文字列値。|  
|<xref:System.Reflection.AssemblyTitleAttribute>|アセンブリのフレンドリ名を指定する文字列値。 たとえば、comdlg という名前のアセンブリに Microsoft Common Dialog Control というタイトルを付けることができます。|  
  
## <a name="strong-name-attributes"></a>厳密な名前の属性  
 厳密な名前の属性を使用すると、アセンブリに厳密な名前を設定できます。 厳密な名前の属性について、次の表で説明します。  
  
|厳密な名前の属性|説明|  
|----------------------------|-----------------|  
|<xref:System.Reflection.AssemblyDelaySignAttribute>|遅延署名が使用されていることを示すブール値。|  
|<xref:System.Reflection.AssemblyKeyFileAttribute>|この属性のコンストラクターにパラメーターとして渡される公開キー (遅延署名を使用する場合) または公開キーと秘密キーの両方を格納するファイルの名前を示す文字列値。 なお、このファイル名は、ソース ファイルのパスではなく出力ファイルのパスから見た相対パス名 (.exe または .dll) です。|  
|<xref:System.Reflection.AssemblyKeyNameAttribute>|この属性のコンストラクターにパラメーターとして渡されるキー ペアを格納するキー コンテナーを示します。|  
  
 次のコード例では、遅延署名を使用し、公開キー ファイル `myKey.snk`を使用する厳密な名前付きアセンブリを作成する場合に適用する属性を示します。  
  
 [!code-cpp[AssemblyDelaySignAttribute#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#4)]
 [!code-csharp[AssemblyDelaySignAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#4)]
 [!code-vb[AssemblyDelaySignAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#4)]  
  
## <a name="see-also"></a>関連項目
- [アセンブリの作成](../../../docs/framework/app-domains/create-assemblies.md)
- [アセンブリを使用したプログラミング](../../../docs/framework/app-domains/programming-with-assemblies.md)
