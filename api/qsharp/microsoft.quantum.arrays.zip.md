---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 32fea60fc36bfdbaa2ab2f3560f291bf4ce4fa51
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705681"
---
# <a name="zip-function"></a><span data-ttu-id="e0314-102">Zip – funkce</span><span class="sxs-lookup"><span data-stu-id="e0314-102">Zip function</span></span>

<span data-ttu-id="e0314-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e0314-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e0314-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e0314-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="e0314-105">Zip je zastaralý.</span><span class="sxs-lookup"><span data-stu-id="e0314-105">Zip has been deprecated.</span></span> <span data-ttu-id="e0314-106"><xref:Microsoft.Quantum.Arrays.Zipped>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="e0314-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="e0314-107">Zadaná dvě pole, vrátí nové pole párů tak, aby každá dvojice obsahovala element z každého původního pole.</span><span class="sxs-lookup"><span data-stu-id="e0314-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="e0314-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="e0314-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="e0314-109">Left: t []</span><span class="sxs-lookup"><span data-stu-id="e0314-109">left : 'T[]</span></span>

<span data-ttu-id="e0314-110">Pole obsahující hodnoty pro první prvek řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="e0314-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="e0314-111">Right: ' U []</span><span class="sxs-lookup"><span data-stu-id="e0314-111">right : 'U[]</span></span>

<span data-ttu-id="e0314-112">Pole obsahující hodnoty pro druhý prvek každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="e0314-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="e0314-113">Výstup: (ne, ' U) []</span><span class="sxs-lookup"><span data-stu-id="e0314-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="e0314-114">Pole obsahující páry formuláře `(left[idx], right[idx])` pro každý `idx` .</span><span class="sxs-lookup"><span data-stu-id="e0314-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="e0314-115">Pokud tato dvě pole nemají stejnou délku, výstup bude až na kratší dobu.</span><span class="sxs-lookup"><span data-stu-id="e0314-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e0314-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e0314-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e0314-117">'S</span><span class="sxs-lookup"><span data-stu-id="e0314-117">'T</span></span>

<span data-ttu-id="e0314-118">Typ levého prvku pole.</span><span class="sxs-lookup"><span data-stu-id="e0314-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="e0314-119">U</span><span class="sxs-lookup"><span data-stu-id="e0314-119">'U</span></span>

<span data-ttu-id="e0314-120">Typ pravého pole prvků.</span><span class="sxs-lookup"><span data-stu-id="e0314-120">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0314-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="e0314-121">See Also</span></span>

- [<span data-ttu-id="e0314-122">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="e0314-122">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="e0314-123">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="e0314-123">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="e0314-124">Microsoft. Forms. Arrays. Unzip</span><span class="sxs-lookup"><span data-stu-id="e0314-124">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)