---
title: コンストラクター '<name>' はそれ自体を呼び出すことはできません。
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 67933e9365b1aa18063f0ccf3c2146a261e7eafc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276043"
---
# <a name="constructor-name-cannot-call-itself"></a>コンス トラクター '\<名 >' 自体を呼び出すことはできません
A`Sub New`クラスまたは構造体でプロシージャを呼び出します。  
  
 コンス トラクターの目的は、クラスのインスタンスを初期化するために、またはそのが最初に構造を作成します。 異なるパラメーター リストがすべて、クラスまたは構造体によって複数のコンス トラクター、することができます。 コンス トラクターは、独自に加え、その機能を実行する別のコンス トラクターを呼び出す許可されています。 コンス トラクターを呼び出す意味がありませんし、許可されている場合、無限再帰の結果が実際にします。  
  
 **エラー ID:** BC30298  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  呼び出されるコンス トラクターのパラメーター リストを確認します。 コンス トラクターの呼び出しを行うのと異なる場合があります。  
  
2.  別のコンス トラクターを呼び出すしない場合は、削除、`Sub New`完全呼び出します。  
  
## <a name="see-also"></a>関連項目
- [オブジェクトの有効期間:オブジェクトを作成および破棄する方法](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
