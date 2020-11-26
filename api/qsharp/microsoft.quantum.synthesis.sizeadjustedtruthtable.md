---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: c53ac3f2c46bca955847fc7b380337e3910390ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202919"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="f2664-102">SizeAdjustedTruthTable – funkce</span><span class="sxs-lookup"><span data-stu-id="f2664-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="f2664-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f2664-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f2664-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2664-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2664-105">Upraví tabulku pravdy z pole logických hodnot podle počtu proměnných.</span><span class="sxs-lookup"><span data-stu-id="f2664-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="f2664-106">Je vráceno nové pole o délce `2^numVars` , pravděpodobně vyžadovat, aby `table` se velikost rozšířila na `false` položky nebo zkrácení na `2^numVars` prvky.</span><span class="sxs-lookup"><span data-stu-id="f2664-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="f2664-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="f2664-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="f2664-108">Tabulka: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="f2664-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="f2664-109">Tabulka pravdy jako pole hodnot hodnoty pravdy</span><span class="sxs-lookup"><span data-stu-id="f2664-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="f2664-110">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2664-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2664-111">Počet proměnných</span><span class="sxs-lookup"><span data-stu-id="f2664-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="f2664-112">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="f2664-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="f2664-113">Velikost upravená tabulka pravdy</span><span class="sxs-lookup"><span data-stu-id="f2664-113">Size adjusted truth table</span></span>