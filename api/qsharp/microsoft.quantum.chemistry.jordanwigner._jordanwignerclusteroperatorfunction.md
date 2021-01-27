---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorFunction
title: _JordanWignerClusterOperatorFunction funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 71aa0256b4d2911fe9d8e3ca091735d6375ed23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839489"
---
# <a name="_jordanwignerclusteroperatorfunction-function"></a><span data-ttu-id="091e9-102">_JordanWignerClusterOperatorFunction funkce</span><span class="sxs-lookup"><span data-stu-id="091e9-102">_JordanWignerClusterOperatorFunction function</span></span>

<span data-ttu-id="091e9-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="091e9-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="091e9-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="091e9-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="091e9-105">Představuje dynamický generátor jako sadu simulovaných bran a rozšíření v JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="091e9-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function _JordanWignerClusterOperatorFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="091e9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="091e9-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="091e9-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="091e9-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="091e9-108">Index generátoru, který se má znázornit jako jednotkový vývoj v JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="091e9-108">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="091e9-109">Výstup: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="091e9-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="091e9-110">`EvolutionUnitary`Představuje čas – vývoj v rámci termínu, na který se odkazuje v ' generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="091e9-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>