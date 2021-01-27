---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853660"
---
# <a name="rangereverse-function"></a><span data-ttu-id="30b93-102">RangeReverse – funkce</span><span class="sxs-lookup"><span data-stu-id="30b93-102">RangeReverse function</span></span>

<span data-ttu-id="30b93-103">Obor názvů: [Microsoft. Procore. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="30b93-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="30b93-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="30b93-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="30b93-105">Vrátí nový rozsah, který je zpětným rozsahem vstupu.</span><span class="sxs-lookup"><span data-stu-id="30b93-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="30b93-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="30b93-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="30b93-107">r: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="30b93-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="30b93-108">Vstupní rozsah</span><span class="sxs-lookup"><span data-stu-id="30b93-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="30b93-109">Výstup: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="30b93-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="30b93-110">Nový rozsah, který je opačnou barvou daného rozsahu.</span><span class="sxs-lookup"><span data-stu-id="30b93-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="30b93-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="30b93-111">Remarks</span></span>

<span data-ttu-id="30b93-112">Všimněte si, že obrácený rozsah není jednoduše `end` .. `-step` .. `start` , protože skutečný poslední prvek rozsahu nemůže být stejný jako `end` .</span><span class="sxs-lookup"><span data-stu-id="30b93-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>