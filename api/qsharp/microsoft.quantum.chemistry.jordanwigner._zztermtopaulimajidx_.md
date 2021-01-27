---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliMajIdx_
title: _ZZTermToPauliMajIdx_ – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: b18529182083ae6a905036ce6c00c3a0695ffccf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839057"
---
# <a name="_zztermtopaulimajidx_-function"></a><span data-ttu-id="b4bcd-102">_ZZTermToPauliMajIdx_ – funkce</span><span class="sxs-lookup"><span data-stu-id="b4bcd-102">_ZZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="b4bcd-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="b4bcd-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="b4bcd-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b4bcd-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="b4bcd-105">Převede GeneratorIndex popisující pojem ZZ na výraz "GeneratorIndex []" v souvislosti s Paul.</span><span class="sxs-lookup"><span data-stu-id="b4bcd-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="b4bcd-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="b4bcd-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="b4bcd-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="b4bcd-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="b4bcd-108">`GeneratorIndex` představuje období ZZ.</span><span class="sxs-lookup"><span data-stu-id="b4bcd-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="b4bcd-109">Výstup: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="b4bcd-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="b4bcd-110">Výraz "GeneratorIndex []" vyjadřující pojem ZZ jako Pauli podmínky.</span><span class="sxs-lookup"><span data-stu-id="b4bcd-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>