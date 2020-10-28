---
uid: Microsoft.Quantum.Arrays.Excluding
title: Vyloučení funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 8848c6e89da50efb4f7550168f1757b25a214a24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706048"
---
# <a name="excluding-function"></a><span data-ttu-id="e268c-102">Vyloučení funkce</span><span class="sxs-lookup"><span data-stu-id="e268c-102">Excluding function</span></span>

<span data-ttu-id="e268c-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e268c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e268c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e268c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e268c-105">Vrátí pole obsahující prvky jiného pole, kromě prvků v daném seznamu indexů.</span><span class="sxs-lookup"><span data-stu-id="e268c-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e268c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e268c-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="e268c-107">Remove: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e268c-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e268c-108">Pole indexů označuje, které prvky by měly být vyloučeny z výstupu.</span><span class="sxs-lookup"><span data-stu-id="e268c-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="e268c-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="e268c-109">array : 'T[]</span></span>

<span data-ttu-id="e268c-110">Pole, ze kterého jsou pořízeny hodnoty ve výstupním poli.</span><span class="sxs-lookup"><span data-stu-id="e268c-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="e268c-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="e268c-111">Output : 'T[]</span></span>

<span data-ttu-id="e268c-112">Pole `output` , jako `output[0]` je první prvek, `array` jehož index se nezobrazuje v `remove` , jako `output[1]` je například druhý takový prvek a tak dále.</span><span class="sxs-lookup"><span data-stu-id="e268c-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e268c-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e268c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e268c-114">'S</span><span class="sxs-lookup"><span data-stu-id="e268c-114">'T</span></span>

<span data-ttu-id="e268c-115">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="e268c-115">The type of the array elements.</span></span>