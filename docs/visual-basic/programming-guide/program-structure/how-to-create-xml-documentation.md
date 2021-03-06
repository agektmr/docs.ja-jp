---
title: '方法: Visual Basic での XML ドキュメントを作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: d67724aad6cd3e7af30531328d85e89937390dd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551372"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>方法: Visual Basic での XML ドキュメントを作成します。
この例では、コードに XML ドキュメントのコメントを追加する方法を示します。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>型またはメンバーの XML ドキュメントを作成するには  
  
1.  **コード エディター**ドキュメントを作成する型またはメンバー上の行にカーソルを置きます。  
  
2.  型`'''`(3 つ単一引用符は含みません)。  
  
     型またはメンバーの XML スケルトンが追加された、**コード エディター**します。  
  
3.  適切なタグの間のわかりやすい情報を追加します。  
  
    > [!NOTE]
    >  それぞれの行が始まる必要があります、XML ドキュメントのブロック内で行を追加する場合`'''`します。  
  
4.  新しい XML ドキュメント コメントを含む型またはメンバーを使用する追加のコードを追加します。  
  
     テキストを表示する IntelliSense、\<概要 > 型またはメンバーのタグ。  
  
5.  ドキュメントのコメントを含む XML ファイルを生成するコードをコンパイルします。 詳細については、「[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目
- [XML の使用によるコードのドキュメントの作成](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [XML のコメント用タグ](../../../visual-basic/language-reference/xmldoc/index.md)
- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
