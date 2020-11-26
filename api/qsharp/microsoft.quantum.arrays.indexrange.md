---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220939"
---
# <a name="indexrange-function"></a><span data-ttu-id="f0bae-102">IndexRange – funkce</span><span class="sxs-lookup"><span data-stu-id="f0bae-102">IndexRange function</span></span>

<span data-ttu-id="f0bae-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f0bae-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f0bae-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f0bae-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f0bae-105">V poli, vrátí rozsah v rámci indexů tohoto pole, který je vhodný pro použití ve smyčce for.</span><span class="sxs-lookup"><span data-stu-id="f0bae-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="f0bae-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f0bae-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="f0bae-107">Array: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="f0bae-107">array : 'TElement[]</span></span>

<span data-ttu-id="f0bae-108">Pole, pro které by měl být vrácen rozsah indexů.</span><span class="sxs-lookup"><span data-stu-id="f0bae-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="f0bae-109">Výstup: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="f0bae-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="f0bae-110">Rozsah ve všech indexech pole.</span><span class="sxs-lookup"><span data-stu-id="f0bae-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f0bae-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f0bae-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="f0bae-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="f0bae-112">'TElement</span></span>

<span data-ttu-id="f0bae-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="f0bae-113">The type of elements of the array.</span></span>