---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliMajIdx_
title: _ZTermToPauliMajIdx_ – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 56de7b7b425b7d7c5830c15d7119fc1d0291d061
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839090"
---
# <a name="_ztermtopaulimajidx_-function"></a><span data-ttu-id="9ab03-102">_ZTermToPauliMajIdx_ – funkce</span><span class="sxs-lookup"><span data-stu-id="9ab03-102">_ZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="9ab03-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="9ab03-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="9ab03-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="9ab03-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="9ab03-105">Převede GeneratorIndex popisující termín Z na výraz "GeneratorIndex []" v souvislosti s Paul.</span><span class="sxs-lookup"><span data-stu-id="9ab03-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="9ab03-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="9ab03-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="9ab03-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="9ab03-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="9ab03-108">`GeneratorIndex` představuje termín Z.</span><span class="sxs-lookup"><span data-stu-id="9ab03-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="9ab03-109">Výstup: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="9ab03-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="9ab03-110">"GeneratorIndex []" vyjadřuje termíny Z termínu Pauli.</span><span class="sxs-lookup"><span data-stu-id="9ab03-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>