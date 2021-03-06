---
title: = 演算子 - C# リファレンス
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 2c999e76a9238e6401e89af0faa81967b13a3995
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244389"
---
# <a name="-operator-c-reference"></a>= 演算子 (C# リファレンス)

代入演算子 `=` は、右辺オペランドの値を、左辺オペランドに指定された変数、[プロパティ](../../programming-guide/classes-and-structs/properties.md)、または[インデクサー](../../../csharp/programming-guide/indexers/index.md)要素に割り当てます。 代入式の結果は、左辺のオペランドに割り当てられる値です。 右辺のオペランドの型は、左辺のオペランドの型と同じであるか、暗黙に変換できる必要があります。

代入演算子は右結合です。つまり、次の形式の式があるとします。

```csharp
a = b = c
```

これが次のように評価されます。

```csharp
a = (b = c)
```

次の例では、ローカル変数、プロパティ、およびインデクサー要素に値を割り当てるための、代入演算子の使用方法を示しています。

[!code-csharp-interactive[assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#Assignments)]

## <a name="ref-assignment-operator"></a>ref 代入演算子

C# 7.3 以降では、ref 代入演算子 `= ref` を使用して、[ref ローカル](../keywords/ref.md#ref-locals)変数または [ref 読み取り専用ローカル](../keywords/ref.md#ref-readonly-locals)変数を割り当てることができます。 次の例は、ref 代入演算子の使用方法を示しています。

[!code-csharp[ref assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#RefAssignment)]

ref 代入演算子の場合、左辺オペランドの型と右辺オペランドの型が同じであることが必要です。

詳しくは、[機能提案メモ](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.3/ref-local-reassignment.md)をご覧ください。

## <a name="operator-overloadability"></a>演算子のオーバーロード可/不可

ユーザー定義型は、代入演算子をオーバー ロードできません。 ただし、ユーザー定義型は、別の型への暗黙的な変換を定義できます。 この方法により、ユーザー定義型の値を、別の型の変数、プロパティ、またはインデクサー要素に割り当てることができます。 詳しくは、[implicit](../keywords/implicit.md) キーワードに関する記事をご覧ください。

## <a name="c-language-specification"></a>C# 言語仕様

詳細については、「[C# 言語仕様](../language-specification/index.md)」の[単純な代入](~/_csharplang/spec/expressions.md#simple-assignment)に関するセクションを参照してください。

## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
- [C# プログラミングガイド](../../programming-guide/index.md)
- [C# 演算子](index.md)
- [ref キーワード](../keywords/ref.md)
