---
uid: Microsoft.Quantum.Arrays.Exclude
title: Funkce Exclude
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: e1fa7e728d4846db90872055454a8182a77a518b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706049"
---
# <a name="exclude-function"></a><span data-ttu-id="dcec4-102">Funkce Exclude</span><span class="sxs-lookup"><span data-stu-id="dcec4-102">Exclude function</span></span>

<span data-ttu-id="dcec4-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dcec4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dcec4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dcec4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dcec4-105">Vrátí pole obsahující prvky jiného pole, kromě prvků v daném seznamu indexů.</span><span class="sxs-lookup"><span data-stu-id="dcec4-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="dcec4-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="dcec4-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="dcec4-107">Remove: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="dcec4-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="dcec4-108">Pole indexů označuje, které prvky by měly být vyloučeny z výstupu.</span><span class="sxs-lookup"><span data-stu-id="dcec4-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="dcec4-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="dcec4-109">array : 'T[]</span></span>

<span data-ttu-id="dcec4-110">Pole, ze kterého jsou pořízeny hodnoty ve výstupním poli.</span><span class="sxs-lookup"><span data-stu-id="dcec4-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="dcec4-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="dcec4-111">Output : 'T[]</span></span>

<span data-ttu-id="dcec4-112">Pole `output` , jako `output[0]` je první prvek, `array` jehož index se nezobrazuje v `remove` , jako `output[1]` je například druhý takový prvek a tak dále.</span><span class="sxs-lookup"><span data-stu-id="dcec4-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dcec4-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="dcec4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dcec4-114">'S</span><span class="sxs-lookup"><span data-stu-id="dcec4-114">'T</span></span>

<span data-ttu-id="dcec4-115">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="dcec4-115">The type of the array elements.</span></span>