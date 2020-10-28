---
uid: Microsoft.Quantum.Arrays.Reversed
title: Obrácená funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705801"
---
# <a name="reversed-function"></a><span data-ttu-id="db847-102">Obrácená funkce</span><span class="sxs-lookup"><span data-stu-id="db847-102">Reversed function</span></span>

<span data-ttu-id="db847-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="db847-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="db847-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="db847-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="db847-105">Vytvoří pole, které obsahuje stejné prvky jako vstupní pole, ale v obráceném pořadí.</span><span class="sxs-lookup"><span data-stu-id="db847-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="db847-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="db847-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="db847-107">Array: t []</span><span class="sxs-lookup"><span data-stu-id="db847-107">array : 'T[]</span></span>

<span data-ttu-id="db847-108">Pole, jehož prvky mají být zkopírovány v obráceném pořadí.</span><span class="sxs-lookup"><span data-stu-id="db847-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="db847-109">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="db847-109">Output : 'T[]</span></span>

<span data-ttu-id="db847-110">Pole obsahující prvky `array[Length(array) - 1]` ..</span><span class="sxs-lookup"><span data-stu-id="db847-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="db847-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="db847-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="db847-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="db847-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="db847-113">'S</span><span class="sxs-lookup"><span data-stu-id="db847-113">'T</span></span>

<span data-ttu-id="db847-114">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="db847-114">The type of the array elements.</span></span>