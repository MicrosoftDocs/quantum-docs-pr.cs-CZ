---
uid: Microsoft.Quantum.Arrays.Zipped
title: Funkce zip
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 56ed97d573bf29dddb7cdb1c3f360218bf97889a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219749"
---
# <a name="zipped-function"></a><span data-ttu-id="ba191-102">Funkce zip</span><span class="sxs-lookup"><span data-stu-id="ba191-102">Zipped function</span></span>

<span data-ttu-id="ba191-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ba191-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ba191-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ba191-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ba191-105">Zadaná dvě pole, vrátí nové pole párů tak, aby každá dvojice obsahovala element z každého původního pole.</span><span class="sxs-lookup"><span data-stu-id="ba191-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="ba191-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ba191-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="ba191-107">Left: t []</span><span class="sxs-lookup"><span data-stu-id="ba191-107">left : 'T[]</span></span>

<span data-ttu-id="ba191-108">Pole obsahující hodnoty pro první prvek řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="ba191-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="ba191-109">Right: ' U []</span><span class="sxs-lookup"><span data-stu-id="ba191-109">right : 'U[]</span></span>

<span data-ttu-id="ba191-110">Pole obsahující hodnoty pro druhý prvek každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="ba191-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="ba191-111">Výstup: (ne, ' U) []</span><span class="sxs-lookup"><span data-stu-id="ba191-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="ba191-112">Pole obsahující páry formuláře `(left[idx], right[idx])` pro každý `idx` .</span><span class="sxs-lookup"><span data-stu-id="ba191-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="ba191-113">Pokud tato dvě pole nemají stejnou délku, výstup bude až na kratší dobu.</span><span class="sxs-lookup"><span data-stu-id="ba191-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ba191-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ba191-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ba191-115">'S</span><span class="sxs-lookup"><span data-stu-id="ba191-115">'T</span></span>

<span data-ttu-id="ba191-116">Typ levého prvku pole.</span><span class="sxs-lookup"><span data-stu-id="ba191-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="ba191-117">U</span><span class="sxs-lookup"><span data-stu-id="ba191-117">'U</span></span>

<span data-ttu-id="ba191-118">Typ pravého pole prvků.</span><span class="sxs-lookup"><span data-stu-id="ba191-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba191-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="ba191-119">See Also</span></span>

- [<span data-ttu-id="ba191-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="ba191-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="ba191-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="ba191-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="ba191-122">Microsoft. Forms. Arrays. Unzip</span><span class="sxs-lookup"><span data-stu-id="ba191-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)