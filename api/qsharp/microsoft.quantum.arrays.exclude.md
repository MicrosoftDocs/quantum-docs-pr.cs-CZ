---
uid: Microsoft.Quantum.Arrays.Exclude
title: Funkce Exclude
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 76cdee56e84951c63e80babfdca6a3de33583cab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848676"
---
# <a name="exclude-function"></a><span data-ttu-id="09723-102">Funkce Exclude</span><span class="sxs-lookup"><span data-stu-id="09723-102">Exclude function</span></span>

<span data-ttu-id="09723-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="09723-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="09723-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="09723-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="09723-105">Vrátí pole obsahující prvky jiného pole, kromě prvků v daném seznamu indexů.</span><span class="sxs-lookup"><span data-stu-id="09723-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="09723-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="09723-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="09723-107">Remove: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="09723-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="09723-108">Pole indexů označuje, které prvky by měly být vyloučeny z výstupu.</span><span class="sxs-lookup"><span data-stu-id="09723-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="09723-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="09723-109">array : 'T[]</span></span>

<span data-ttu-id="09723-110">Pole, ze kterého jsou pořízeny hodnoty ve výstupním poli.</span><span class="sxs-lookup"><span data-stu-id="09723-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="09723-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="09723-111">Output : 'T[]</span></span>

<span data-ttu-id="09723-112">Pole `output` , jako `output[0]` je první prvek, `array` jehož index se nezobrazuje v `remove` , jako `output[1]` je například druhý takový prvek a tak dále.</span><span class="sxs-lookup"><span data-stu-id="09723-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="09723-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="09723-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="09723-114">'S</span><span class="sxs-lookup"><span data-stu-id="09723-114">'T</span></span>

<span data-ttu-id="09723-115">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="09723-115">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="09723-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="09723-116">Example</span></span>

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Exclude([1, 3, 4], array);
```