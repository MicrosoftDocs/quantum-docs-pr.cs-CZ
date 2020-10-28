---
uid: Microsoft.Quantum.Arrays.Merged
title: Sloučená funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705872"
---
# <a name="merged-function"></a><span data-ttu-id="5cb47-102">Sloučená funkce</span><span class="sxs-lookup"><span data-stu-id="5cb47-102">Merged function</span></span>

<span data-ttu-id="5cb47-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5cb47-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5cb47-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5cb47-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5cb47-105">U dvou seřazených polí vrátí jedno pole obsahující prvky obou v setříděném pořadí.</span><span class="sxs-lookup"><span data-stu-id="5cb47-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="5cb47-106">Používá se interně slučovacím řazením.</span><span class="sxs-lookup"><span data-stu-id="5cb47-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="5cb47-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="5cb47-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="5cb47-108">porovnání: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5cb47-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="5cb47-109">Left: t []</span><span class="sxs-lookup"><span data-stu-id="5cb47-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="5cb47-110">Right: t []</span><span class="sxs-lookup"><span data-stu-id="5cb47-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="5cb47-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="5cb47-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5cb47-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5cb47-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5cb47-113">'S</span><span class="sxs-lookup"><span data-stu-id="5cb47-113">'T</span></span>

