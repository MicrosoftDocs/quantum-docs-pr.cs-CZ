---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3 – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: 37fda4082a46870270414649f807659fa561962b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219681"
---
# <a name="zipped3-function"></a><span data-ttu-id="b525a-102">Zipped3 – funkce</span><span class="sxs-lookup"><span data-stu-id="b525a-102">Zipped3 function</span></span>

<span data-ttu-id="b525a-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b525a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b525a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b525a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b525a-105">Zadaná tři pole vrací nové pole tří řazených kolekcí členů, aby každá 3-řazená kolekce členů obsahovala element z každého původního pole.</span><span class="sxs-lookup"><span data-stu-id="b525a-105">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="b525a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b525a-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="b525a-107">First: t 1 []</span><span class="sxs-lookup"><span data-stu-id="b525a-107">first : 'T1[]</span></span>

<span data-ttu-id="b525a-108">Pole obsahující hodnoty pro první prvek řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="b525a-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="b525a-109">sekundy: t 2 []</span><span class="sxs-lookup"><span data-stu-id="b525a-109">second : 'T2[]</span></span>

<span data-ttu-id="b525a-110">Pole obsahující hodnoty pro druhý prvek každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="b525a-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="b525a-111">třetí: t 3 []</span><span class="sxs-lookup"><span data-stu-id="b525a-111">third : 'T3[]</span></span>

<span data-ttu-id="b525a-112">Pole obsahující hodnoty třetího prvku každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="b525a-112">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="b525a-113">Výstup: (ne 1, t 2, t 3) []</span><span class="sxs-lookup"><span data-stu-id="b525a-113">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="b525a-114">Pole obsahující 3 – řazené kolekce členů formuláře `(first[idx], second[idx], third[idx])` pro každý `idx` .</span><span class="sxs-lookup"><span data-stu-id="b525a-114">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="b525a-115">Pokud se tři pole neshodují, bude výstup, který je kratší než tento počet vstupů.</span><span class="sxs-lookup"><span data-stu-id="b525a-115">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b525a-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b525a-116">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="b525a-117">Ne 1</span><span class="sxs-lookup"><span data-stu-id="b525a-117">'T1</span></span>

<span data-ttu-id="b525a-118">Typ prvních prvků pole.</span><span class="sxs-lookup"><span data-stu-id="b525a-118">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="b525a-119">Ne 2</span><span class="sxs-lookup"><span data-stu-id="b525a-119">'T2</span></span>

<span data-ttu-id="b525a-120">Typ druhých prvků pole.</span><span class="sxs-lookup"><span data-stu-id="b525a-120">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="b525a-121">Ne 3</span><span class="sxs-lookup"><span data-stu-id="b525a-121">'T3</span></span>

<span data-ttu-id="b525a-122">Typ elementů třetího pole.</span><span class="sxs-lookup"><span data-stu-id="b525a-122">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="b525a-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="b525a-123">See Also</span></span>

- [<span data-ttu-id="b525a-124">Microsoft.Quantum.Arrays.Zipped</span><span class="sxs-lookup"><span data-stu-id="b525a-124">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="b525a-125">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="b525a-125">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)