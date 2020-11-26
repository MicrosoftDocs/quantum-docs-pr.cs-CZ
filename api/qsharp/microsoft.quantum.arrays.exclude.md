---
uid: Microsoft.Quantum.Arrays.Exclude
title: Funkce Exclude
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 4ea0d754fce4fc7e3e4e42e55b56720cb3f95ca6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221347"
---
# <a name="exclude-function"></a><span data-ttu-id="09c33-102">Funkce Exclude</span><span class="sxs-lookup"><span data-stu-id="09c33-102">Exclude function</span></span>

<span data-ttu-id="09c33-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="09c33-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="09c33-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="09c33-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="09c33-105">Vrátí pole obsahující prvky jiného pole, kromě prvků v daném seznamu indexů.</span><span class="sxs-lookup"><span data-stu-id="09c33-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="09c33-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="09c33-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="09c33-107">Remove: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="09c33-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="09c33-108">Pole indexů označuje, které prvky by měly být vyloučeny z výstupu.</span><span class="sxs-lookup"><span data-stu-id="09c33-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="09c33-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="09c33-109">array : 'T[]</span></span>

<span data-ttu-id="09c33-110">Pole, ze kterého jsou pořízeny hodnoty ve výstupním poli.</span><span class="sxs-lookup"><span data-stu-id="09c33-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="09c33-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="09c33-111">Output : 'T[]</span></span>

<span data-ttu-id="09c33-112">Pole `output` , jako `output[0]` je první prvek, `array` jehož index se nezobrazuje v `remove` , jako `output[1]` je například druhý takový prvek a tak dále.</span><span class="sxs-lookup"><span data-stu-id="09c33-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="09c33-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="09c33-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="09c33-114">'S</span><span class="sxs-lookup"><span data-stu-id="09c33-114">'T</span></span>

<span data-ttu-id="09c33-115">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="09c33-115">The type of the array elements.</span></span>