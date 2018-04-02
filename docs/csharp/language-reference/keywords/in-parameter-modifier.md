---
title: in パラメーター修飾子 (C# リファレンス)
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9b8b21e2bdc95829c831ee71f24b47986321b7d0
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="dfaeb-102">in パラメーター修飾子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="dfaeb-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="dfaeb-103">`in` キーワードによって、参照により引数が渡されます。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="dfaeb-104">[ref](ref.md) や [out](out-parameter-modifier.md) キーワードと似ています。ただし、`in` 引数を呼び出されたメソッドで変更することはできませんが、`ref` 引数は変更できます。また、`out` 引数は呼び出し元が変更する必要があり、これらの変更は呼び出し元コンテキストで監視可能です。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-104">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method, whereas `ref` arguments may be modified,  `out` arguments must be modified by the caller, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="dfaeb-105">前の例は、`in` 修飾子が呼び出しサイトでは不要であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-105">The preceding example demonstrates that the `in` modifier is unnecessary at the call site.</span></span> <span data-ttu-id="dfaeb-106">これはメソッド宣言でのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-106">It is only required in the method declaration.</span></span>

> [!NOTE] 
> <span data-ttu-id="dfaeb-107">`foreach` ステートメントの一部、または LINQ クエリの `join` 句の一部として、型パラメーターが反変であることを示すために `in` キーワードをジェネリック型パラメーターで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-107">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="dfaeb-108">これらのコンテキストでの `in` キーワードの使用の詳細については、これらすべての使用に関するリンクを提供する「[in](in.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-108">For more information on the use of the `in` keyword in these contexts, see [in](in.md) which provides links to all those uses.</span></span>
  
 <span data-ttu-id="dfaeb-109">`in` 引数として渡される変数は、メソッド呼び出しで渡される前に初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-109">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="dfaeb-110">ただし、呼び出されたメソッドでは値の割り当てや、引数の変更を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-110">However, the called method may not assign a value or modify the argument.</span></span>  
  
 <span data-ttu-id="dfaeb-111">`in`、`ref`、`out`キーワードは実行時の動作が異なりますが、コンパイル時にメソッド シグネチャの一部とは見なされません。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-111">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="dfaeb-112">したがって、唯一の違いが、1 つのメソッドは `ref` または `in` 引数を受け取り、もう一方のメソッドは `out` 引数を受け取ることである場合、メソッドはオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-112">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="dfaeb-113">たとえば、次のコードはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-113">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="dfaeb-114">`in` の有無に基づくオーバーロードは可能ですが、コンパイラの警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-114">Overloading based on the presence of `in` is allowed, but generates a compiler warning:</span></span>  
  
```csharp
class InOverloads
{
    // Discouraged. Calling SampleMethod(value) is ambiguous.
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

<span data-ttu-id="dfaeb-115">呼び出し元メソッドでは値を変更できないため、プロパティまたは定数を `in` パラメーターとして渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-115">Properties or constants may be passed as `in` parameters, because the calling method may not modify their values.</span></span>
  
<span data-ttu-id="dfaeb-116">次の種類のメソッドには、`in`、`ref`、`out` キーワードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-116">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="dfaeb-117">[async](../../../csharp/language-reference/keywords/async.md) 修飾子を使用して定義した Async メソッド。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-117">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
- <span data-ttu-id="dfaeb-118">[yield return](../../../csharp/language-reference/keywords/yield.md) または `yield break` ステートメントを含む Iterator メソッド。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-118">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

<span data-ttu-id="dfaeb-119">通常は、`in` 引数を宣言して、値で引数を渡すために必要なコピー操作を回避します。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-119">You typically declare `in` arguments to avoid the copy operations necessary for passing arguments by value.</span></span> <span data-ttu-id="dfaeb-120">これは、引数が構造体などの値の型で、参照渡しよりもコピー操作の方が負荷がかかる場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-120">This is most useful when arguments are value types such as structures where copy operations are more expensive than passing by reference.</span></span>

> [!WARNING]
>  <span data-ttu-id="dfaeb-121">`in` パラメーターは誤って使用すると、さらに負荷がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-121">`in` parameters can be even more expensive if misused.</span></span> <span data-ttu-id="dfaeb-122">コンパイラでは、メンバー メソッドが、構造体の状態を変更するかどうかを認識しません。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-122">The compiler may not know if member methods modify the state of the struct.</span></span> <span data-ttu-id="dfaeb-123">オブジェクトが変更されないことがコンパイラで確認できない場合は、常に防御のためにコンパイラがコピーを作成し、そのコピーを利用してメンバー参照を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-123">Whenever the compiler cannot ensure that the object is not modified, it defensively creates a copy and calls member references using that copy.</span></span> <span data-ttu-id="dfaeb-124">変更されるとすれば、その防御用のコピーに対して加えられます。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-124">Any possible modifications are to that defensive copy.</span></span> <span data-ttu-id="dfaeb-125">このようなコピーが作成されないようにするには、`in` パラメーターを `in` 引数として渡す方法と、構造体を `readonly struct` として定義する方法の 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="dfaeb-125">The two ways to avoid these copies are to pass `in` parameters as `in` arguments or to define structures as `readonly struct`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="dfaeb-126">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="dfaeb-126">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dfaeb-127">参照</span><span class="sxs-lookup"><span data-stu-id="dfaeb-127">See Also</span></span>  
 [<span data-ttu-id="dfaeb-128">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="dfaeb-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="dfaeb-129">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="dfaeb-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="dfaeb-130">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="dfaeb-130">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="dfaeb-131">メソッド パラメーター</span><span class="sxs-lookup"><span data-stu-id="dfaeb-131">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)  
 [<span data-ttu-id="dfaeb-132">値の型による参照セマンティクス</span><span class="sxs-lookup"><span data-stu-id="dfaeb-132">Reference Semantics with Value Types</span></span>](../../../csharp/reference-semantics-with-value-types.md)