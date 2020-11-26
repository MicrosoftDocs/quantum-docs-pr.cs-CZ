---
uid: Microsoft.Quantum.Arrays.Most
title: Většina funkcí
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 81e66e0b64ae8dfc44d163b68370ccadd191c729
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220599"
---
# <a name="most-function"></a><span data-ttu-id="35e20-102">Většina funkcí</span><span class="sxs-lookup"><span data-stu-id="35e20-102">Most function</span></span>

<span data-ttu-id="35e20-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="35e20-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="35e20-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35e20-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35e20-105">Vytvoří pole, které se rovná vstupnímu poli s tím rozdílem, že poslední prvek pole je vyřazen.</span><span class="sxs-lookup"><span data-stu-id="35e20-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="35e20-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="35e20-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="35e20-107">Array: t []</span><span class="sxs-lookup"><span data-stu-id="35e20-107">array : 'T[]</span></span>

<span data-ttu-id="35e20-108">Pole, jehož první až poslední prvky mají tvořit výstupní pole.</span><span class="sxs-lookup"><span data-stu-id="35e20-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="35e20-109">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="35e20-109">Output : 'T[]</span></span>

<span data-ttu-id="35e20-110">Pole obsahující prvky `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="35e20-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="35e20-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="35e20-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="35e20-112">'S</span><span class="sxs-lookup"><span data-stu-id="35e20-112">'T</span></span>

<span data-ttu-id="35e20-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="35e20-113">The type of the array elements.</span></span>