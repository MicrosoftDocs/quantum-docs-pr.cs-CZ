---
title: Kontrola použití neověřených qubits – sada pro vývoj všech procesorů
description: Přečtěte si o nástroji Microsoft QDK invalidateed qubits pro kontrolu použití, který používá simulátor trasování doby provozu ke kontrole Q# kódu pro potenciálně neplatnou qubits.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9014097ace7c9f19d93a92372da40f71fa7f87ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858625"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a><span data-ttu-id="adde0-103">Simulátor trasování provozu: neověřená Kontrola použití qubits</span><span class="sxs-lookup"><span data-stu-id="adde0-103">Quantum trace simulator: invalidated qubits use checker</span></span>

<span data-ttu-id="adde0-104">Nástroj pro kontrolu použití neověřených qubits je součástí nástroje pro vybudování doby [provozu.](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="adde0-104">The invalidated qubits use checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="adde0-105">Můžete ji použít ke zjištění potenciálních chyb v kódu způsobených neplatným qubits.</span><span class="sxs-lookup"><span data-stu-id="adde0-105">You can use it to detect potential bugs in the code caused by invalid qubits.</span></span> 

## <a name="invalid-qubits"></a><span data-ttu-id="adde0-106">Neplatný qubits</span><span class="sxs-lookup"><span data-stu-id="adde0-106">Invalid qubits</span></span>

<span data-ttu-id="adde0-107">Vezměte v úvahu následující část Q# kódu pro ilustraci problémů zjištěných neověřeným qubits použití nástroje:</span><span class="sxs-lookup"><span data-stu-id="adde0-107">Consider the following piece of Q# code to illustrate the issues detected by the invalidated qubits use checker:</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="adde0-108">Při použití `H` operace na `q[0]` , odkazuje na již vydaný qubit, což může způsobit nedefinované chování.</span><span class="sxs-lookup"><span data-stu-id="adde0-108">When you apply the `H` operation to `q[0]`, it points to an already released qubit, which can cause undefined behavior.</span></span> <span data-ttu-id="adde0-109">Pokud je povolená funkce Qubits pro kontrolu použití, vyvolá výjimku, `InvalidatedQubitsUseCheckerException` Pokud program použije operaci na už vydaný qubit.</span><span class="sxs-lookup"><span data-stu-id="adde0-109">When the Invalidated Qubits Use Checker is enabled, it throws the exception `InvalidatedQubitsUseCheckerException` if the program applies an operation to an already released qubit.</span></span> <span data-ttu-id="adde0-110">Další informace naleznete v tématu <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>.</span><span class="sxs-lookup"><span data-stu-id="adde0-110">For more information, see <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>.</span></span>

## <a name="invoking-the-invalidated-qubits-use-checker"></a><span data-ttu-id="adde0-111">Vyvolává se qubits pro kontrolu použití neověřených</span><span class="sxs-lookup"><span data-stu-id="adde0-111">Invoking the invalidated qubits use checker</span></span>

<span data-ttu-id="adde0-112">Chcete-li spustit simulátor trasování doby provozu s neověřeným qubits, je nutné vytvořit <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instanci, nastavit `UseInvalidatedQubitsUseChecker` vlastnost na **hodnotu true** a poté vytvořit novou <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instanci s `QCTraceSimulatorConfiguration` parametrem.</span><span class="sxs-lookup"><span data-stu-id="adde0-112">To run the quantum trace simulator with the invalidated qubits use checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseInvalidatedQubitsUseChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a><span data-ttu-id="adde0-113">Použití funkce qubits s neověřenou kontrolou v hostitelském programu C#</span><span class="sxs-lookup"><span data-stu-id="adde0-113">Using the invalidated qubits use checker in a C# host program</span></span>

<span data-ttu-id="adde0-114">Následuje příklad hostitelských programů v jazyce C#, které používají simulátor trasování doby provozu s povoleným qubitsm ověřováním pomocí služby invalidateed:</span><span class="sxs-lookup"><span data-stu-id="adde0-114">The following is an example of C# host programs that uses the quantum trace simulator with the invalidated qubits use checker enabled:</span></span> 

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.UseInvalidatedQubitsUseChecker = true; // enables UseInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="adde0-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="adde0-115">See also</span></span>

- <span data-ttu-id="adde0-116">Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) pro všechna ta.</span><span class="sxs-lookup"><span data-stu-id="adde0-116">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="adde0-117"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="adde0-117">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="adde0-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="adde0-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="adde0-119"><xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>Reference k rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="adde0-119">The <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException> API reference.</span></span>
