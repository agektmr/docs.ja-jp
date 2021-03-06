---
title: '方法: プロシージャ (Visual Basic) から値を返す'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 38b0673f5725077eec9253021eec4216e66504a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54615250"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>方法: プロシージャ (Visual Basic) から値を返す
A`Function`プロシージャに値を返す呼び出し元のコードを実行するか、`Return`ステートメントまたはを戻したり、`Exit Function`または`End Function`ステートメント。  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Return ステートメントを使用して値を返す  
  
1.  配置、`Return`でプロシージャのタスクが完了した後の時点でのステートメント。  
  
2.  に従って、`Return`呼び出し元のコードを取得するキーワード、値を生成する式をします。  
  
3.  同じプロシージャ内に複数の `Return` ステートメントを含めることができます。  
  
     次`Function`プロシージャが最長の辺の三角形の斜辺を計算し、呼び出し元のコードに返します。  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     次の例では、一般的な呼び出しを`hypotenuse`、返される値を格納します。  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Exit 関数または終了関数を使用して値を返す  
  
1.  内の少なくとも 1 か所で、`Function`プロシージャ、プロシージャ名に値を割り当てます。  
  
2.  実行すると、`Exit Function`または`End Function`ステートメントでは、Visual Basic は、プロシージャの名前を最も最近割り当てられた値を返します。  
  
3.  同じプロシージャ内に複数の `Exit Function` ステートメントを含めることができ、さらに同じプロシージャ内に `Return` ステートメントと `Exit Function` ステートメントを混在させることができます。  
  
4.  1 つのみできます`End Function`内のステートメントを`Function`プロシージャ。  
  
     詳細と例を参照してください「戻り値」[関数ステートメント](../../../../visual-basic/language-reference/statements/function-statement.md)します。  
  
## <a name="see-also"></a>関連項目
- [プロシージャ](./index.md)
- [Sub プロシージャ](./sub-procedures.md)
- [Property プロシージャ](./property-procedures.md)
- [演算子プロシージャ](./operator-procedures.md)
- [プロシージャのパラメーターと引数](./procedure-parameters-and-arguments.md)
- [Function ステートメント](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Return ステートメント](../../../../visual-basic/language-reference/statements/return-statement.md)
- [方法: 値を返すプロシージャを作成します。](./how-to-create-a-procedure-that-returns-a-value.md)
- [方法: 値を返すプロシージャを呼び出す](./how-to-call-a-procedure-that-returns-a-value.md)
