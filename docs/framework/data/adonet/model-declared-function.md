---
title: モデル宣言関数
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: 5db7d49fd4b839cef47db8086b4ef39ce4dc6aea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725143"
---
# <a name="model-declared-function"></a>モデル宣言関数
A*モデル宣言関数*が概念モデルで宣言されていますが、その概念モデルで定義されていない関数です。 この関数は、ホスト環境またはストレージ環境で定義します。 たとえば、モデル宣言関数は、データベースに定義された関数にマップされ、これによって概念モデルにおけるサーバー側の機能が公開される場合があります。  
  
 モデル宣言関数の宣言には、次の情報が含まれます。  
  
-   関数の名前。 (必須)  
  
-   戻り値の型。 (オプション)。  
  
    > [!NOTE]
    >  戻り値が指定されていない場合、戻り値の型は void になります。  
  
-   パラメーター名と型を含むパラメーター情報。 (オプション)。  
  
## <a name="example"></a>例  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)概念スキーマ定義言語と呼ばれるドメイン固有言語 (DSL) を使用して ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 概念モデルを定義します。 モデル宣言関数の 1 つの実装は、CSDL で、[関数インポート](https://msdn.microsoft.com/library/125704ae-56c7-4233-80b7-389a10f3a65d)します。 次の CSDL は、関数インポート定義を含むエンティティ コンテナーを定義しています。 戻り値の型が指定されていないため、関数の戻り値の型は void になります。  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a>関連項目
- [Entity Data Model キーの概念](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
