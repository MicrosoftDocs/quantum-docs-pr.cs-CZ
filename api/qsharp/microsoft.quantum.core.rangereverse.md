---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698225"
---
# <a name="rangereverse-function"></a><span data-ttu-id="3c3cc-102">RangeReverse – funkce</span><span class="sxs-lookup"><span data-stu-id="3c3cc-102">RangeReverse function</span></span>

<span data-ttu-id="3c3cc-103">Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="3c3cc-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="3c3cc-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c3cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c3cc-105">Vrátí nový rozsah, který je zpětným rozsahem vstupu.</span><span class="sxs-lookup"><span data-stu-id="3c3cc-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="3c3cc-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3c3cc-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="3c3cc-107">r: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="3c3cc-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="3c3cc-108">Vstupní rozsah</span><span class="sxs-lookup"><span data-stu-id="3c3cc-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="3c3cc-109">Výstup: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="3c3cc-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="3c3cc-110">Nový rozsah, který je opačnou barvou daného rozsahu.</span><span class="sxs-lookup"><span data-stu-id="3c3cc-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c3cc-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3c3cc-111">Remarks</span></span>

<span data-ttu-id="3c3cc-112">Všimněte si, že obrácený rozsah není jednoduše `end` .. `-step` .. `start` , protože skutečný poslední prvek rozsahu nemůže být stejný jako `end` .</span><span class="sxs-lookup"><span data-stu-id="3c3cc-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>