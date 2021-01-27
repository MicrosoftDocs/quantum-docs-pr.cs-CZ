---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: a154e5becba4dae762596a3fc1b268855520fa1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850967"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="6ac19-102">SquareArrayFact – funkce</span><span class="sxs-lookup"><span data-stu-id="6ac19-102">SquareArrayFact function</span></span>

<span data-ttu-id="6ac19-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6ac19-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6ac19-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6ac19-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6ac19-105">Představuje podmínku, že dvojrozměrné pole má čtvercový tvar.</span><span class="sxs-lookup"><span data-stu-id="6ac19-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="6ac19-106">Popis</span><span class="sxs-lookup"><span data-stu-id="6ac19-106">Description</span></span>

<span data-ttu-id="6ac19-107">Tato funkce vyhodnotí, že každý řádek v poli má tolik prvků, jako jsou řádky (elementy) v poli.</span><span class="sxs-lookup"><span data-stu-id="6ac19-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="6ac19-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="6ac19-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="6ac19-109">Array: t [] []</span><span class="sxs-lookup"><span data-stu-id="6ac19-109">array : 'T[][]</span></span>

<span data-ttu-id="6ac19-110">Dvojrozměrné pole prvků</span><span class="sxs-lookup"><span data-stu-id="6ac19-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="6ac19-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6ac19-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="6ac19-112">Zpráva, která se má vytisknout, pokud pole není čtvercové pole</span><span class="sxs-lookup"><span data-stu-id="6ac19-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ac19-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ac19-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6ac19-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6ac19-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6ac19-115">'S</span><span class="sxs-lookup"><span data-stu-id="6ac19-115">'T</span></span>

<span data-ttu-id="6ac19-116">Typ každého prvku `array` .</span><span class="sxs-lookup"><span data-stu-id="6ac19-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="6ac19-117">Příklad</span><span class="sxs-lookup"><span data-stu-id="6ac19-117">Example</span></span>

```qsharp
SquareArrayFact([[1, 2], [3, 4]], "Array is not a square");       // okay
SquareArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not a square"); // will fail
SquareArrayFact([[1, 2], [3, 4, 5]], "Array is not a square");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="6ac19-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="6ac19-118">See Also</span></span>

- [<span data-ttu-id="6ac19-119">Microsoft. Forms. Arrays. RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="6ac19-119">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)