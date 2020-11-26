---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Funkce unzip
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219953"
---
# <a name="unzipped-function"></a><span data-ttu-id="e37f2-102">Funkce unzip</span><span class="sxs-lookup"><span data-stu-id="e37f2-102">Unzipped function</span></span>

<span data-ttu-id="e37f2-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e37f2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e37f2-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e37f2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e37f2-105">V případě pole se dvěma řazenými kolekcemi členů vrátí řazenou kolekci členů dvou polí, z nichž každý obsahuje prvky pro vstupní pole.</span><span class="sxs-lookup"><span data-stu-id="e37f2-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="e37f2-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e37f2-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="e37f2-107">Šipka: (t, ' U) []</span><span class="sxs-lookup"><span data-stu-id="e37f2-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="e37f2-108">Pole obsahující 2 – řazené kolekce členů</span><span class="sxs-lookup"><span data-stu-id="e37f2-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="e37f2-109">Výstup: (ne [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="e37f2-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="e37f2-110">Dvě pole, první obsahující všechny první prvky vstupních řazených kolekcí členů, druhý, který obsahuje všechny druhé prvky vstupních řazených kolekcí členů.</span><span class="sxs-lookup"><span data-stu-id="e37f2-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e37f2-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e37f2-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e37f2-112">'S</span><span class="sxs-lookup"><span data-stu-id="e37f2-112">'T</span></span>

<span data-ttu-id="e37f2-113">Typ prvního prvku v každé řazené kolekci členů</span><span class="sxs-lookup"><span data-stu-id="e37f2-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="e37f2-114">U</span><span class="sxs-lookup"><span data-stu-id="e37f2-114">'U</span></span>

<span data-ttu-id="e37f2-115">Typ druhého prvku v každé řazené kolekci členů</span><span class="sxs-lookup"><span data-stu-id="e37f2-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="e37f2-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="e37f2-116">See Also</span></span>

- [<span data-ttu-id="e37f2-117">Microsoft.Quantum.Arrays.Zipped</span><span class="sxs-lookup"><span data-stu-id="e37f2-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)