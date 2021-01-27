---
uid: Microsoft.Quantum.Arrays.Sorted
title: Seřazená funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845448"
---
# <a name="sorted-function"></a><span data-ttu-id="acf03-102">Seřazená funkce</span><span class="sxs-lookup"><span data-stu-id="acf03-102">Sorted function</span></span>

<span data-ttu-id="acf03-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="acf03-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="acf03-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="acf03-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="acf03-105">Předanému poli vrátí prvky tohoto pole seřazené podle dané funkce porovnání.</span><span class="sxs-lookup"><span data-stu-id="acf03-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="acf03-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="acf03-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="acf03-107">porovnání: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="acf03-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="acf03-108">Funkce, která porovná dva prvky, například, že jsou `a` považovány za menší nebo rovny, `b` Pokud `comparison(a, b)` je `true` .</span><span class="sxs-lookup"><span data-stu-id="acf03-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="acf03-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="acf03-109">array : 'T[]</span></span>

<span data-ttu-id="acf03-110">Pole, které má být seřazeno.</span><span class="sxs-lookup"><span data-stu-id="acf03-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="acf03-111">Výstup: t []</span><span class="sxs-lookup"><span data-stu-id="acf03-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="acf03-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="acf03-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="acf03-113">'S</span><span class="sxs-lookup"><span data-stu-id="acf03-113">'T</span></span>

<span data-ttu-id="acf03-114">Typ každého prvku `array` .</span><span class="sxs-lookup"><span data-stu-id="acf03-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="acf03-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="acf03-115">Example</span></span>

<span data-ttu-id="acf03-116">Následující fragment kódu seřadí pole celých čísel, která se mají objevit ve vzestupném pořadí:</span><span class="sxs-lookup"><span data-stu-id="acf03-116">The following snippet sorts an array of integers to occur in ascending order:</span></span>

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a><span data-ttu-id="acf03-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="acf03-117">Remarks</span></span>

<span data-ttu-id="acf03-118">Tato funkce `comparison` je považována za přenositelný, takže pokud `comparison(a, b)` a `comparison(b, c)` , pak `comparison(a, c)` se předpokládá.</span><span class="sxs-lookup"><span data-stu-id="acf03-118">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="acf03-119">Pokud tato vlastnost není uložena, bude výstup této funkce pravděpodobně nesprávný.</span><span class="sxs-lookup"><span data-stu-id="acf03-119">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="acf03-120">Vzhledem k tomu, že je to funkce, jsou výsledky zcela deterministickáy i v případě, že se dva prvky považují za stejné jako v rámci `comparison` `comparison(a, b)` a `comparison(b, a)` `true` .</span><span class="sxs-lookup"><span data-stu-id="acf03-120">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="acf03-121">Konkrétně je zaručeno, že řazení prováděné touto funkcí je stabilní, aby v případě, že dva prvky `a` a `b` výskyty v tomto pořadí v `array` a jsou považovány za stejné `comparison` , pak se `a` zobrazí také před `b` ve výstupu.</span><span class="sxs-lookup"><span data-stu-id="acf03-121">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="acf03-122">Příklad:</span><span class="sxs-lookup"><span data-stu-id="acf03-122">For example:</span></span>

```qsharp
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