---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Funkce unzip
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845372"
---
# <a name="unzipped-function"></a><span data-ttu-id="efbc9-102">Funkce unzip</span><span class="sxs-lookup"><span data-stu-id="efbc9-102">Unzipped function</span></span>

<span data-ttu-id="efbc9-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="efbc9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="efbc9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="efbc9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="efbc9-105">V případě pole se dvěma řazenými kolekcemi členů vrátí řazenou kolekci členů dvou polí, z nichž každý obsahuje prvky pro vstupní pole.</span><span class="sxs-lookup"><span data-stu-id="efbc9-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="efbc9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="efbc9-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="efbc9-107">Šipka: (t, ' U) []</span><span class="sxs-lookup"><span data-stu-id="efbc9-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="efbc9-108">Pole obsahující 2 – řazené kolekce členů</span><span class="sxs-lookup"><span data-stu-id="efbc9-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="efbc9-109">Výstup: (ne [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="efbc9-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="efbc9-110">Dvě pole, první obsahující všechny první prvky vstupních řazených kolekcí členů, druhý, který obsahuje všechny druhé prvky vstupních řazených kolekcí členů.</span><span class="sxs-lookup"><span data-stu-id="efbc9-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="efbc9-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="efbc9-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="efbc9-112">'S</span><span class="sxs-lookup"><span data-stu-id="efbc9-112">'T</span></span>

<span data-ttu-id="efbc9-113">Typ prvního prvku v každé řazené kolekci členů</span><span class="sxs-lookup"><span data-stu-id="efbc9-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="efbc9-114">U</span><span class="sxs-lookup"><span data-stu-id="efbc9-114">'U</span></span>

<span data-ttu-id="efbc9-115">Typ druhého prvku v každé řazené kolekci členů</span><span class="sxs-lookup"><span data-stu-id="efbc9-115">The type of the second element in each tuple</span></span>

## <a name="example"></a><span data-ttu-id="efbc9-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="efbc9-116">Example</span></span>

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a><span data-ttu-id="efbc9-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="efbc9-117">See Also</span></span>

- [<span data-ttu-id="efbc9-118">Microsoft.Quantum.Arrays.Zipped</span><span class="sxs-lookup"><span data-stu-id="efbc9-118">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)