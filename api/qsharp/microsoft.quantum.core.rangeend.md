---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698229"
---
# <a name="rangeend-function"></a><span data-ttu-id="6e01b-102">RangeEnd – funkce</span><span class="sxs-lookup"><span data-stu-id="6e01b-102">RangeEnd function</span></span>

<span data-ttu-id="6e01b-103">Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="6e01b-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="6e01b-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6e01b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6e01b-105">Vrátí definovanou koncovou hodnotu daného rozsahu, což není nutně poslední prvek v sekvenci.</span><span class="sxs-lookup"><span data-stu-id="6e01b-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="6e01b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6e01b-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="6e01b-107">Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="6e01b-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="6e01b-108">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6e01b-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6e01b-109">Definovaná koncová hodnota daného rozsahu.</span><span class="sxs-lookup"><span data-stu-id="6e01b-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e01b-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="6e01b-110">Remarks</span></span>

<span data-ttu-id="6e01b-111">První prvek výrazu rozsahu je `start` , jeho druhý prvek je, `start+step` třetí prvek je `start+step+step` atd., dokud `end` není předán.</span><span class="sxs-lookup"><span data-stu-id="6e01b-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="6e01b-112">Všimněte si, že definovaná koncová hodnota rozsahu se může lišit od posledního prvku v pořadí určeném rozsahem. například v rozsahu 0..</span><span class="sxs-lookup"><span data-stu-id="6e01b-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="6e01b-113">2...</span><span class="sxs-lookup"><span data-stu-id="6e01b-113">2 ..</span></span> <span data-ttu-id="6e01b-114">5 poslední prvek je 4, ale koncová hodnota je 5.</span><span class="sxs-lookup"><span data-stu-id="6e01b-114">5 the last element is 4 but the end value is 5.</span></span>