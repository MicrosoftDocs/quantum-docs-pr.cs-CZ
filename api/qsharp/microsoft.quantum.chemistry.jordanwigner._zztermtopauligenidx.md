---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliGenIdx
title: _ZZTermToPauliGenIdx funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 0bbb0325406767f9d27e317ccc306f1fe77d00f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839062"
---
# <a name="_zztermtopauligenidx-function"></a><span data-ttu-id="33be5-102">_ZZTermToPauliGenIdx funkce</span><span class="sxs-lookup"><span data-stu-id="33be5-102">_ZZTermToPauliGenIdx function</span></span>

<span data-ttu-id="33be5-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="33be5-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="33be5-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="33be5-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="33be5-105">Převede GeneratorIndex popisující pojem ZZ na výraz "GeneratorIndex []" v souvislosti s Paul.</span><span class="sxs-lookup"><span data-stu-id="33be5-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="33be5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="33be5-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="33be5-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="33be5-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="33be5-108">`GeneratorIndex` představuje období ZZ.</span><span class="sxs-lookup"><span data-stu-id="33be5-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="33be5-109">Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="33be5-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="33be5-110">Výraz "GeneratorIndex []" vyjadřující pojem ZZ jako Pauli podmínky.</span><span class="sxs-lookup"><span data-stu-id="33be5-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>