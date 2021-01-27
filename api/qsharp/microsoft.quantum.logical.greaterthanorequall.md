---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: f33a7f17f3391d87e3eff9fb31939586036e83f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815848"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="38fc8-102">GreaterThanOrEqualL – funkce</span><span class="sxs-lookup"><span data-stu-id="38fc8-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="38fc8-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="38fc8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="38fc8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38fc8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38fc8-105">Vrátí hodnotu true pouze v případě, že je číslo větší nebo rovno jinému číslu.</span><span class="sxs-lookup"><span data-stu-id="38fc8-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="38fc8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="38fc8-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="38fc8-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="38fc8-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="38fc8-108">První hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="38fc8-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="38fc8-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="38fc8-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="38fc8-110">Druhá hodnota, která se má porovnat.</span><span class="sxs-lookup"><span data-stu-id="38fc8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="38fc8-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="38fc8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="38fc8-112">`true` IF a pouze pokud `a` je větší než nebo je rovno `b` .</span><span class="sxs-lookup"><span data-stu-id="38fc8-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="38fc8-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="38fc8-113">Remarks</span></span>

<span data-ttu-id="38fc8-114">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="38fc8-114">The following are equivalent:</span></span>

```qsharp
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```