---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: c9dd07ddc63f1d75952d3841997eed0f78e054b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219783"
---
# <a name="zip4-function"></a><span data-ttu-id="34067-102">Zip4 – funkce</span><span class="sxs-lookup"><span data-stu-id="34067-102">Zip4 function</span></span>

<span data-ttu-id="34067-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="34067-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="34067-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34067-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="34067-105">Zip4 se už nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="34067-105">Zip4 has been deprecated.</span></span> <span data-ttu-id="34067-106"><xref:Microsoft.Quantum.Arrays.Zipped4>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="34067-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.</span></span>

<span data-ttu-id="34067-107">U čtyř polí vrátí nové pole se 4 řazenými kolekcemi členů tak, aby každá 4 řazená kolekce členů obsahovala element z každého původního pole.</span><span class="sxs-lookup"><span data-stu-id="34067-107">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="34067-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="34067-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="34067-109">First: t 1 []</span><span class="sxs-lookup"><span data-stu-id="34067-109">first : 'T1[]</span></span>

<span data-ttu-id="34067-110">Pole obsahující hodnoty pro první prvek řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="34067-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="34067-111">sekundy: t 2 []</span><span class="sxs-lookup"><span data-stu-id="34067-111">second : 'T2[]</span></span>

<span data-ttu-id="34067-112">Pole obsahující hodnoty pro druhý prvek každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="34067-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="34067-113">třetí: t 3 []</span><span class="sxs-lookup"><span data-stu-id="34067-113">third : 'T3[]</span></span>

<span data-ttu-id="34067-114">Pole obsahující hodnoty třetího prvku každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="34067-114">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="34067-115">čtvrté: t 4 []</span><span class="sxs-lookup"><span data-stu-id="34067-115">fourth : 'T4[]</span></span>

<span data-ttu-id="34067-116">Pole obsahující hodnoty pro čtvrtý prvek každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="34067-116">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="34067-117">Výstup: (ne 1, t 2, t 3, t 4) []</span><span class="sxs-lookup"><span data-stu-id="34067-117">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="34067-118">Pole obsahující 4 – řazené kolekce členů formuláře `(first[idx], second[idx], third[idx], fourth[idx])` pro každý `idx` .</span><span class="sxs-lookup"><span data-stu-id="34067-118">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="34067-119">Pokud se čtyři pole neshodují, bude výstup, který je kratší než tento počet vstupů.</span><span class="sxs-lookup"><span data-stu-id="34067-119">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="34067-120">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="34067-120">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="34067-121">Ne 1</span><span class="sxs-lookup"><span data-stu-id="34067-121">'T1</span></span>

<span data-ttu-id="34067-122">Typ prvních prvků pole.</span><span class="sxs-lookup"><span data-stu-id="34067-122">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="34067-123">Ne 2</span><span class="sxs-lookup"><span data-stu-id="34067-123">'T2</span></span>

<span data-ttu-id="34067-124">Typ druhých prvků pole.</span><span class="sxs-lookup"><span data-stu-id="34067-124">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="34067-125">Ne 3</span><span class="sxs-lookup"><span data-stu-id="34067-125">'T3</span></span>

<span data-ttu-id="34067-126">Typ elementů třetího pole.</span><span class="sxs-lookup"><span data-stu-id="34067-126">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="34067-127">NE4</span><span class="sxs-lookup"><span data-stu-id="34067-127">'T4</span></span>

<span data-ttu-id="34067-128">Typ čtvrté prvky pole.</span><span class="sxs-lookup"><span data-stu-id="34067-128">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="34067-129">Viz také</span><span class="sxs-lookup"><span data-stu-id="34067-129">See Also</span></span>

- [<span data-ttu-id="34067-130">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="34067-130">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="34067-131">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="34067-131">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)