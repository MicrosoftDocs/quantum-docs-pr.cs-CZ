---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698208"
---
# <a name="rangestart-function"></a><span data-ttu-id="4c95e-102">RangeStart – funkce</span><span class="sxs-lookup"><span data-stu-id="4c95e-102">RangeStart function</span></span>

<span data-ttu-id="4c95e-103">Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="4c95e-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="4c95e-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4c95e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4c95e-105">Vrátí definovanou počáteční hodnotu daného rozsahu.</span><span class="sxs-lookup"><span data-stu-id="4c95e-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="4c95e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4c95e-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="4c95e-107">Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="4c95e-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="4c95e-108">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4c95e-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4c95e-109">Definovaná počáteční hodnota daného rozsahu.</span><span class="sxs-lookup"><span data-stu-id="4c95e-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="4c95e-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4c95e-110">Remarks</span></span>

<span data-ttu-id="4c95e-111">První prvek výrazu rozsahu je `start` , jeho druhý prvek je, `start+step` třetí prvek je `start+step+step` atd., dokud `end` není předán.</span><span class="sxs-lookup"><span data-stu-id="4c95e-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="4c95e-112">Všimněte si, že definovaná počáteční hodnota rozsahu je shodná s prvním prvkem sekvence, pokud rozsah neurčuje prázdnou sekvenci (například 2..</span><span class="sxs-lookup"><span data-stu-id="4c95e-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="4c95e-113">1).</span><span class="sxs-lookup"><span data-stu-id="4c95e-113">1).</span></span>