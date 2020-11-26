---
uid: Microsoft.Quantum.Arrays.Sorted
title: Seřazená funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: bd8b869e03c7f4687c456a944e07a811ae0d2ce2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220225"
---
# <a name="sorted-function"></a><span data-ttu-id="b1fa7-102">Seřazená funkce</span><span class="sxs-lookup"><span data-stu-id="b1fa7-102">Sorted function</span></span>

<span data-ttu-id="b1fa7-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b1fa7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b1fa7-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1fa7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1fa7-105">Předanému poli vrátí prvky tohoto pole seřazené podle dané funkce porovnání.</span><span class="sxs-lookup"><span data-stu-id="b1fa7-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b1fa7-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b1fa7-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="b1fa7-107">porovnání: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b1fa7-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b1fa7-108">Funkce, která porovná dva prvky, například, že jsou `a` považovány za menší nebo rovny, `b` Pokud `comparison(a, b)` je `true` .</span><span class="sxs-lookup"><span data-stu-id="b1fa7-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="b1fa7-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="b1fa7-109">array : 'T[]</span></span>

<span data-ttu-id="b1fa7-110">Pole, které má být seřazeno.</span><span class="sxs-lookup"><span data-stu-id="b1fa7-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="b1fa7-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="b1fa7-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b1fa7-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b1fa7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b1fa7-113">'S</span><span class="sxs-lookup"><span data-stu-id="b1fa7-113">'T</span></span>

<span data-ttu-id="b1fa7-114">Typ každého prvku `array` .</span><span class="sxs-lookup"><span data-stu-id="b1fa7-114">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1fa7-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b1fa7-115">Remarks</span></span>

<span data-ttu-id="b1fa7-116">Tato funkce `comparison` je považována za přenositelný, takže pokud `comparison(a, b)` a `comparison(b, c)` , pak `comparison(a, c)` se předpokládá.</span><span class="sxs-lookup"><span data-stu-id="b1fa7-116">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="b1fa7-117">Pokud tato vlastnost není uložena, bude výstup této funkce pravděpodobně nesprávný.</span><span class="sxs-lookup"><span data-stu-id="b1fa7-117">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="b1fa7-118">Vzhledem k tomu, že je to funkce, jsou výsledky zcela deterministickáy i v případě, že se dva prvky považují za stejné jako v rámci `comparison` `comparison(a, b)` a `comparison(b, a)` `true` .</span><span class="sxs-lookup"><span data-stu-id="b1fa7-118">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="b1fa7-119">Konkrétně je zaručeno, že řazení prováděné touto funkcí je stabilní, aby v případě, že dva prvky `a` a `b` výskyty v tomto pořadí v `array` a jsou považovány za stejné `comparison` , pak se `a` zobrazí také před `b` ve výstupu.</span><span class="sxs-lookup"><span data-stu-id="b1fa7-119">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="b1fa7-120">Příklad:</span><span class="sxs-lookup"><span data-stu-id="b1fa7-120">For example:</span></span>

```Q#
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```