---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 39c8581fe795a1b76d2a6e81c238a271287c2c38
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213799"
---
# <a name="rangestep-function"></a><span data-ttu-id="8d0b7-102">RangeStep – funkce</span><span class="sxs-lookup"><span data-stu-id="8d0b7-102">RangeStep function</span></span>

<span data-ttu-id="8d0b7-103">Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="8d0b7-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="8d0b7-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8d0b7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8d0b7-105">Vrátí celé číslo, které určuje, jak se počítá další hodnota rozsahu.</span><span class="sxs-lookup"><span data-stu-id="8d0b7-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="8d0b7-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8d0b7-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="8d0b7-107">Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="8d0b7-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="8d0b7-108">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8d0b7-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8d0b7-109">Definovaná hodnota kroku daného rozsahu.</span><span class="sxs-lookup"><span data-stu-id="8d0b7-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="8d0b7-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="8d0b7-110">Remarks</span></span>

<span data-ttu-id="8d0b7-111">První prvek výrazu rozsahu je `start` , jeho druhý prvek je, `start+step` třetí prvek je `start+step+step` atd., dokud `end` není předán.</span><span class="sxs-lookup"><span data-stu-id="8d0b7-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>