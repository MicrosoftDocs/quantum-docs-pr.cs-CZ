---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliMajIdx_
title: _ZTermToPauliMajIdx_ – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 890e60c4b7c5bc474c9f00b59dac6bfddb0e891b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698488"
---
# <a name="_ztermtopaulimajidx_-function"></a><span data-ttu-id="3dc0b-102">_ZTermToPauliMajIdx_ – funkce</span><span class="sxs-lookup"><span data-stu-id="3dc0b-102">_ZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="3dc0b-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="3dc0b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="3dc0b-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3dc0b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3dc0b-105">Převede GeneratorIndex popisující termín Z na výraz "GeneratorIndex []" v souvislosti s Paul.</span><span class="sxs-lookup"><span data-stu-id="3dc0b-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="3dc0b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3dc0b-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="3dc0b-107">termín: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3dc0b-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3dc0b-108">`GeneratorIndex` představuje termín Z.</span><span class="sxs-lookup"><span data-stu-id="3dc0b-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="3dc0b-109">Výstup: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="3dc0b-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="3dc0b-110">"GeneratorIndex []" vyjadřuje termíny Z termínu Pauli.</span><span class="sxs-lookup"><span data-stu-id="3dc0b-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>