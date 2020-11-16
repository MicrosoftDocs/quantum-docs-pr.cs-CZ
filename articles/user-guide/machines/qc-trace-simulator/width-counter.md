---
title: Čítač šířky – sada pro vývoj všech procesorů
description: 'Přečtěte si o čítači šířky Microsoft QDK, který používá simulátor trasování doby provozu k výpočtu počtu qubits přidělených a vypůjčených operacemi v Q# programu.'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: e54e92cc4a76ce9f9c5aead84f2b64320d6b4f1c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691115"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="1ef9d-103">Simulátor trasování doby využití: čítač šířky</span><span class="sxs-lookup"><span data-stu-id="1ef9d-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="1ef9d-104">Čítač šířky je součástí [simulátoru pro sledování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)doby plnění.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="1ef9d-105">Můžete ji použít k určení počtu qubits přidělených a vypůjčených každou operací v Q# programu.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-105">You can use it to count the number of qubits allocated and borrowed by each operation in a Q# program.</span></span> <span data-ttu-id="1ef9d-106">Některé primitivní operace mohou přidělit nadbytečné qubits, například vynásobit kontrolované `X` operace nebo kontrolované `T` operace.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="1ef9d-107">Vyvolání čítače šířky</span><span class="sxs-lookup"><span data-stu-id="1ef9d-107">Invoking the width counter</span></span>

<span data-ttu-id="1ef9d-108">Chcete-li spustit simulátor trasování doby provozu s čítačem šířky, je nutné vytvořit <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instanci, nastavit `UseWidthCounter` vlastnost na **hodnotu true** a poté vytvořit novou <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instanci s `QCTraceSimulatorConfiguration` parametrem jako.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true** , and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="1ef9d-109">Použití čítače šířky v hostitelském programu C#</span><span class="sxs-lookup"><span data-stu-id="1ef9d-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="1ef9d-110">Příklad jazyka C#, který následuje v tomto oddílu, vypočítá počet extra qubits přidělených implementací operace s vynásobeným výsledkem <xref:Microsoft.Quantum.Intrinsic.X> , který je založený na následujícím Q# ukázkovém kódu:</span><span class="sxs-lookup"><span data-stu-id="1ef9d-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:Microsoft.Quantum.Intrinsic.X> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="1ef9d-111">Operace s hodnotou vynásobení <xref:Microsoft.Quantum.Intrinsic.X> funguje na celkem pět qubits, přiděluje dvě [pomocné qubits](xref:microsoft.quantum.glossary#ancilla)a má vstupní šířku **5** .</span><span class="sxs-lookup"><span data-stu-id="1ef9d-111">The multiply controlled <xref:Microsoft.Quantum.Intrinsic.X> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5** .</span></span> <span data-ttu-id="1ef9d-112">Pomocí následujícího programu v jazyce C# ověřte počty:</span><span class="sxs-lookup"><span data-stu-id="1ef9d-112">Use the following C# program to verify the counts:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
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

<span data-ttu-id="1ef9d-113">První část programu spustí `ApplyMultiControlledX` operaci.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="1ef9d-114">Druhá část používá [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metodu pro načtení počtu přidělených qubits a také počet qubits, které `Controlled X` operace přijala jako vstup.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="1ef9d-115">Nakonec můžete vystavit výstup všech statistik shromážděných pomocí čítače šířky ve formátu CSV pomocí následujících možností:</span><span class="sxs-lookup"><span data-stu-id="1ef9d-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="1ef9d-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="1ef9d-116">See also</span></span>

- <span data-ttu-id="1ef9d-117">Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) pro všechna ta.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="1ef9d-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="1ef9d-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="1ef9d-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="1ef9d-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
