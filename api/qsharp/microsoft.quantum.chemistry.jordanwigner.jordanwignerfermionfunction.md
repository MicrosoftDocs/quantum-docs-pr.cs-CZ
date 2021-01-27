---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionFunction
title: JordanWignerFermionFunction – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: a1c0b56e18f3adfb6c413880cc0c155741a3255a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98838859"
---
# <a name="jordanwignerfermionfunction-function"></a><span data-ttu-id="df4ad-102">JordanWignerFermionFunction – funkce</span><span class="sxs-lookup"><span data-stu-id="df4ad-102">JordanWignerFermionFunction function</span></span>

<span data-ttu-id="df4ad-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="df4ad-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="df4ad-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="df4ad-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="df4ad-105">Představuje dynamický generátor jako sadu simulovaných bran a rozšíření v JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="df4ad-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function JordanWignerFermionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="df4ad-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="df4ad-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="df4ad-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="df4ad-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="df4ad-108">Index generátoru, který se má znázornit jako jednotkový vývoj v JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="df4ad-108">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="df4ad-109">Výstup: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="df4ad-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="df4ad-110">`EvolutionUnitary`Představuje čas – vývoj v rámci termínu, na který se odkazuje v ' generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="df4ad-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>