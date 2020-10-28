---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705809"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="6add5-102">RectangularArrayFact – funkce</span><span class="sxs-lookup"><span data-stu-id="6add5-102">RectangularArrayFact function</span></span>

<span data-ttu-id="6add5-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6add5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6add5-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6add5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6add5-105">Představuje podmínku, že dvourozměrné pole má obdélníkový tvar.</span><span class="sxs-lookup"><span data-stu-id="6add5-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="6add5-106">Popis</span><span class="sxs-lookup"><span data-stu-id="6add5-106">Description</span></span>

<span data-ttu-id="6add5-107">Tato funkce vyhodnotí, že každý řádek v poli má stejnou délku.</span><span class="sxs-lookup"><span data-stu-id="6add5-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="6add5-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="6add5-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="6add5-109">Array: t [] []</span><span class="sxs-lookup"><span data-stu-id="6add5-109">array : 'T[][]</span></span>

<span data-ttu-id="6add5-110">Dvojrozměrné pole prvků</span><span class="sxs-lookup"><span data-stu-id="6add5-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="6add5-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6add5-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="6add5-112">Zpráva, která se má vytisknout, pokud pole není obdélníkové pole</span><span class="sxs-lookup"><span data-stu-id="6add5-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="6add5-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6add5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6add5-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6add5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6add5-115">'S</span><span class="sxs-lookup"><span data-stu-id="6add5-115">'T</span></span>

<span data-ttu-id="6add5-116">Typ každého prvku `array` .</span><span class="sxs-lookup"><span data-stu-id="6add5-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="6add5-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="6add5-117">See Also</span></span>

- [<span data-ttu-id="6add5-118">Microsoft. Forms. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="6add5-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)