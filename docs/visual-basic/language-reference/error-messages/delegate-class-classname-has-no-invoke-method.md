---
title: Delegate クラス '<classname>' には Invoke メソッドが含まれていないため、この型の式をメソッド呼び出しのターゲットに設定することはできません。
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 8339d038f845b8568f31f3068a98ccccf580aeae
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286651"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>Delegate クラス\<classname >' この型の式はメソッド呼び出しのターゲットにすることはできませんので Invoke メソッドがありません
呼び出し`Invoke`デリゲートを通じてが失敗したため、`Invoke`デリゲート クラスは実装されていません。  
  
 **エラー ID:** BC30220  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  デリゲート クラスのインスタンスが作成されたことを確認、`Dim`ステートメントと、プロシージャがデリゲートのインスタンスに割り当てられたこと、`AddressOf`演算子。  
  
2.  デリゲート クラスを実装するコードを見つけて、それを実装することを確認、`Invoke`プロシージャ。  
  
## <a name="see-also"></a>関連項目
- [デリゲート](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Delegate ステートメント](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [AddressOf 演算子](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Dim ステートメント](../../../visual-basic/language-reference/statements/dim-statement.md)
