---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Funkce výčtu
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848127"
---
# <a name="enumerated-function"></a><span data-ttu-id="c09d9-102">Funkce výčtu</span><span class="sxs-lookup"><span data-stu-id="c09d9-102">Enumerated function</span></span>

<span data-ttu-id="c09d9-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c09d9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c09d9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c09d9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c09d9-105">V případě pole, vrátí nové pole obsahující prvky původního pole spolu s indexy každého prvku.</span><span class="sxs-lookup"><span data-stu-id="c09d9-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="c09d9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c09d9-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="c09d9-107">Array: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="c09d9-107">array : 'TElement[]</span></span>

<span data-ttu-id="c09d9-108">Pole, jehož prvky mají být vyčísleny.</span><span class="sxs-lookup"><span data-stu-id="c09d9-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="c09d9-109">Výstup: ([int](xref:microsoft.quantum.lang-ref.int), ' TElement) []</span><span class="sxs-lookup"><span data-stu-id="c09d9-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="c09d9-110">Nové pole obsahující prvky původního pole spolu s jejich indexy.</span><span class="sxs-lookup"><span data-stu-id="c09d9-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c09d9-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c09d9-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="c09d9-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="c09d9-112">'TElement</span></span>

<span data-ttu-id="c09d9-113">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="c09d9-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="c09d9-114">Příklad</span><span class="sxs-lookup"><span data-stu-id="c09d9-114">Example</span></span>

<span data-ttu-id="c09d9-115">Následující `for` smyčky jsou ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="c09d9-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```