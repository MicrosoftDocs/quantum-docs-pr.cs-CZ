---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 – – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: f4b1a769614ee9434b2141b8fcb91f34cd071bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705680"
---
# <a name="zip3-function"></a><span data-ttu-id="b8146-102">Zip3 – – funkce</span><span class="sxs-lookup"><span data-stu-id="b8146-102">Zip3 function</span></span>

<span data-ttu-id="b8146-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b8146-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b8146-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b8146-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="b8146-105">Zip3 – se už nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="b8146-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="b8146-106"><xref:Microsoft.Quantum.Arrays.Zipped3>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="b8146-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="b8146-107">Zadaná tři pole vrací nové pole tří řazených kolekcí členů, aby každá 3-řazená kolekce členů obsahovala element z každého původního pole.</span><span class="sxs-lookup"><span data-stu-id="b8146-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="b8146-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="b8146-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="b8146-109">First: t 1 []</span><span class="sxs-lookup"><span data-stu-id="b8146-109">first : 'T1[]</span></span>

<span data-ttu-id="b8146-110">Pole obsahující hodnoty pro první prvek řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="b8146-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="b8146-111">sekundy: t 2 []</span><span class="sxs-lookup"><span data-stu-id="b8146-111">second : 'T2[]</span></span>

<span data-ttu-id="b8146-112">Pole obsahující hodnoty pro druhý prvek každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="b8146-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="b8146-113">třetí: t 3 []</span><span class="sxs-lookup"><span data-stu-id="b8146-113">third : 'T3[]</span></span>

<span data-ttu-id="b8146-114">Pole obsahující hodnoty třetího prvku každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="b8146-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="b8146-115">Výstup: (ne 1, t 2, t 3) []</span><span class="sxs-lookup"><span data-stu-id="b8146-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="b8146-116">Pole obsahující 3 – řazené kolekce členů formuláře `(first[idx], second[idx], third[idx])` pro každý `idx` .</span><span class="sxs-lookup"><span data-stu-id="b8146-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="b8146-117">Pokud se tři pole neshodují, bude výstup, který je kratší než tento počet vstupů.</span><span class="sxs-lookup"><span data-stu-id="b8146-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b8146-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b8146-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="b8146-119">Ne 1</span><span class="sxs-lookup"><span data-stu-id="b8146-119">'T1</span></span>

<span data-ttu-id="b8146-120">Typ prvních prvků pole.</span><span class="sxs-lookup"><span data-stu-id="b8146-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="b8146-121">Ne 2</span><span class="sxs-lookup"><span data-stu-id="b8146-121">'T2</span></span>

<span data-ttu-id="b8146-122">Typ druhých prvků pole.</span><span class="sxs-lookup"><span data-stu-id="b8146-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="b8146-123">Ne 3</span><span class="sxs-lookup"><span data-stu-id="b8146-123">'T3</span></span>

<span data-ttu-id="b8146-124">Typ elementů třetího pole.</span><span class="sxs-lookup"><span data-stu-id="b8146-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8146-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="b8146-125">See Also</span></span>

- [<span data-ttu-id="b8146-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="b8146-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="b8146-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="b8146-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)