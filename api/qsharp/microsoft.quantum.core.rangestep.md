---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698205"
---
# <a name="rangestep-function"></a><span data-ttu-id="b90e4-102">RangeStep – funkce</span><span class="sxs-lookup"><span data-stu-id="b90e4-102">RangeStep function</span></span>

<span data-ttu-id="b90e4-103">Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="b90e4-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="b90e4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b90e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b90e4-105">Vrátí celé číslo, které určuje, jak se počítá další hodnota rozsahu.</span><span class="sxs-lookup"><span data-stu-id="b90e4-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="b90e4-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b90e4-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="b90e4-107">Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="b90e4-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="b90e4-108">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b90e4-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b90e4-109">Definovaná hodnota kroku daného rozsahu.</span><span class="sxs-lookup"><span data-stu-id="b90e4-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="b90e4-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b90e4-110">Remarks</span></span>

<span data-ttu-id="b90e4-111">První prvek výrazu rozsahu je `start` , jeho druhý prvek je, `start+step` třetí prvek je `start+step+step` atd., dokud `end` není předán.</span><span class="sxs-lookup"><span data-stu-id="b90e4-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>