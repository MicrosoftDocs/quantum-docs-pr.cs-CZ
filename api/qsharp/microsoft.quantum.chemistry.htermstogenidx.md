---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 73324a48cc4b42de0d5d8618ad9e833d289125f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698689"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="48af7-102">HTermsToGenIdx – funkce</span><span class="sxs-lookup"><span data-stu-id="48af7-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="48af7-103">Obor názvů: [Microsoft.. chemie](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="48af7-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="48af7-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48af7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48af7-105">Převede index na Hamiltonian termín ve `HTerm[]` formátu dat na GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="48af7-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="48af7-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="48af7-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="48af7-107">data: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="48af7-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="48af7-108">Vstupní data ve `HTerm[]` formátu.</span><span class="sxs-lookup"><span data-stu-id="48af7-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="48af7-109">termType: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="48af7-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="48af7-110">Další informace přidané do GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="48af7-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="48af7-111">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48af7-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48af7-112">Index na termín Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="48af7-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="48af7-113">Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="48af7-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="48af7-114">GeneratorIndex reprezentující Hamiltonian termín, který představuje `data[idx]` , spolu s dalšími informacemi, které přidal `termType` .</span><span class="sxs-lookup"><span data-stu-id="48af7-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>