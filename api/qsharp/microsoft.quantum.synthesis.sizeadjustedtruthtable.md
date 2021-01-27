---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 8d69aa119c25a0f64743fec36c00ecdef2450c44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855323"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="141cd-102">SizeAdjustedTruthTable – funkce</span><span class="sxs-lookup"><span data-stu-id="141cd-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="141cd-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="141cd-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="141cd-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="141cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="141cd-105">Upraví tabulku pravdy z pole logických hodnot podle počtu proměnných.</span><span class="sxs-lookup"><span data-stu-id="141cd-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="141cd-106">Je vráceno nové pole o délce `2^numVars` , pravděpodobně vyžadovat, aby `table` se velikost rozšířila na `false` položky nebo zkrácení na `2^numVars` prvky.</span><span class="sxs-lookup"><span data-stu-id="141cd-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="141cd-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="141cd-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="141cd-108">Tabulka: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="141cd-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="141cd-109">Tabulka pravdy jako pole hodnot hodnoty pravdy</span><span class="sxs-lookup"><span data-stu-id="141cd-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="141cd-110">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="141cd-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="141cd-111">Počet proměnných</span><span class="sxs-lookup"><span data-stu-id="141cd-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="141cd-112">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="141cd-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="141cd-113">Velikost upravená tabulka pravdy</span><span class="sxs-lookup"><span data-stu-id="141cd-113">Size adjusted truth table</span></span>