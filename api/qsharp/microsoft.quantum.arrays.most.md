---
uid: Microsoft.Quantum.Arrays.Most
title: Většina funkcí
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705864"
---
# <a name="most-function"></a><span data-ttu-id="a982d-102">Většina funkcí</span><span class="sxs-lookup"><span data-stu-id="a982d-102">Most function</span></span>

<span data-ttu-id="a982d-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a982d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a982d-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a982d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a982d-105">Vytvoří pole, které se rovná vstupnímu poli s tím rozdílem, že poslední prvek pole je vyřazen.</span><span class="sxs-lookup"><span data-stu-id="a982d-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="a982d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a982d-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="a982d-107">Array: t []</span><span class="sxs-lookup"><span data-stu-id="a982d-107">array : 'T[]</span></span>

<span data-ttu-id="a982d-108">Pole, jehož první až poslední prvky mají tvořit výstupní pole.</span><span class="sxs-lookup"><span data-stu-id="a982d-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="a982d-109">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="a982d-109">Output : 'T[]</span></span>

<span data-ttu-id="a982d-110">Pole obsahující prvky `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="a982d-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a982d-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a982d-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a982d-112">'S</span><span class="sxs-lookup"><span data-stu-id="a982d-112">'T</span></span>

<span data-ttu-id="a982d-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="a982d-113">The type of the array elements.</span></span>