---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: Operace AssertPhaseLessThan
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 8a943ff937593801bd308ab4224c7051ff8a10cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223744"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="e09c9-102">Operace AssertPhaseLessThan</span><span class="sxs-lookup"><span data-stu-id="e09c9-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="e09c9-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e09c9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e09c9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e09c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e09c9-105">Vyhodnotí, že `number` kódovaný v PhaseLittleEndian je menší než `value` .</span><span class="sxs-lookup"><span data-stu-id="e09c9-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e09c9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e09c9-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="e09c9-107">hodnota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e09c9-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e09c9-108">`number` musí být menší než to.</span><span class="sxs-lookup"><span data-stu-id="e09c9-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="e09c9-109">číslo: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e09c9-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="e09c9-110">Celé číslo bez znaménka, které je porovnáno s `value` .</span><span class="sxs-lookup"><span data-stu-id="e09c9-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e09c9-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e09c9-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e09c9-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e09c9-112">Remarks</span></span>

<span data-ttu-id="e09c9-113">Řízená verze této operace ignoruje ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="e09c9-113">The controlled version of this operation ignores controls.</span></span>