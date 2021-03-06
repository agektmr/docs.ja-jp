---
title: 既定プロパティ '<propertyname1>' は、'<propertyname2>' の既定プロパティ '<classname>' と競合しているため、'Shadows' と宣言できません。
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: bc75b01532ffb112622d7f9bc837490c627883b3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270392"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>既定のプロパティ '\<propertyname1 >' 既定のプロパティと競合'\<propertyname2 >' で '\<classname >'、'Shadows' を宣言する必要があります
プロパティは、基底クラスで定義されたプロパティと同じ名前で宣言します。 このような状況では、このクラスのプロパティは、基底クラスのプロパティをシャドウする必要があります。  
  
 このメッセージは警告です。 `Shadows` は、既定で指定されていると見なされます。 警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。  
  
 **エラー ID:** BC40007  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   追加、`Shadows`プロパティの名前が宣言されているキーワードを宣言、または変更します。  
  
## <a name="see-also"></a>関連項目
- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Visual Basic におけるシャドウ](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
