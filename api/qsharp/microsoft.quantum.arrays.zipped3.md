---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3 – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: 6a4ffaeff8e6248a708ab9f8f9a6ff0c2e9e08d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842178"
---
# <a name="zipped3-function"></a><span data-ttu-id="99db9-102">Zipped3 – funkce</span><span class="sxs-lookup"><span data-stu-id="99db9-102">Zipped3 function</span></span>

<span data-ttu-id="99db9-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="99db9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="99db9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99db9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99db9-105">Zadaná tři pole vrací nové pole tří řazených kolekcí členů, aby každá 3-řazená kolekce členů obsahovala element z každého původního pole.</span><span class="sxs-lookup"><span data-stu-id="99db9-105">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="99db9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="99db9-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="99db9-107">First: t 1 []</span><span class="sxs-lookup"><span data-stu-id="99db9-107">first : 'T1[]</span></span>

<span data-ttu-id="99db9-108">Pole obsahující hodnoty pro první prvek řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="99db9-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="99db9-109">sekundy: t 2 []</span><span class="sxs-lookup"><span data-stu-id="99db9-109">second : 'T2[]</span></span>

<span data-ttu-id="99db9-110">Pole obsahující hodnoty pro druhý prvek každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="99db9-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="99db9-111">třetí: t 3 []</span><span class="sxs-lookup"><span data-stu-id="99db9-111">third : 'T3[]</span></span>

<span data-ttu-id="99db9-112">Pole obsahující hodnoty třetího prvku každé řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="99db9-112">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="99db9-113">Výstup: (ne 1, t 2, t 3) []</span><span class="sxs-lookup"><span data-stu-id="99db9-113">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="99db9-114">Pole obsahující 3 – řazené kolekce členů formuláře `(first[idx], second[idx], third[idx])` pro každý `idx` .</span><span class="sxs-lookup"><span data-stu-id="99db9-114">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="99db9-115">Pokud se tři pole neshodují, bude výstup, který je kratší než tento počet vstupů.</span><span class="sxs-lookup"><span data-stu-id="99db9-115">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="99db9-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="99db9-116">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="99db9-117">Ne 1</span><span class="sxs-lookup"><span data-stu-id="99db9-117">'T1</span></span>

<span data-ttu-id="99db9-118">Typ prvních prvků pole.</span><span class="sxs-lookup"><span data-stu-id="99db9-118">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="99db9-119">Ne 2</span><span class="sxs-lookup"><span data-stu-id="99db9-119">'T2</span></span>

<span data-ttu-id="99db9-120">Typ druhých prvků pole.</span><span class="sxs-lookup"><span data-stu-id="99db9-120">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="99db9-121">Ne 3</span><span class="sxs-lookup"><span data-stu-id="99db9-121">'T3</span></span>

<span data-ttu-id="99db9-122">Typ elementů třetího pole.</span><span class="sxs-lookup"><span data-stu-id="99db9-122">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="99db9-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="99db9-123">See Also</span></span>

- [<span data-ttu-id="99db9-124">Microsoft.Quantum.Arrays.Zipped</span><span class="sxs-lookup"><span data-stu-id="99db9-124">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="99db9-125">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="99db9-125">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)