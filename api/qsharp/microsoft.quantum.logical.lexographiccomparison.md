---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: 4d8596c52b0fc8082a2b766d95d4052a4964b8b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197580"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="91337-102">LexographicComparison – funkce</span><span class="sxs-lookup"><span data-stu-id="91337-102">LexographicComparison function</span></span>

<span data-ttu-id="91337-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="91337-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="91337-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91337-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91337-105">S ohledem na funkci porovnání vrátí novou funkci, která lexographically porovnává dvě pole.</span><span class="sxs-lookup"><span data-stu-id="91337-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="91337-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="91337-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="91337-107">elementComparison: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="91337-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="91337-108">Funkce, která porovná dva prvky `x` a `y` a vrátí, pokud `x` je menší nebo rovno `y` .</span><span class="sxs-lookup"><span data-stu-id="91337-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="91337-109">Výstup: (ne [], t [])-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="91337-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="91337-110">Funkce, která porovnává dvě pole `xs` a `ys` a vrátí, pokud se `xs` vyskytnou `ys` v pořadí lexographical nebo se rovná.</span><span class="sxs-lookup"><span data-stu-id="91337-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="91337-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="91337-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="91337-112">'S</span><span class="sxs-lookup"><span data-stu-id="91337-112">'T</span></span>

<span data-ttu-id="91337-113">Typ prvků pole, které jsou porovnány.</span><span class="sxs-lookup"><span data-stu-id="91337-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="91337-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="91337-114">Remarks</span></span>

<span data-ttu-id="91337-115">Porovnání lexographic mezi dvěma poli `xs` a `ys` je definováno následujícím postupem.</span><span class="sxs-lookup"><span data-stu-id="91337-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="91337-116">Říkáme, že dva prvky `x` a `y` jsou ekvivalentní, pokud `elementComparison(x, y)` a `elementComparison(y, x)` jsou obě true.</span><span class="sxs-lookup"><span data-stu-id="91337-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="91337-117">Obě pole jsou porovnány elementem po prvku, dokud první dvojice prvků, které nejsou ekvivalentní.</span><span class="sxs-lookup"><span data-stu-id="91337-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="91337-118">Pole obsahující prvek, který nastane jako první v závislosti na, `elementComparison` se říká, že se má objevit jako první v lexographical řazení.</span><span class="sxs-lookup"><span data-stu-id="91337-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="91337-119">Pokud nejsou nalezeny žádné neekvivalentní prvky a jedno pole je delší než druhý, tak kratší pole se říká, že se má objevit jako první.</span><span class="sxs-lookup"><span data-stu-id="91337-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="91337-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="91337-120">See Also</span></span>

- [<span data-ttu-id="91337-121">Microsoft. Forms. Arrays. tříděné</span><span class="sxs-lookup"><span data-stu-id="91337-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)