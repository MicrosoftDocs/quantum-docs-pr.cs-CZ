---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213833"
---
# <a name="rangereverse-function"></a><span data-ttu-id="f4828-102">RangeReverse – funkce</span><span class="sxs-lookup"><span data-stu-id="f4828-102">RangeReverse function</span></span>

<span data-ttu-id="f4828-103">Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="f4828-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="f4828-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f4828-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f4828-105">Vrátí nový rozsah, který je zpětným rozsahem vstupu.</span><span class="sxs-lookup"><span data-stu-id="f4828-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="f4828-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f4828-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="f4828-107">r: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="f4828-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="f4828-108">Vstupní rozsah</span><span class="sxs-lookup"><span data-stu-id="f4828-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="f4828-109">Výstup: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="f4828-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="f4828-110">Nový rozsah, který je opačnou barvou daného rozsahu.</span><span class="sxs-lookup"><span data-stu-id="f4828-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4828-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f4828-111">Remarks</span></span>

<span data-ttu-id="f4828-112">Všimněte si, že obrácený rozsah není jednoduše `end` .. `-step` .. `start` , protože skutečný poslední prvek rozsahu nemůže být stejný jako `end` .</span><span class="sxs-lookup"><span data-stu-id="f4828-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>