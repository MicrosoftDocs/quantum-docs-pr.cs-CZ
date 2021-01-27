---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 46745632e2f6bafad0d7359141522b84f48c039d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839621"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="e66d2-102">HTermToGenIdx – funkce</span><span class="sxs-lookup"><span data-stu-id="e66d2-102">HTermToGenIdx function</span></span>

<span data-ttu-id="e66d2-103">Obor názvů: [Microsoft.. chemie](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e66d2-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="e66d2-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e66d2-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="e66d2-105">Převede výraz Hamiltonian ve `HTerm` formátu dat na GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="e66d2-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="e66d2-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e66d2-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="e66d2-107">termín: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="e66d2-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="e66d2-108">Vstupní data ve `HTerm` formátu.</span><span class="sxs-lookup"><span data-stu-id="e66d2-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="e66d2-109">termType: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e66d2-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e66d2-110">Další informace přidané do GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="e66d2-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="e66d2-111">Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e66d2-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e66d2-112">GeneratorIndex reprezentující Hamiltonian termín, který představuje `term` , spolu s dalšími informacemi, které přidal `termType` .</span><span class="sxs-lookup"><span data-stu-id="e66d2-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>