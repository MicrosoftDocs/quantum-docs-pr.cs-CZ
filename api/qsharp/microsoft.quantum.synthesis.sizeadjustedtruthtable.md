---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 3480f022df7a289594b003f201d16d8bf7c29d7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709280"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="f7879-102">SizeAdjustedTruthTable – funkce</span><span class="sxs-lookup"><span data-stu-id="f7879-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="f7879-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f7879-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f7879-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7879-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f7879-105">Upraví tabulku pravdy z pole logických hodnot podle počtu proměnných.</span><span class="sxs-lookup"><span data-stu-id="f7879-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="f7879-106">Je vráceno nové pole o délce `2^numVars` , pravděpodobně vyžadovat, aby `table` se velikost rozšířila na `false` položky nebo zkrácení na `2^numVars` prvky.</span><span class="sxs-lookup"><span data-stu-id="f7879-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="f7879-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="f7879-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="f7879-108">Tabulka: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="f7879-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="f7879-109">Tabulka pravdy jako pole hodnot hodnoty pravdy</span><span class="sxs-lookup"><span data-stu-id="f7879-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="f7879-110">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f7879-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f7879-111">Počet proměnných</span><span class="sxs-lookup"><span data-stu-id="f7879-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="f7879-112">Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="f7879-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="f7879-113">Velikost upravená tabulka pravdy</span><span class="sxs-lookup"><span data-stu-id="f7879-113">Size adjusted truth table</span></span>