---
title: Kontrola použití invalidateed qubits | Simulátor sledování počítačového systému | Microsoft Docs
description: Přehled simulátoru trasování počítačů s využitím
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 7403381b995ab660aa5cbc5a52b1e12c5c9ce442
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184963"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="1fbc3-103">Kontrola použití neověřené Qubits</span><span class="sxs-lookup"><span data-stu-id="1fbc3-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="1fbc3-104">`Invalidated Qubits Use Checker` je součástí [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítače, který je určený pro detekci potenciálních chyb v kódu.</span><span class="sxs-lookup"><span data-stu-id="1fbc3-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="1fbc3-105">Vezměte v úvahu následující část kódu Q # pro ilustraci problémů zjištěných `Invalidated Qubits Use Checker`.</span><span class="sxs-lookup"><span data-stu-id="1fbc3-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubitTest () : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="1fbc3-106">Když se `H` aplikuje na `q[0]` odkazuje na už vydaný qubit.</span><span class="sxs-lookup"><span data-stu-id="1fbc3-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="1fbc3-107">To může způsobit nedefinované chování.</span><span class="sxs-lookup"><span data-stu-id="1fbc3-107">This can cause undefined behavior.</span></span> <span data-ttu-id="1fbc3-108">Pokud je povolená `Invalidated Qubits Use Checker`, bude vyvolána výjimka `InvalidatedQubitsUseCheckerException`, pokud se operace použije na už vydaný qubit.</span><span class="sxs-lookup"><span data-stu-id="1fbc3-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="1fbc3-109">Další podrobnosti najdete v dokumentaci k rozhraní API v [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="1fbc3-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="1fbc3-110">Použití funkce Qubits s neověřenou kontrolou v C# programu</span><span class="sxs-lookup"><span data-stu-id="1fbc3-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="1fbc3-111">Tady je příklad kódu C# ovladače pro použití `Trace
Simulator` počítače s více instancemi s povoleným `Invalidated Qubits Use Checker`em:</span><span class="sxs-lookup"><span data-stu-id="1fbc3-111">The following is an example of C# driver code for using the quantum computer `Trace
Simulator` with the `Invalidated Qubits Use Checker` enabled:</span></span> 

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
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="1fbc3-112">Třída `QCTraceSimulatorConfiguration` ukládá konfiguraci simulátoru trasování počítačů a může být poskytnuta jako argument pro `QCTraceSimulator` konstruktor.</span><span class="sxs-lookup"><span data-stu-id="1fbc3-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="1fbc3-113">Pokud je `useInvalidatedQubitsUseChecker` nastaveno na hodnotu true, je povolen `Invalidated Qubits Use Checker`.</span><span class="sxs-lookup"><span data-stu-id="1fbc3-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="1fbc3-114">Další podrobnosti najdete v dokumentaci k rozhraní API na [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) a [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="1fbc3-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="1fbc3-115">Další informace najdete v tématech</span><span class="sxs-lookup"><span data-stu-id="1fbc3-115">See also</span></span> ##

- <span data-ttu-id="1fbc3-116">Přehled [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) počítačů ve službě.</span><span class="sxs-lookup"><span data-stu-id="1fbc3-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>