---
uid: Microsoft.Quantum.Arrays.Reversed
title: Obrácená funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845461"
---
# <a name="reversed-function"></a><span data-ttu-id="03f41-102">Obrácená funkce</span><span class="sxs-lookup"><span data-stu-id="03f41-102">Reversed function</span></span>

<span data-ttu-id="03f41-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="03f41-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="03f41-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03f41-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03f41-105">Vytvoří pole, které obsahuje stejné prvky jako vstupní pole, ale v obráceném pořadí.</span><span class="sxs-lookup"><span data-stu-id="03f41-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="03f41-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="03f41-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="03f41-107">Array: t []</span><span class="sxs-lookup"><span data-stu-id="03f41-107">array : 'T[]</span></span>

<span data-ttu-id="03f41-108">Pole, jehož prvky mají být zkopírovány v obráceném pořadí.</span><span class="sxs-lookup"><span data-stu-id="03f41-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="03f41-109">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="03f41-109">Output : 'T[]</span></span>

<span data-ttu-id="03f41-110">Pole obsahující prvky `array[Length(array) - 1]` ..</span><span class="sxs-lookup"><span data-stu-id="03f41-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="03f41-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="03f41-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="03f41-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="03f41-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="03f41-113">'S</span><span class="sxs-lookup"><span data-stu-id="03f41-113">'T</span></span>

<span data-ttu-id="03f41-114">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="03f41-114">The type of the array elements.</span></span>