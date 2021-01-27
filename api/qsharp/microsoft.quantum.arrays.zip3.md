---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 – – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: b41b0789cdf90db534ee7a50ff25eb3a931ec683
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845355"
---
# <a name="zip3-function"></a><span data-ttu-id="63874-102">Zip3 – – funkce</span><span class="sxs-lookup"><span data-stu-id="63874-102">Zip3 function</span></span>

<span data-ttu-id="63874-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="63874-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="63874-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63874-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="63874-105">Zip3 – se už nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="63874-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="63874-106"><xref:Microsoft.Quantum.Arrays.Zipped3>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="63874-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="63874-107">Zadaná tři pole vrací nové pole tří řazených kolekcí členů, aby každá 3-řazená kolekce členů obsahovala element z každého původního pole.</span><span class="sxs-lookup"><span data-stu-id="63874-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="63874-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="63874-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="63874-109">First: t 1 []</span><span class="sxs-lookup"><span data-stu-id="63874-109">first : 'T1[]</span></span>

<span data-ttu-id="63874-110">Pole obsahující hodnoty pro první prvek řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="63874-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="63874-111">sekundy: t 2 []</span><span class="sxs-lookup"><span data-stu-id="63874-111">second : 'T2[]</span></span>

<span data-ttu-id="63874-112">Pole obsahující hodnoty pro druhý prvek každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="63874-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="63874-113">třetí: t 3 []</span><span class="sxs-lookup"><span data-stu-id="63874-113">third : 'T3[]</span></span>

<span data-ttu-id="63874-114">Pole obsahující hodnoty třetího prvku každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="63874-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="63874-115">Výstup: (ne 1, t 2, t 3) []</span><span class="sxs-lookup"><span data-stu-id="63874-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="63874-116">Pole obsahující 3 – řazené kolekce členů formuláře `(first[idx], second[idx], third[idx])` pro každý `idx` .</span><span class="sxs-lookup"><span data-stu-id="63874-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="63874-117">Pokud se tři pole neshodují, bude výstup, který je kratší než tento počet vstupů.</span><span class="sxs-lookup"><span data-stu-id="63874-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="63874-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="63874-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="63874-119">Ne 1</span><span class="sxs-lookup"><span data-stu-id="63874-119">'T1</span></span>

<span data-ttu-id="63874-120">Typ prvních prvků pole.</span><span class="sxs-lookup"><span data-stu-id="63874-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="63874-121">Ne 2</span><span class="sxs-lookup"><span data-stu-id="63874-121">'T2</span></span>

<span data-ttu-id="63874-122">Typ druhých prvků pole.</span><span class="sxs-lookup"><span data-stu-id="63874-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="63874-123">Ne 3</span><span class="sxs-lookup"><span data-stu-id="63874-123">'T3</span></span>

<span data-ttu-id="63874-124">Typ elementů třetího pole.</span><span class="sxs-lookup"><span data-stu-id="63874-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="63874-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="63874-125">See Also</span></span>

- [<span data-ttu-id="63874-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="63874-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="63874-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="63874-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)