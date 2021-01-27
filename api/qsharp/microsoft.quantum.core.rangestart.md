---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 5b04e8c860a4bd6af7b10b4dbf803b1eb69ef5d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831119"
---
# <a name="rangestart-function"></a><span data-ttu-id="845a2-102">RangeStart – funkce</span><span class="sxs-lookup"><span data-stu-id="845a2-102">RangeStart function</span></span>

<span data-ttu-id="845a2-103">Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="845a2-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="845a2-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="845a2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="845a2-105">Vrátí definovanou počáteční hodnotu daného rozsahu.</span><span class="sxs-lookup"><span data-stu-id="845a2-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="845a2-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="845a2-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="845a2-107">Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="845a2-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="845a2-108">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="845a2-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="845a2-109">Definovaná počáteční hodnota daného rozsahu.</span><span class="sxs-lookup"><span data-stu-id="845a2-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="845a2-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="845a2-110">Remarks</span></span>

<span data-ttu-id="845a2-111">První prvek výrazu rozsahu je `start` , jeho druhý prvek je, `start+step` třetí prvek je `start+step+step` atd., dokud `end` není předán.</span><span class="sxs-lookup"><span data-stu-id="845a2-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="845a2-112">Všimněte si, že definovaná počáteční hodnota rozsahu je shodná s prvním prvkem sekvence, pokud rozsah neurčuje prázdnou sekvenci (například 2..</span><span class="sxs-lookup"><span data-stu-id="845a2-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="845a2-113">1).</span><span class="sxs-lookup"><span data-stu-id="845a2-113">1).</span></span>