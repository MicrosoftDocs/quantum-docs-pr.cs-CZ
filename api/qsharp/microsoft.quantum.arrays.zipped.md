---
uid: Microsoft.Quantum.Arrays.Zipped
title: Funkce zip
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845333"
---
# <a name="zipped-function"></a><span data-ttu-id="621c8-102">Funkce zip</span><span class="sxs-lookup"><span data-stu-id="621c8-102">Zipped function</span></span>

<span data-ttu-id="621c8-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="621c8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="621c8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="621c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="621c8-105">Zadaná dvě pole, vrátí nové pole párů tak, aby každá dvojice obsahovala element z každého původního pole.</span><span class="sxs-lookup"><span data-stu-id="621c8-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="621c8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="621c8-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="621c8-107">Left: t []</span><span class="sxs-lookup"><span data-stu-id="621c8-107">left : 'T[]</span></span>

<span data-ttu-id="621c8-108">Pole obsahující hodnoty pro první prvek řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="621c8-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="621c8-109">Right: ' U []</span><span class="sxs-lookup"><span data-stu-id="621c8-109">right : 'U[]</span></span>

<span data-ttu-id="621c8-110">Pole obsahující hodnoty pro druhý prvek každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="621c8-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="621c8-111">Výstup: (ne, ' U) []</span><span class="sxs-lookup"><span data-stu-id="621c8-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="621c8-112">Pole obsahující páry formuláře `(left[idx], right[idx])` pro každý `idx` .</span><span class="sxs-lookup"><span data-stu-id="621c8-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="621c8-113">Pokud tato dvě pole nemají stejnou délku, výstup bude až na kratší dobu.</span><span class="sxs-lookup"><span data-stu-id="621c8-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="621c8-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="621c8-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="621c8-115">'S</span><span class="sxs-lookup"><span data-stu-id="621c8-115">'T</span></span>

<span data-ttu-id="621c8-116">Typ levého prvku pole.</span><span class="sxs-lookup"><span data-stu-id="621c8-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="621c8-117">U</span><span class="sxs-lookup"><span data-stu-id="621c8-117">'U</span></span>

<span data-ttu-id="621c8-118">Typ pravého pole prvků.</span><span class="sxs-lookup"><span data-stu-id="621c8-118">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="621c8-119">Příklad</span><span class="sxs-lookup"><span data-stu-id="621c8-119">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="621c8-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="621c8-120">See Also</span></span>

- [<span data-ttu-id="621c8-121">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="621c8-121">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="621c8-122">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="621c8-122">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="621c8-123">Microsoft. Forms. Arrays. Unzip</span><span class="sxs-lookup"><span data-stu-id="621c8-123">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)