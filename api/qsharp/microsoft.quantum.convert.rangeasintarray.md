---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: f756e42aef7dc600e1fc6943a02513ac791f2320
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214003"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="df82c-102">RangeAsIntArray – funkce</span><span class="sxs-lookup"><span data-stu-id="df82c-102">RangeAsIntArray function</span></span>

<span data-ttu-id="df82c-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="df82c-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="df82c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df82c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df82c-105">Vytvoří pole celých čísel, která jsou vyhodnocena spuštěním `arr` .. krok.. účelu.</span><span class="sxs-lookup"><span data-stu-id="df82c-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="df82c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="df82c-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="df82c-107">Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="df82c-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="df82c-108">`Range`Hodnoty, `start..step..end` které mají být převedeny na pole.</span><span class="sxs-lookup"><span data-stu-id="df82c-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="df82c-109">Výstup: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="df82c-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="df82c-110">Nové pole celých čísel odpovídající hodnotám, které prochází `range` .</span><span class="sxs-lookup"><span data-stu-id="df82c-110">A new array of integers corresponding to values iterated over by `range`.</span></span>