---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: Operace AssertPhaseLessThan
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: d003d83a84356ce52c5601135000813c7f119e4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707448"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="bba9c-102">Operace AssertPhaseLessThan</span><span class="sxs-lookup"><span data-stu-id="bba9c-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="bba9c-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bba9c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bba9c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bba9c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bba9c-105">Vyhodnotí, že `number` kódovaný v PhaseLittleEndian je menší než `value` .</span><span class="sxs-lookup"><span data-stu-id="bba9c-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="bba9c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="bba9c-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="bba9c-107">hodnota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bba9c-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bba9c-108">`number` musí být menší než to.</span><span class="sxs-lookup"><span data-stu-id="bba9c-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="bba9c-109">číslo: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bba9c-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="bba9c-110">Celé číslo bez znaménka, které je porovnáno s `value` .</span><span class="sxs-lookup"><span data-stu-id="bba9c-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bba9c-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bba9c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bba9c-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="bba9c-112">Remarks</span></span>

<span data-ttu-id="bba9c-113">Řízená verze této operace ignoruje ovládací prvky.</span><span class="sxs-lookup"><span data-stu-id="bba9c-113">The controlled version of this operation ignores controls.</span></span>