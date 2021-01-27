---
title: Kvantové simulátory a programy v Q#
description: Popisuje kvantové simulátory dostupné jako cílové počítače pro programy v Q#.
author: QuantumWriter
ms.author: v-benbra
ms.date: 6/17/2020
ms.topic: conceptual
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: 408c636d5383cf594e7ebec6ab2edd66e20ffb82
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858773"
---
# <a name="quantum-simulators"></a><span data-ttu-id="b3006-103">Kvantové simulátory</span><span class="sxs-lookup"><span data-stu-id="b3006-103">Quantum simulators</span></span>

<span data-ttu-id="b3006-104">Kvantové simulátory jsou softwarové programy spouštěné na klasických počítačích. Fungují jako *cílové počítače* pro programy v Q# a umožňují spouštět a testovat kvantové programy v prostředí, které předpovídá, jak budou qubity bude reagovat na různé operace.</span><span class="sxs-lookup"><span data-stu-id="b3006-104">Quantum simulators are software programs that run on classical computers and act as the *target machine* for a Q# program, making it possible to run and test quantum programs in an environment that predicts how qubits will react to different operations.</span></span> <span data-ttu-id="b3006-105">V tomto článku se dozvíte, které kvantové simulátory jsou součástí sady Quantum Development Kit (QDK), a seznámíte se s různými způsoby předání programů v Q# simulátorům, například prostřednictvím příkazového řádku nebo pomocí kódu ovladače napsaného v klasickém jazyce.</span><span class="sxs-lookup"><span data-stu-id="b3006-105">This article describes which quantum simulators are included with the Quantum Development Kit (QDK), and different ways that you can pass a Q# program to the quantum simulators, for example, via the command line or by using driver code written in a classical language.</span></span>  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a><span data-ttu-id="b3006-106">Kvantové simulátory sady Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="b3006-106">The Quantum Development Kit (QDK) quantum simulators</span></span>

<span data-ttu-id="b3006-107">Kvantový simulátor zodpovídá za poskytnutí implementací kvantových primitiv pro daný algoritmus.</span><span class="sxs-lookup"><span data-stu-id="b3006-107">The quantum simulator is responsible for providing implementations of quantum primitives for an algorithm.</span></span> <span data-ttu-id="b3006-108">Mezi ně patří primitivní operace, jako je `H`, `CNOT` a `Measure`, a také nástroje pro správu a sledování qubitů.</span><span class="sxs-lookup"><span data-stu-id="b3006-108">This includes primitive operations such as `H`, `CNOT`, and `Measure`, as well as qubit management and tracking.</span></span> <span data-ttu-id="b3006-109">Sada QDK obsahuje různé třídy kvantových simulátorů reprezentujících různé způsoby simulace stejného kvantového algoritmu.</span><span class="sxs-lookup"><span data-stu-id="b3006-109">The QDK includes different classes of quantum simulators representing different ways of simulating the same quantum algorithm.</span></span> 


<span data-ttu-id="b3006-110">Každý typ kvantového simulátoru může zajišťovat odlišnou implementaci těchto primitiv.</span><span class="sxs-lookup"><span data-stu-id="b3006-110">Each type of quantum simulator can provide different implementations of these primitives.</span></span> <span data-ttu-id="b3006-111">Například [simulátor celkového stavu](xref:microsoft.quantum.machines.full-state-simulator) spouští kvantový algoritmus kompletní simulací [kvantového stavového vektoru](xref:microsoft.quantum.glossary#quantum-state), zatímco [simulátor trasování kvantového počítače](xref:microsoft.quantum.machines.qc-trace-simulator.intro) vůbec nebere aktuální kvantový stav v úvahu.</span><span class="sxs-lookup"><span data-stu-id="b3006-111">For example, the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator) runs the quantum algorithm by fully simulating the [quantum state vector](xref:microsoft.quantum.glossary#quantum-state), whereas the [quantum computer trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) doesn't consider the actual quantum state at all.</span></span> <span data-ttu-id="b3006-112">Místo toho sleduje hradla, qubity a další prostředky použité v algoritmu.</span><span class="sxs-lookup"><span data-stu-id="b3006-112">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machine-classes"></a><span data-ttu-id="b3006-113">Třídy kvantových počítačů</span><span class="sxs-lookup"><span data-stu-id="b3006-113">Quantum machine classes</span></span>

<span data-ttu-id="b3006-114">V budoucnu bude sady QDK definovat další třídy kvantových počítačů s podporou dalších typů simulace a s podporou spouštění algoritmů na kvantovém hardwaru.</span><span class="sxs-lookup"><span data-stu-id="b3006-114">In the future, the QDK will define additional quantum machine classes to support other types of simulation and to support running on quantum hardware.</span></span> <span data-ttu-id="b3006-115">Díky tomu, že umožňujeme neměnnost algoritmů při změnách implementace samotného počítače, usnadňujeme testování a ladění algoritmů v simulaci a následné spouštění na reálném hardwaru s jistotou, že se algoritmus nezměnil.</span><span class="sxs-lookup"><span data-stu-id="b3006-115">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

<span data-ttu-id="b3006-116">Sada QDK zahrnuje několik tříd kvantových počítačů, které jsou definované v oboru názvů `Microsoft.Quantum.Simulation.Simulators`.</span><span class="sxs-lookup"><span data-stu-id="b3006-116">The QDK includes several quantum machine classes, all defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

|<span data-ttu-id="b3006-117">Simulátor</span><span class="sxs-lookup"><span data-stu-id="b3006-117">Simulator</span></span> |<span data-ttu-id="b3006-118">Třída</span><span class="sxs-lookup"><span data-stu-id="b3006-118">Class</span></span>|<span data-ttu-id="b3006-119">Popis</span><span class="sxs-lookup"><span data-stu-id="b3006-119">Description</span></span>|
|-----|------|---|
|[<span data-ttu-id="b3006-120">Simulátor celkového stavu</span><span class="sxs-lookup"><span data-stu-id="b3006-120">Full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | <span data-ttu-id="b3006-121">Spouští a ladí kvantové algoritmy a je omezený na zhruba 30 qubitů.</span><span class="sxs-lookup"><span data-stu-id="b3006-121">Runs and debugs quantum algorithms, and is limited to about 30 qubits.</span></span> |
|[<span data-ttu-id="b3006-122">Jednoduchý estimátor prostředků</span><span class="sxs-lookup"><span data-stu-id="b3006-122">Simple resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | <span data-ttu-id="b3006-123">Provádí nejvyšší úroveň analýz prostředků vyžadovaných ke spuštění kvantového algoritmu a podporuje tisíce qubitů.</span><span class="sxs-lookup"><span data-stu-id="b3006-123">Performs a top level analysis of the resources needed to run a quantum algorithm, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="b3006-124">Trasovací estimátor prostředků</span><span class="sxs-lookup"><span data-stu-id="b3006-124">Trace-based resource estimator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |<span data-ttu-id="b3006-125">Spouští pokročilejší analýzy vyžadovaných prostředků v rámci celého grafu volání a podporuje tisíce qubitů.</span><span class="sxs-lookup"><span data-stu-id="b3006-125">Runs advanced analysis of resources consumptions for the algorithm's entire call-graph, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="b3006-126">Simulátor Toffoli</span><span class="sxs-lookup"><span data-stu-id="b3006-126">Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |<span data-ttu-id="b3006-127">Simuluje kvantové algoritmy, které jsou omezené na kvantové operace `X` a `CNOT` vícenásobně řízené operace `X` a podporuje miliony qubitů.</span><span class="sxs-lookup"><span data-stu-id="b3006-127">Simulates quantum algorithms that are limited to `X`, `CNOT`, and multi-controlled `X` quantum operations, and supports million of qubits.</span></span> |

## <a name="invoking-the-quantum-simulator"></a><span data-ttu-id="b3006-128">Vyvolání kvantového simulátoru</span><span class="sxs-lookup"><span data-stu-id="b3006-128">Invoking the quantum simulator</span></span>

<span data-ttu-id="b3006-129">V tématu [Způsoby spuštění programu v Q#](xref:microsoft.quantum.guide.host-programs) jsou popsané tři způsoby předávání kódu Q# do kvantového simulátoru:</span><span class="sxs-lookup"><span data-stu-id="b3006-129">In [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs), three ways of passing the Q# code to the quantum simulator are demonstrated:</span></span> 

* <span data-ttu-id="b3006-130">Použití příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="b3006-130">Using the command line</span></span>
* <span data-ttu-id="b3006-131">Použití hostitelského programu v Pythonu</span><span class="sxs-lookup"><span data-stu-id="b3006-131">Using a Python host program</span></span>
* <span data-ttu-id="b3006-132">Použití hostitelského programu v C#</span><span class="sxs-lookup"><span data-stu-id="b3006-132">Using a C# host program</span></span>

<span data-ttu-id="b3006-133">Kvantové počítače jsou instancemi normálních tříd .NET, takže jsou vytvořeny vyvoláním jejich konstruktoru stejně jako u jakékoli jiné třídy .NET.</span><span class="sxs-lookup"><span data-stu-id="b3006-133">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span> <span data-ttu-id="b3006-134">Jak to uděláte, závisí na způsobu spuštění programu v Q#.</span><span class="sxs-lookup"><span data-stu-id="b3006-134">How you do this depends on how you run the Q# program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b3006-135">Další kroky</span><span class="sxs-lookup"><span data-stu-id="b3006-135">Next steps</span></span>

* <span data-ttu-id="b3006-136">Podrobné informace o vyvolání cílových počítačů pro programy v Q# v různých prostředích najdete v tématu [Způsoby spuštění programu v Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="b3006-136">For details about how to invoke target machines for Q# programs in different environments, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
