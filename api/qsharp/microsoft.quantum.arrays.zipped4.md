---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Zipped4 – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d5ee10ac9776383e75bc16a5c003a8b1a65c5698
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219630"
---
# <a name="zipped4-function"></a><span data-ttu-id="f77fc-102">Zipped4 – funkce</span><span class="sxs-lookup"><span data-stu-id="f77fc-102">Zipped4 function</span></span>

<span data-ttu-id="f77fc-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f77fc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f77fc-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f77fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f77fc-105">U čtyř polí vrátí nové pole se 4 řazenými kolekcemi členů tak, aby každá 4 řazená kolekce členů obsahovala element z každého původního pole.</span><span class="sxs-lookup"><span data-stu-id="f77fc-105">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="f77fc-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f77fc-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="f77fc-107">First: t 1 []</span><span class="sxs-lookup"><span data-stu-id="f77fc-107">first : 'T1[]</span></span>

<span data-ttu-id="f77fc-108">Pole obsahující hodnoty pro první prvek řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="f77fc-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="f77fc-109">sekundy: t 2 []</span><span class="sxs-lookup"><span data-stu-id="f77fc-109">second : 'T2[]</span></span>

<span data-ttu-id="f77fc-110">Pole obsahující hodnoty pro druhý prvek každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="f77fc-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="f77fc-111">třetí: t 3 []</span><span class="sxs-lookup"><span data-stu-id="f77fc-111">third : 'T3[]</span></span>

<span data-ttu-id="f77fc-112">Pole obsahující hodnoty třetího prvku každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="f77fc-112">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="f77fc-113">čtvrté: t 4 []</span><span class="sxs-lookup"><span data-stu-id="f77fc-113">fourth : 'T4[]</span></span>

<span data-ttu-id="f77fc-114">Pole obsahující hodnoty pro čtvrtý prvek každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="f77fc-114">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="f77fc-115">Výstup: (ne 1, t 2, t 3, t 4) []</span><span class="sxs-lookup"><span data-stu-id="f77fc-115">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="f77fc-116">Pole obsahující 4 – řazené kolekce členů formuláře `(first[idx], second[idx], third[idx], fourth[idx])` pro každý `idx` .</span><span class="sxs-lookup"><span data-stu-id="f77fc-116">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="f77fc-117">Pokud se čtyři pole neshodují, bude výstup, který je kratší než tento počet vstupů.</span><span class="sxs-lookup"><span data-stu-id="f77fc-117">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f77fc-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f77fc-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="f77fc-119">Ne 1</span><span class="sxs-lookup"><span data-stu-id="f77fc-119">'T1</span></span>

<span data-ttu-id="f77fc-120">Typ prvních prvků pole.</span><span class="sxs-lookup"><span data-stu-id="f77fc-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="f77fc-121">Ne 2</span><span class="sxs-lookup"><span data-stu-id="f77fc-121">'T2</span></span>

<span data-ttu-id="f77fc-122">Typ druhých prvků pole.</span><span class="sxs-lookup"><span data-stu-id="f77fc-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="f77fc-123">Ne 3</span><span class="sxs-lookup"><span data-stu-id="f77fc-123">'T3</span></span>

<span data-ttu-id="f77fc-124">Typ elementů třetího pole.</span><span class="sxs-lookup"><span data-stu-id="f77fc-124">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="f77fc-125">NE4</span><span class="sxs-lookup"><span data-stu-id="f77fc-125">'T4</span></span>

<span data-ttu-id="f77fc-126">Typ čtvrté prvky pole.</span><span class="sxs-lookup"><span data-stu-id="f77fc-126">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="f77fc-127">Viz také</span><span class="sxs-lookup"><span data-stu-id="f77fc-127">See Also</span></span>

- [<span data-ttu-id="f77fc-128">Microsoft.Quantum.Arrays.Zipped</span><span class="sxs-lookup"><span data-stu-id="f77fc-128">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="f77fc-129">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="f77fc-129">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)