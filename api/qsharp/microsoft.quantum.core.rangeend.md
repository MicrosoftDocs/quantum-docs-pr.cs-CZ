---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 90a9e31bf5c4a5e92a35998ddaec8c9e9de9888e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224033"
---
# <a name="rangeend-function"></a><span data-ttu-id="13908-102">RangeEnd – funkce</span><span class="sxs-lookup"><span data-stu-id="13908-102">RangeEnd function</span></span>

<span data-ttu-id="13908-103">Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="13908-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="13908-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="13908-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="13908-105">Vrátí definovanou koncovou hodnotu daného rozsahu, což není nutně poslední prvek v sekvenci.</span><span class="sxs-lookup"><span data-stu-id="13908-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="13908-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="13908-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="13908-107">Rozsah: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="13908-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="13908-108">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="13908-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="13908-109">Definovaná koncová hodnota daného rozsahu.</span><span class="sxs-lookup"><span data-stu-id="13908-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="13908-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="13908-110">Remarks</span></span>

<span data-ttu-id="13908-111">První prvek výrazu rozsahu je `start` , jeho druhý prvek je, `start+step` třetí prvek je `start+step+step` atd., dokud `end` není předán.</span><span class="sxs-lookup"><span data-stu-id="13908-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="13908-112">Všimněte si, že definovaná koncová hodnota rozsahu se může lišit od posledního prvku v pořadí určeném rozsahem. například v rozsahu 0..</span><span class="sxs-lookup"><span data-stu-id="13908-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="13908-113">2...</span><span class="sxs-lookup"><span data-stu-id="13908-113">2 ..</span></span> <span data-ttu-id="13908-114">5 poslední prvek je 4, ale koncová hodnota je 5.</span><span class="sxs-lookup"><span data-stu-id="13908-114">5 the last element is 4 but the end value is 5.</span></span>