---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 936e1bcc58b2f1af3bdb606884128c38d2f58867
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204109"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="bbfdf-102">HTermsToGenSys – funkce</span><span class="sxs-lookup"><span data-stu-id="bbfdf-102">HTermsToGenSys function</span></span>

<span data-ttu-id="bbfdf-103">Obor názvů: [Microsoft.. chemie](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="bbfdf-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="bbfdf-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="bbfdf-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="bbfdf-105">Převede Hamiltonian ve `HTerm[]` formátu dat na GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="bbfdf-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="bbfdf-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="bbfdf-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="bbfdf-107">data: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="bbfdf-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="bbfdf-108">Vstupní data ve `HTerm[]` formátu.</span><span class="sxs-lookup"><span data-stu-id="bbfdf-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="bbfdf-109">termType: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="bbfdf-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="bbfdf-110">Další informace přidané do GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="bbfdf-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="bbfdf-111">Výstup: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="bbfdf-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="bbfdf-112">GeneratorSystem představující Hamiltonian reprezentovaný vstupem `data` .</span><span class="sxs-lookup"><span data-stu-id="bbfdf-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>