---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 84dc132528f8fd1c45fb2f7345111a05626ee686
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839628"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="231eb-102">HTermsToGenIdx – funkce</span><span class="sxs-lookup"><span data-stu-id="231eb-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="231eb-103">Obor názvů: [Microsoft.. chemie](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="231eb-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="231eb-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="231eb-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="231eb-105">Převede index na Hamiltonian termín ve `HTerm[]` formátu dat na GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="231eb-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="231eb-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="231eb-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="231eb-107">data: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="231eb-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="231eb-108">Vstupní data ve `HTerm[]` formátu.</span><span class="sxs-lookup"><span data-stu-id="231eb-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="231eb-109">termType: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="231eb-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="231eb-110">Další informace přidané do GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="231eb-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="231eb-111">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="231eb-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="231eb-112">Index na termín Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="231eb-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="231eb-113">Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="231eb-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="231eb-114">GeneratorIndex reprezentující Hamiltonian termín, který představuje `data[idx]` , spolu s dalšími informacemi, které přidal `termType` .</span><span class="sxs-lookup"><span data-stu-id="231eb-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>