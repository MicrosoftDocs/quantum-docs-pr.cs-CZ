---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: dd72355adb32f9a0d109ee36b24be2d445f3fa66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698684"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="3f757-102">HTermToGenIdx – funkce</span><span class="sxs-lookup"><span data-stu-id="3f757-102">HTermToGenIdx function</span></span>

<span data-ttu-id="3f757-103">Obor názvů: [Microsoft.. chemie](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="3f757-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="3f757-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f757-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f757-105">Převede výraz Hamiltonian ve `HTerm` formátu dat na GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="3f757-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="3f757-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3f757-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="3f757-107">termín: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="3f757-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="3f757-108">Vstupní data ve `HTerm` formátu.</span><span class="sxs-lookup"><span data-stu-id="3f757-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="3f757-109">termType: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3f757-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3f757-110">Další informace přidané do GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="3f757-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="3f757-111">Výstup: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3f757-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3f757-112">GeneratorIndex reprezentující Hamiltonian termín, který představuje `term` , spolu s dalšími informacemi, které přidal `termType` .</span><span class="sxs-lookup"><span data-stu-id="3f757-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>