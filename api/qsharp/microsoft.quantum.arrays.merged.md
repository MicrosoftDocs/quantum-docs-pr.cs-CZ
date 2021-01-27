---
uid: Microsoft.Quantum.Arrays.Merged
title: Sloučená funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845615"
---
# <a name="merged-function"></a><span data-ttu-id="c84f6-102">Sloučená funkce</span><span class="sxs-lookup"><span data-stu-id="c84f6-102">Merged function</span></span>

<span data-ttu-id="c84f6-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c84f6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c84f6-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c84f6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c84f6-105">U dvou seřazených polí vrátí jedno pole obsahující prvky obou v setříděném pořadí.</span><span class="sxs-lookup"><span data-stu-id="c84f6-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="c84f6-106">Používá se interně slučovacím řazením.</span><span class="sxs-lookup"><span data-stu-id="c84f6-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="c84f6-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="c84f6-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="c84f6-108">porovnání: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c84f6-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="c84f6-109">Left: t []</span><span class="sxs-lookup"><span data-stu-id="c84f6-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="c84f6-110">Right: t []</span><span class="sxs-lookup"><span data-stu-id="c84f6-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="c84f6-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="c84f6-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c84f6-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c84f6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c84f6-113">'S</span><span class="sxs-lookup"><span data-stu-id="c84f6-113">'T</span></span>

