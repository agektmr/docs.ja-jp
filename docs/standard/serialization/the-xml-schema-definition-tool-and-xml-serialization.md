---
title: XML スキーマ定義ツールと XML シリアル化
ms.date: 03/30/2017
helpviewer_keywords:
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
ms.openlocfilehash: abd96b7fab18b0fac18a2da791e5da8015d481c9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623808"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a>XML スキーマ定義ツールと XML シリアル化
XML スキーマ定義ツール ([XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)) は、Windows® Software Development Kit (SDK) の一部として、.NET Framework ツールと共にインストールされます。 このツールは、主に次の 2 つの目的を実現するためにデザインされています。  
  
-   特定の XML スキーマ定義言語 (XSD) スキーマに準拠する C# クラス ファイルまたは Visual Basic クラス ファイルの生成。 このツールは、XML スキーマを引数として受け取り、<xref:System.Xml.Serialization.XmlSerializer> を使用したシリアル化時にそのスキーマに準拠している多数のクラスを含むファイルを出力します。 ツールを使用して、特定のスキーマに準拠するクラスを生成する方法については、次を参照してください。[方法。クラスと XML スキーマ ドキュメントを生成する XML スキーマ定義ツールを使用して](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)します。  
  
-   .dll ファイルまたは .exe ファイルからの XML スキーマ ドキュメントの生成。 作成済み、または属性を使用して変更済みの一連のファイルのスキーマを確認するには、このツールに DLL または EXE を引数として渡し、その XML スキーマを生成します。 一連のクラスから XML スキーマ ドキュメントを生成するツールを使用する方法については、次を参照してください。[方法。クラスと XML スキーマ ドキュメントを生成する XML スキーマ定義ツールを使用して](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)します。  
  
 このツールおよびその他のツールの詳細については、「[ツール](../../../docs/framework/tools/index.md)」を参照してください。 ツールのオプションの詳細については、「[XML スキーマ定義ツール (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Data.DataSet>
- [XML シリアル化の概要](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [XML スキーマ定義ツール (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [方法: オブジェクトをシリアル化します。](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [方法: オブジェクトを逆シリアル化します。](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
- [方法: XML スキーマ定義ツールを使用して、クラスと XML スキーマ ドキュメントを生成するには](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)
- [.NET Framework での XML スキーマのバインディング サポート](https://msdn.microsoft.com/library/8f0619dd-f1fc-4895-ae21-6d45d0382cc1)
