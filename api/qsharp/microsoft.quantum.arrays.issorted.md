---
uid: Microsoft.Quantum.Arrays.IsSorted
title: Funkce inřazení
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: a5916b5cbf36e1b6c421a81e04016a333e2b5be7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845735"
---
# <a name="issorted-function"></a><span data-ttu-id="93353-102">Funkce inřazení</span><span class="sxs-lookup"><span data-stu-id="93353-102">IsSorted function</span></span>

<span data-ttu-id="93353-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="93353-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="93353-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="93353-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="93353-105">V případě pole, vrátí, zda je toto pole řazeno tak, jak je definováno danou funkcí porovnání.</span><span class="sxs-lookup"><span data-stu-id="93353-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="93353-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="93353-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="93353-107">porovnání: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="93353-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="93353-108">Funkce, která porovná dva prvky, například, že jsou `a` považovány za menší nebo rovny, `b` Pokud `comparison(a, b)` je `true` .</span><span class="sxs-lookup"><span data-stu-id="93353-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="93353-109">Array: t []</span><span class="sxs-lookup"><span data-stu-id="93353-109">array : 'T[]</span></span>

<span data-ttu-id="93353-110">Pole, které se má zkontrolovat</span><span class="sxs-lookup"><span data-stu-id="93353-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="93353-111">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="93353-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="93353-112">`true` Pokud a pouze pokud pro každou dvojici prvků `a` a `b` výskyt `array` v tomto pořadí, `comparison(a, b)` je `true` .</span><span class="sxs-lookup"><span data-stu-id="93353-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="93353-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="93353-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="93353-114">'S</span><span class="sxs-lookup"><span data-stu-id="93353-114">'T</span></span>

<span data-ttu-id="93353-115">Typ každého prvku `array` .</span><span class="sxs-lookup"><span data-stu-id="93353-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="93353-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="93353-116">Remarks</span></span>

<span data-ttu-id="93353-117">Tato funkce `comparison` je považována za přenositelný, takže pokud `comparison(a, b)` a `comparison(b, c)` , pak `comparison(a, c)` se předpokládá.</span><span class="sxs-lookup"><span data-stu-id="93353-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="93353-118">Pokud tato vlastnost není uložena, bude výstup této funkce pravděpodobně nesprávný.</span><span class="sxs-lookup"><span data-stu-id="93353-118">If this property does not hold, then the output of this function may be incorrect.</span></span>