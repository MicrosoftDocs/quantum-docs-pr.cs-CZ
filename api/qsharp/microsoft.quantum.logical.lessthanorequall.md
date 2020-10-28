---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 333b76fc4885104e107dd25003a4e0dd5a9dd4af
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697280"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="99722-102">LessThanOrEqualL – funkce</span><span class="sxs-lookup"><span data-stu-id="99722-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="99722-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="99722-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="99722-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="99722-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="99722-105">Vrátí hodnotu true pouze v případě, že je číslo menší nebo rovno jinému číslu.</span><span class="sxs-lookup"><span data-stu-id="99722-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="99722-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="99722-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="99722-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="99722-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="99722-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="99722-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="99722-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="99722-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="99722-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="99722-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="99722-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="99722-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="99722-112">`true` pouze pokud je a pouze v případě, že `a` je menší nebo rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="99722-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="99722-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="99722-113">Remarks</span></span>

<span data-ttu-id="99722-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="99722-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```