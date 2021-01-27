---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 667b579337eec28d6b75de61668bd79de176883e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853604"
---
# <a name="rangestep-function"></a><span data-ttu-id="4e761-102">RangeStep – funkce</span><span class="sxs-lookup"><span data-stu-id="4e761-102">RangeStep function</span></span>

<span data-ttu-id="4e761-103">Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="4e761-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="4e761-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4e761-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4e761-105">Vrátí celé číslo, které určuje, jak se počítá další hodnota rozsahu.</span><span class="sxs-lookup"><span data-stu-id="4e761-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="4e761-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4e761-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="4e761-107">Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="4e761-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="4e761-108">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4e761-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4e761-109">Definovaná hodnota kroku daného rozsahu.</span><span class="sxs-lookup"><span data-stu-id="4e761-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e761-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4e761-110">Remarks</span></span>

<span data-ttu-id="4e761-111">První prvek výrazu rozsahu je `start` , jeho druhý prvek je, `start+step` třetí prvek je `start+step+step` atd., dokud `end` není předán.</span><span class="sxs-lookup"><span data-stu-id="4e761-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>