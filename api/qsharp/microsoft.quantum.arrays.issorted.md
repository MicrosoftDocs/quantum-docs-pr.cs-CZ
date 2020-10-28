---
uid: Microsoft.Quantum.Arrays.IsSorted
title: Funkce inřazení
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: 330c1f789585f64cf255bc74f8a9c1ccf81b009e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705929"
---
# <a name="issorted-function"></a><span data-ttu-id="21a85-102">Funkce inřazení</span><span class="sxs-lookup"><span data-stu-id="21a85-102">IsSorted function</span></span>

<span data-ttu-id="21a85-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="21a85-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="21a85-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="21a85-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="21a85-105">V případě pole, vrátí, zda je toto pole řazeno tak, jak je definováno danou funkcí porovnání.</span><span class="sxs-lookup"><span data-stu-id="21a85-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="21a85-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="21a85-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="21a85-107">porovnání: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="21a85-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="21a85-108">Funkce, která porovná dva prvky, například, že jsou `a` považovány za menší nebo rovny, `b` Pokud `comparison(a, b)` je `true` .</span><span class="sxs-lookup"><span data-stu-id="21a85-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="21a85-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="21a85-109">array : 'T[]</span></span>

<span data-ttu-id="21a85-110">Pole, které se má zkontrolovat</span><span class="sxs-lookup"><span data-stu-id="21a85-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="21a85-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="21a85-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="21a85-112">`true` Pokud a pouze pokud pro každou dvojici prvků `a` a `b` výskyt `array` v tomto pořadí, `comparison(a, b)` je `true` .</span><span class="sxs-lookup"><span data-stu-id="21a85-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="21a85-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="21a85-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="21a85-114">'S</span><span class="sxs-lookup"><span data-stu-id="21a85-114">'T</span></span>

<span data-ttu-id="21a85-115">Typ každého prvku `array` .</span><span class="sxs-lookup"><span data-stu-id="21a85-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="21a85-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="21a85-116">Remarks</span></span>

<span data-ttu-id="21a85-117">Tato funkce `comparison` je považována za přenositelný, takže pokud `comparison(a, b)` a `comparison(b, c)` , pak `comparison(a, c)` se předpokládá.</span><span class="sxs-lookup"><span data-stu-id="21a85-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="21a85-118">Pokud tato vlastnost není uložena, bude výstup této funkce pravděpodobně nesprávný.</span><span class="sxs-lookup"><span data-stu-id="21a85-118">If this property does not hold, then the output of this function may be incorrect.</span></span>