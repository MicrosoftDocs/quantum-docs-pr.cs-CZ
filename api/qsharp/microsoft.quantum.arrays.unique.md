---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850909"
---
# <a name="unique-function"></a><span data-ttu-id="00afd-102">Unique – funkce</span><span class="sxs-lookup"><span data-stu-id="00afd-102">Unique function</span></span>

<span data-ttu-id="00afd-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="00afd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="00afd-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="00afd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="00afd-105">Vrátí nové pole, které nemá stejné sousedící prvky.</span><span class="sxs-lookup"><span data-stu-id="00afd-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="00afd-106">Popis</span><span class="sxs-lookup"><span data-stu-id="00afd-106">Description</span></span>

<span data-ttu-id="00afd-107">V případě určitého pole prvků a funkce pro otestování rovnosti vrátí tato funkce nové pole, ve kterém je zachováno relativní pořadí prvků, ale všechny sousední prvky, které jsou stejné, jsou filtrovány pouze na jeden prvek.</span><span class="sxs-lookup"><span data-stu-id="00afd-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="00afd-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="00afd-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="00afd-109">EQUAL: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="00afd-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="00afd-110">Funkce, která porovnává dva prvky, jako jsou `a` považovány za, `b` Pokud `equal(a, b)` je `true` .</span><span class="sxs-lookup"><span data-stu-id="00afd-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="00afd-111">Array: t []</span><span class="sxs-lookup"><span data-stu-id="00afd-111">array : 'T[]</span></span>

<span data-ttu-id="00afd-112">Pole, které má být filtrováno pro jedinečné prvky.</span><span class="sxs-lookup"><span data-stu-id="00afd-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="00afd-113">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="00afd-113">Output : 'T[]</span></span>

<span data-ttu-id="00afd-114">Pole, které nemá stejné sousedící prvky.</span><span class="sxs-lookup"><span data-stu-id="00afd-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="00afd-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="00afd-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="00afd-116">'S</span><span class="sxs-lookup"><span data-stu-id="00afd-116">'T</span></span>

<span data-ttu-id="00afd-117">Typ každého prvku `array` .</span><span class="sxs-lookup"><span data-stu-id="00afd-117">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="00afd-118">Příklad</span><span class="sxs-lookup"><span data-stu-id="00afd-118">Example</span></span>

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a><span data-ttu-id="00afd-119">Poznámky</span><span class="sxs-lookup"><span data-stu-id="00afd-119">Remarks</span></span>

<span data-ttu-id="00afd-120">Pokud existuje více prvků, které jsou stejné, ale nejsou vedle sebe, bude ve výstupním poli více výskytů.</span><span class="sxs-lookup"><span data-stu-id="00afd-120">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="00afd-121">Tuto funkci lze použít společně s `Sorted` k získání pole s celkovými jedinečnými prvky.</span><span class="sxs-lookup"><span data-stu-id="00afd-121">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>