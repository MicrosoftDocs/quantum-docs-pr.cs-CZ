---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698264"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="0105e-102">RangeAsIntArray – funkce</span><span class="sxs-lookup"><span data-stu-id="0105e-102">RangeAsIntArray function</span></span>

<span data-ttu-id="0105e-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="0105e-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="0105e-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0105e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0105e-105">Vytvoří pole celých čísel, která jsou vyhodnocena spuštěním `arr` .. krok.. účelu.</span><span class="sxs-lookup"><span data-stu-id="0105e-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="0105e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="0105e-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="0105e-107">Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="0105e-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="0105e-108">`Range`Hodnoty, `start..step..end` které mají být převedeny na pole.</span><span class="sxs-lookup"><span data-stu-id="0105e-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="0105e-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0105e-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0105e-110">Nové pole celých čísel odpovídající hodnotám, které prochází `range` .</span><span class="sxs-lookup"><span data-stu-id="0105e-110">A new array of integers corresponding to values iterated over by `range`.</span></span>