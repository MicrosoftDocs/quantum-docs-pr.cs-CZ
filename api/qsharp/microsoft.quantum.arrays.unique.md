---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: 7964d5d41eb68cb05f9414164d69496c1f76eb08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220004"
---
# <a name="unique-function"></a><span data-ttu-id="8b8e4-102">Unique – funkce</span><span class="sxs-lookup"><span data-stu-id="8b8e4-102">Unique function</span></span>

<span data-ttu-id="8b8e4-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8b8e4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8b8e4-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b8e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b8e4-105">Vrátí nové pole, které nemá stejné sousedící prvky.</span><span class="sxs-lookup"><span data-stu-id="8b8e4-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="8b8e4-106">Popis</span><span class="sxs-lookup"><span data-stu-id="8b8e4-106">Description</span></span>

<span data-ttu-id="8b8e4-107">V případě určitého pole prvků a funkce pro otestování rovnosti vrátí tato funkce nové pole, ve kterém je zachováno relativní pořadí prvků, ale všechny sousední prvky, které jsou stejné, jsou filtrovány pouze na jeden prvek.</span><span class="sxs-lookup"><span data-stu-id="8b8e4-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="8b8e4-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="8b8e4-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="8b8e4-109">EQUAL: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8b8e4-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8b8e4-110">Funkce, která porovnává dva prvky, jako jsou `a` považovány za, `b` Pokud `equal(a, b)` je `true` .</span><span class="sxs-lookup"><span data-stu-id="8b8e4-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="8b8e4-111">Array: t []</span><span class="sxs-lookup"><span data-stu-id="8b8e4-111">array : 'T[]</span></span>

<span data-ttu-id="8b8e4-112">Pole, které má být filtrováno pro jedinečné prvky.</span><span class="sxs-lookup"><span data-stu-id="8b8e4-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="8b8e4-113">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="8b8e4-113">Output : 'T[]</span></span>

<span data-ttu-id="8b8e4-114">Pole, které nemá stejné sousedící prvky.</span><span class="sxs-lookup"><span data-stu-id="8b8e4-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8b8e4-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8b8e4-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8b8e4-116">'S</span><span class="sxs-lookup"><span data-stu-id="8b8e4-116">'T</span></span>

<span data-ttu-id="8b8e4-117">Typ každého prvku `array` .</span><span class="sxs-lookup"><span data-stu-id="8b8e4-117">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8b8e4-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="8b8e4-118">Remarks</span></span>

<span data-ttu-id="8b8e4-119">Pokud existuje více prvků, které jsou stejné, ale nejsou vedle sebe, bude ve výstupním poli více výskytů.</span><span class="sxs-lookup"><span data-stu-id="8b8e4-119">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="8b8e4-120">Tuto funkci lze použít společně s `Sorted` k získání pole s celkovými jedinečnými prvky.</span><span class="sxs-lookup"><span data-stu-id="8b8e4-120">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>