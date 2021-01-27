---
uid: Microsoft.Quantum.Arrays.Excluding
title: Vyloučení funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: c117431e3d98bba4ed3d29cb0b171247bf77be0b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848658"
---
# <a name="excluding-function"></a><span data-ttu-id="ce3ea-102">Vyloučení funkce</span><span class="sxs-lookup"><span data-stu-id="ce3ea-102">Excluding function</span></span>

<span data-ttu-id="ce3ea-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ce3ea-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ce3ea-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ce3ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ce3ea-105">Vrátí pole obsahující prvky jiného pole, kromě prvků v daném seznamu indexů.</span><span class="sxs-lookup"><span data-stu-id="ce3ea-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ce3ea-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ce3ea-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="ce3ea-107">Remove: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ce3ea-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ce3ea-108">Pole indexů označuje, které prvky by měly být vyloučeny z výstupu.</span><span class="sxs-lookup"><span data-stu-id="ce3ea-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="ce3ea-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="ce3ea-109">array : 'T[]</span></span>

<span data-ttu-id="ce3ea-110">Pole, ze kterého jsou pořízeny hodnoty ve výstupním poli.</span><span class="sxs-lookup"><span data-stu-id="ce3ea-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="ce3ea-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="ce3ea-111">Output : 'T[]</span></span>

<span data-ttu-id="ce3ea-112">Pole `output` , jako `output[0]` je první prvek, `array` jehož index se nezobrazuje v `remove` , jako `output[1]` je například druhý takový prvek a tak dále.</span><span class="sxs-lookup"><span data-stu-id="ce3ea-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ce3ea-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ce3ea-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ce3ea-114">'S</span><span class="sxs-lookup"><span data-stu-id="ce3ea-114">'T</span></span>

<span data-ttu-id="ce3ea-115">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="ce3ea-115">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="ce3ea-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="ce3ea-116">Example</span></span>

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Excluding([1, 3, 4], array);
```