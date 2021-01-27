---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 8ed658003f749efd31b8d841cecbb0a23a471af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850900"
---
# <a name="zip-function"></a><span data-ttu-id="50af6-102">Zip – funkce</span><span class="sxs-lookup"><span data-stu-id="50af6-102">Zip function</span></span>

<span data-ttu-id="50af6-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="50af6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="50af6-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="50af6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="50af6-105">Zip je zastaralý.</span><span class="sxs-lookup"><span data-stu-id="50af6-105">Zip has been deprecated.</span></span> <span data-ttu-id="50af6-106"><xref:Microsoft.Quantum.Arrays.Zipped>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="50af6-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="50af6-107">Zadaná dvě pole, vrátí nové pole párů tak, aby každá dvojice obsahovala element z každého původního pole.</span><span class="sxs-lookup"><span data-stu-id="50af6-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="50af6-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="50af6-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="50af6-109">Left: t []</span><span class="sxs-lookup"><span data-stu-id="50af6-109">left : 'T[]</span></span>

<span data-ttu-id="50af6-110">Pole obsahující hodnoty pro první prvek řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="50af6-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="50af6-111">Right: ' U []</span><span class="sxs-lookup"><span data-stu-id="50af6-111">right : 'U[]</span></span>

<span data-ttu-id="50af6-112">Pole obsahující hodnoty pro druhý prvek každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="50af6-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="50af6-113">Výstup: (ne, ' U) []</span><span class="sxs-lookup"><span data-stu-id="50af6-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="50af6-114">Pole obsahující páry formuláře `(left[idx], right[idx])` pro každý `idx` .</span><span class="sxs-lookup"><span data-stu-id="50af6-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="50af6-115">Pokud tato dvě pole nemají stejnou délku, výstup bude až na kratší dobu.</span><span class="sxs-lookup"><span data-stu-id="50af6-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="50af6-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="50af6-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="50af6-117">'S</span><span class="sxs-lookup"><span data-stu-id="50af6-117">'T</span></span>

<span data-ttu-id="50af6-118">Typ levého prvku pole.</span><span class="sxs-lookup"><span data-stu-id="50af6-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="50af6-119">U</span><span class="sxs-lookup"><span data-stu-id="50af6-119">'U</span></span>

<span data-ttu-id="50af6-120">Typ pravého pole prvků.</span><span class="sxs-lookup"><span data-stu-id="50af6-120">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="50af6-121">Příklad</span><span class="sxs-lookup"><span data-stu-id="50af6-121">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zip(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="50af6-122">Viz také</span><span class="sxs-lookup"><span data-stu-id="50af6-122">See Also</span></span>

- [<span data-ttu-id="50af6-123">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="50af6-123">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="50af6-124">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="50af6-124">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="50af6-125">Microsoft. Forms. Arrays. Unzip</span><span class="sxs-lookup"><span data-stu-id="50af6-125">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)