---
uid: Microsoft.Quantum.Arrays.Merged
title: Sloučená funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: b3383f8a04e6fa23562aa81e5b911d06752f4fb5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220633"
---
# <a name="merged-function"></a><span data-ttu-id="4c691-102">Sloučená funkce</span><span class="sxs-lookup"><span data-stu-id="4c691-102">Merged function</span></span>

<span data-ttu-id="4c691-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4c691-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4c691-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4c691-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4c691-105">U dvou seřazených polí vrátí jedno pole obsahující prvky obou v setříděném pořadí.</span><span class="sxs-lookup"><span data-stu-id="4c691-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="4c691-106">Používá se interně slučovacím řazením.</span><span class="sxs-lookup"><span data-stu-id="4c691-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="4c691-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="4c691-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="4c691-108">porovnání: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4c691-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="4c691-109">Left: t []</span><span class="sxs-lookup"><span data-stu-id="4c691-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="4c691-110">Right: t []</span><span class="sxs-lookup"><span data-stu-id="4c691-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="4c691-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="4c691-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4c691-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4c691-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4c691-113">'S</span><span class="sxs-lookup"><span data-stu-id="4c691-113">'T</span></span>

