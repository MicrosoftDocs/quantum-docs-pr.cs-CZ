---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: 8cf6b85da6e8fee7fc255a173753a6468d8134b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845491"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="22bdc-102">RectangularArrayFact – funkce</span><span class="sxs-lookup"><span data-stu-id="22bdc-102">RectangularArrayFact function</span></span>

<span data-ttu-id="22bdc-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="22bdc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="22bdc-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22bdc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="22bdc-105">Představuje podmínku, že dvourozměrné pole má obdélníkový tvar.</span><span class="sxs-lookup"><span data-stu-id="22bdc-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="22bdc-106">Popis</span><span class="sxs-lookup"><span data-stu-id="22bdc-106">Description</span></span>

<span data-ttu-id="22bdc-107">Tato funkce vyhodnotí, že každý řádek v poli má stejnou délku.</span><span class="sxs-lookup"><span data-stu-id="22bdc-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="22bdc-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="22bdc-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="22bdc-109">Array: t [] []</span><span class="sxs-lookup"><span data-stu-id="22bdc-109">array : 'T[][]</span></span>

<span data-ttu-id="22bdc-110">Dvojrozměrné pole prvků</span><span class="sxs-lookup"><span data-stu-id="22bdc-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="22bdc-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="22bdc-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="22bdc-112">Zpráva, která se má vytisknout, pokud pole není obdélníkové pole</span><span class="sxs-lookup"><span data-stu-id="22bdc-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="22bdc-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="22bdc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="22bdc-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="22bdc-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="22bdc-115">'S</span><span class="sxs-lookup"><span data-stu-id="22bdc-115">'T</span></span>

<span data-ttu-id="22bdc-116">Typ každého prvku `array` .</span><span class="sxs-lookup"><span data-stu-id="22bdc-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="22bdc-117">Příklad</span><span class="sxs-lookup"><span data-stu-id="22bdc-117">Example</span></span>

```qsharp
RectangularArrayFact([[1, 2], [3, 4]], "Array is not rectangular");       // okay
RectangularArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not rectangular"); // okay
RectangularArrayFact([[1, 2], [3, 4, 5]], "Array is not rectangular");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="22bdc-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="22bdc-118">See Also</span></span>

- [<span data-ttu-id="22bdc-119">Microsoft. Forms. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="22bdc-119">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)