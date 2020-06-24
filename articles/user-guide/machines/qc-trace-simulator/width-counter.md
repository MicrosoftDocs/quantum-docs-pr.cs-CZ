---
title: Čítač šířky
description: Přečtěte si o čítači šířky Microsoft QDKe, který spočítá počet qubits přidělených a vydaných každou operací v programu pro práci za sebou.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274570"
---
# <a name="width-counter"></a><span data-ttu-id="def84-103">Čítač šířky</span><span class="sxs-lookup"><span data-stu-id="def84-103">Width Counter</span></span>

<span data-ttu-id="def84-104">`Width Counter`Počítá počet qubits přidělených a vydaných jednotlivými operacemi.</span><span class="sxs-lookup"><span data-stu-id="def84-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="def84-105">Všechny operace z `Microsoft.Quantum.Intrinsic` oboru názvů se vyjadřují v rámci jednoduchých qubit rotací, T Branch, qubitch Clifford bran, CNOT bran a měření multi-qubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="def84-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="def84-106">Některé primitivní operace mohou přidělit další qubits.</span><span class="sxs-lookup"><span data-stu-id="def84-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="def84-107">Můžete například vynásobit kontrolované `X` brány nebo řízené `T` brány.</span><span class="sxs-lookup"><span data-stu-id="def84-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="def84-108">Můžeme nám vypočítat počet dalších qubits přidělených implementací brány řízené vynásobením `X` :</span><span class="sxs-lookup"><span data-stu-id="def84-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="def84-109">Použití čítače šířky v rámci programu v jazyce C#</span><span class="sxs-lookup"><span data-stu-id="def84-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="def84-110">Vynásobení kontrolovaného `X` na základě celkového počtu 5 qubits přidělí 2 doplňkové qubits a jeho vstupní šířka bude 5.</span><span class="sxs-lookup"><span data-stu-id="def84-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="def84-111">Chcete-li zjistit, zda se jedná o tento případ, můžeme použít následující program C#:</span><span class="sxs-lookup"><span data-stu-id="def84-111">To check that this is the case, we can use the following C# program:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="def84-112">První část programu se spustí `ApplyMultiControlledX` .</span><span class="sxs-lookup"><span data-stu-id="def84-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="def84-113">V druhé části používáme metodu `QCTraceSimulator.GetMetric` k získání počtu přidělených qubits a také počtu qubits, které řízené `X` přijetí jako vstupu.</span><span class="sxs-lookup"><span data-stu-id="def84-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="def84-114">Nakonec můžete pro výstup všech statistik shromážděných pomocí čítače šířky ve formátu CSV použít následující:</span><span class="sxs-lookup"><span data-stu-id="def84-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="def84-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="def84-115">See also</span></span> ##

- <span data-ttu-id="def84-116">Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.</span><span class="sxs-lookup"><span data-stu-id="def84-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
