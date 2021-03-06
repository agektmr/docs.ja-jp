---
title: '&lt;&lt; 演算子 - C# リファレンス'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: 79a48d88e2c83b5ad78804367ee3c07f78622c08
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333526"
---
# <a name="ltlt-operator-c-reference"></a>&lt;&lt; 演算子 (C# リファレンス)

左シフト演算子 (`<<`) は、最初のオペランドを 2 番目のオペランドで指定されたビット数だけ左にシフトします。 2 番目のオペランドの型は、[int](../keywords/int.md) または事前に定義された `int` への暗黙的な数値変換を持つ型にする必要があります。

## <a name="remarks"></a>コメント

最初のオペランドが [int](../keywords/int.md) または [uint](../keywords/uint.md) (32 ビット値) である場合、シフト数は、2 番目のオペランドの下位 5 ビットで指定されます。 つまり、実際のシフト数は、0 - 31 ビットです。

最初のオペランドが [long](../keywords/long.md) または [ulong](../keywords/ulong.md) (64 ビット値) である場合、シフト数は、2 番目のオペランドの下位 6 ビットで指定されます。 つまり、実際のシフト数は、0 - 63 ビットです。

シフトが破棄された後に最初のオペランドの型の範囲内に含まれないすべての上位ビットおよび下位の空のビットはゼロで埋められます。 シフト演算ではオーバーフローは発生しません。

ユーザー定義型は、`<<` 演算子をオーバーロードすることができます (「[operator](../keywords/operator.md)」を参照)。最初のオペランドの型は、ユーザー定義型である必要があり、2 番目のオペランドの型は `int` でなければなりません。 二項演算子をオーバーロードすると、対応する代入演算子がある場合、これも暗黙的にオーバーロードされます。

## <a name="example"></a>例

[!code-csharp[csRefOperators#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#14)]

## <a name="comments"></a>コメント

1 と 33 は同じ下位 5 ビットを持つため、`i<<1` と `i<<33` は、同じ結果になります。

## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
- [C# プログラミングガイド](../../programming-guide/index.md)
- [C# 演算子](index.md)
