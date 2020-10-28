---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: f0b68974a0ea26907b58971e4fa4b1f06f5714d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697276"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="2a40c-102">LexographicComparison – funkce</span><span class="sxs-lookup"><span data-stu-id="2a40c-102">LexographicComparison function</span></span>

<span data-ttu-id="2a40c-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2a40c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2a40c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a40c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a40c-105">S ohledem na funkci porovnání vrátí novou funkci, která lexographically porovnává dvě pole.</span><span class="sxs-lookup"><span data-stu-id="2a40c-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="2a40c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2a40c-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="2a40c-107">elementComparison: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2a40c-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2a40c-108">Funkce, která porovná dva prvky `x` a `y` a vrátí, pokud `x` je menší nebo rovno `y` .</span><span class="sxs-lookup"><span data-stu-id="2a40c-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="2a40c-109">Výstup: (ne [], t [])-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2a40c-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2a40c-110">Funkce, která porovnává dvě pole `xs` a `ys` a vrátí, pokud se `xs` vyskytnou `ys` v pořadí lexographical nebo se rovná.</span><span class="sxs-lookup"><span data-stu-id="2a40c-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2a40c-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2a40c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2a40c-112">'S</span><span class="sxs-lookup"><span data-stu-id="2a40c-112">'T</span></span>

<span data-ttu-id="2a40c-113">Typ prvků pole, které jsou porovnány.</span><span class="sxs-lookup"><span data-stu-id="2a40c-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a40c-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2a40c-114">Remarks</span></span>

<span data-ttu-id="2a40c-115">Porovnání lexographic mezi dvěma poli `xs` a `ys` je definováno následujícím postupem.</span><span class="sxs-lookup"><span data-stu-id="2a40c-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="2a40c-116">Říkáme, že dva prvky `x` a `y` jsou ekvivalentní, pokud `elementComparison(x, y)` a `elementComparison(y, x)` jsou obě true.</span><span class="sxs-lookup"><span data-stu-id="2a40c-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="2a40c-117">Obě pole jsou porovnány elementem po prvku, dokud první dvojice prvků, které nejsou ekvivalentní.</span><span class="sxs-lookup"><span data-stu-id="2a40c-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="2a40c-118">Pole obsahující prvek, který nastane jako první v závislosti na, `elementComparison` se říká, že se má objevit jako první v lexographical řazení.</span><span class="sxs-lookup"><span data-stu-id="2a40c-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="2a40c-119">Pokud nejsou nalezeny žádné neekvivalentní prvky a jedno pole je delší než druhý, tak kratší pole se říká, že se má objevit jako první.</span><span class="sxs-lookup"><span data-stu-id="2a40c-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a40c-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="2a40c-120">See Also</span></span>

- [<span data-ttu-id="2a40c-121">Microsoft. Forms. Arrays. tříděné</span><span class="sxs-lookup"><span data-stu-id="2a40c-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)