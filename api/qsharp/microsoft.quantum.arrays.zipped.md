---
uid: Microsoft.Quantum.Arrays.Zipped
title: Funkce zip
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705672"
---
# <a name="zipped-function"></a><span data-ttu-id="da348-102">Funkce zip</span><span class="sxs-lookup"><span data-stu-id="da348-102">Zipped function</span></span>

<span data-ttu-id="da348-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="da348-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="da348-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="da348-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="da348-105">Zadaná dvě pole, vrátí nové pole párů tak, aby každá dvojice obsahovala element z každého původního pole.</span><span class="sxs-lookup"><span data-stu-id="da348-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="da348-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="da348-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="da348-107">Left: t []</span><span class="sxs-lookup"><span data-stu-id="da348-107">left : 'T[]</span></span>

<span data-ttu-id="da348-108">Pole obsahující hodnoty pro první prvek řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="da348-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="da348-109">Right: ' U []</span><span class="sxs-lookup"><span data-stu-id="da348-109">right : 'U[]</span></span>

<span data-ttu-id="da348-110">Pole obsahující hodnoty pro druhý prvek každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="da348-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="da348-111">Výstup: (ne, ' U) []</span><span class="sxs-lookup"><span data-stu-id="da348-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="da348-112">Pole obsahující páry formuláře `(left[idx], right[idx])` pro každý `idx` .</span><span class="sxs-lookup"><span data-stu-id="da348-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="da348-113">Pokud tato dvě pole nemají stejnou délku, výstup bude až na kratší dobu.</span><span class="sxs-lookup"><span data-stu-id="da348-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="da348-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="da348-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="da348-115">'S</span><span class="sxs-lookup"><span data-stu-id="da348-115">'T</span></span>

<span data-ttu-id="da348-116">Typ levého prvku pole.</span><span class="sxs-lookup"><span data-stu-id="da348-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="da348-117">U</span><span class="sxs-lookup"><span data-stu-id="da348-117">'U</span></span>

<span data-ttu-id="da348-118">Typ pravého pole prvků.</span><span class="sxs-lookup"><span data-stu-id="da348-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="da348-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="da348-119">See Also</span></span>

- [<span data-ttu-id="da348-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="da348-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="da348-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="da348-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="da348-122">Microsoft. Forms. Arrays. Unzip</span><span class="sxs-lookup"><span data-stu-id="da348-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)