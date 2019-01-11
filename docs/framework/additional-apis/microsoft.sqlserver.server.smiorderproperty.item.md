---
title: SmiOrderProperty.Item プロパティ (Microsoft.SqlServer.Server)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- Microsoft.SqlServer.Server.SmiOrderProperty.Item
- Microsoft.SqlServer.Server.SmiOrderProperty.get_Item
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: c586d07e8ea0c2ac0b1efb603e8900d681fd0a91
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152665"
---
# <a name="smiorderpropertyitem-property"></a><span data-ttu-id="7fec5-102">SmiOrderProperty.Item プロパティ</span><span class="sxs-lookup"><span data-stu-id="7fec5-102">SmiOrderProperty.Item Property</span></span>

<span data-ttu-id="7fec5-103">エンティティの列の順序を取得します。</span><span class="sxs-lookup"><span data-stu-id="7fec5-103">Gets the column order for the entity.</span></span> <span data-ttu-id="7fec5-104">このプロパティが含まれるアセンブリには、SQLAccess.dll で友人関係があります。</span><span class="sxs-lookup"><span data-stu-id="7fec5-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="7fec5-105">SQL Server で使用するものでは。</span><span class="sxs-lookup"><span data-stu-id="7fec5-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="7fec5-106">その他のデータベースには、そのデータベースによって提供されるホスティング メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fec5-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="7fec5-107">構文</span><span class="sxs-lookup"><span data-stu-id="7fec5-107">Syntax</span></span>

```csharp
internal SmiColumnOrder Item { get; }
```

## <a name="property-value"></a><span data-ttu-id="7fec5-108">プロパティの値</span><span class="sxs-lookup"><span data-stu-id="7fec5-108">Property value</span></span>

<span data-ttu-id="7fec5-109">列の順序。</span><span class="sxs-lookup"><span data-stu-id="7fec5-109">The column order.</span></span>

## <a name="remarks"></a><span data-ttu-id="7fec5-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="7fec5-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="7fec5-111">`SmiOrderProperty.Item`プロパティは内部であり、コード内で直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="7fec5-111">The `SmiOrderProperty.Item` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="7fec5-112">Microsoft はいかなる運用アプリケーションでこのプロパティの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7fec5-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="7fec5-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="7fec5-113">Requirements</span></span>

<span data-ttu-id="7fec5-114">**名前空間:** <xref:Microsoft.SqlServer.Server></span><span class="sxs-lookup"><span data-stu-id="7fec5-114">**Namespace:** <xref:Microsoft.SqlServer.Server></span></span>

<span data-ttu-id="7fec5-115">**アセンブリ:** System.Data (system.data.dll 内)</span><span class="sxs-lookup"><span data-stu-id="7fec5-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="7fec5-116">**.NET framework のバージョン:** 2.0 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="7fec5-116">**.NET Framework versions:** Available since 2.0.</span></span>