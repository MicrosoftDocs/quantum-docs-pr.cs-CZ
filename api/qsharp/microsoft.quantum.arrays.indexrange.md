---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845783"
---
# <a name="indexrange-function"></a><span data-ttu-id="ed2b8-102">IndexRange – funkce</span><span class="sxs-lookup"><span data-stu-id="ed2b8-102">IndexRange function</span></span>

<span data-ttu-id="ed2b8-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ed2b8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ed2b8-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ed2b8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ed2b8-105">V poli, vrátí rozsah v rámci indexů tohoto pole, který je vhodný pro použití ve smyčce for.</span><span class="sxs-lookup"><span data-stu-id="ed2b8-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="ed2b8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ed2b8-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="ed2b8-107">Array: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="ed2b8-107">array : 'TElement[]</span></span>

<span data-ttu-id="ed2b8-108">Pole, pro které by měl být vrácen rozsah indexů.</span><span class="sxs-lookup"><span data-stu-id="ed2b8-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="ed2b8-109">Výstup: [Rozsah](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="ed2b8-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="ed2b8-110">Rozsah ve všech indexech pole.</span><span class="sxs-lookup"><span data-stu-id="ed2b8-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ed2b8-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ed2b8-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="ed2b8-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="ed2b8-112">'TElement</span></span>

<span data-ttu-id="ed2b8-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="ed2b8-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="ed2b8-114">Příklad</span><span class="sxs-lookup"><span data-stu-id="ed2b8-114">Example</span></span>

<span data-ttu-id="ed2b8-115">Následující `for` smyčky jsou ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="ed2b8-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```