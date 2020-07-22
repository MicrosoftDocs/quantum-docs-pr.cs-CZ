---
title: Plný stav simulátoru pro náročné na všechna ta – vývojová sada
description: 'Zjistěte, jak spustit programy Q # v simulátoru Microsoft Quantum Development Kit úplný stav.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: 563fdbd2a45461d112e4c46651eddd75c6fc3db2
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871174"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="36dbd-103">Simulátor úplného stavu pro sadu QDK (pro vytváření plně stavů)</span><span class="sxs-lookup"><span data-stu-id="36dbd-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="36dbd-104">QDK poskytuje úplný stav simulátoru, který simuluje počítač s více podsystémy na vašem místním počítači.</span><span class="sxs-lookup"><span data-stu-id="36dbd-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="36dbd-105">Pomocí celého stavového simulátoru můžete spouštět a ladit algoritmy, které jsou napsané v Q #, a to s využitím až 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="36dbd-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="36dbd-106">Úplný stav simulátoru je podobný simulátoru při používání služby Microsoft Research na platformě [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) .</span><span class="sxs-lookup"><span data-stu-id="36dbd-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="36dbd-107">Vyvolání a spuštění simulátoru úplného stavu</span><span class="sxs-lookup"><span data-stu-id="36dbd-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="36dbd-108">Vystavíte plný stav simulátoru prostřednictvím `QuantumSimulator` třídy.</span><span class="sxs-lookup"><span data-stu-id="36dbd-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="36dbd-109">Další podrobnosti najdete v tématu [způsoby spuštění programu Q #](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="36dbd-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="36dbd-110">Vyvolání simulátoru z C #</span><span class="sxs-lookup"><span data-stu-id="36dbd-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="36dbd-111">Vytvořte instanci `QuantumSimulator` třídy a pak ji předejte `Run` metodě operace s více poli, spolu s dalšími parametry.</span><span class="sxs-lookup"><span data-stu-id="36dbd-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="36dbd-112">Vzhledem k tomu `QuantumSimulator` , že třída implementuje <xref:System.IDisposable> rozhraní, je nutné zavolat `Dispose` metodu, jakmile již nepotřebujete instanci simulátoru.</span><span class="sxs-lookup"><span data-stu-id="36dbd-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="36dbd-113">Nejlepším způsobem, jak to provést, je zabalit deklaraci a operace simulátoru do příkazu [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) , který automaticky volá `Dispose` metodu.</span><span class="sxs-lookup"><span data-stu-id="36dbd-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="36dbd-114">Vyvolání simulátoru z Pythonu</span><span class="sxs-lookup"><span data-stu-id="36dbd-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="36dbd-115">Použijte metodu [simulovat ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) z knihovny Pythonu Q v knihovně Python s importovanou operací q #:</span><span class="sxs-lookup"><span data-stu-id="36dbd-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="36dbd-116">Vyvolání simulátoru z příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="36dbd-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="36dbd-117">Při spuštění programu Q # z příkazového řádku je úplným cílovým počítačem simulátor celého stavu.</span><span class="sxs-lookup"><span data-stu-id="36dbd-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="36dbd-118">Volitelně můžete pomocí parametru **--simulátor** (nebo **-s** ) určit požadovaný cílový počítač.</span><span class="sxs-lookup"><span data-stu-id="36dbd-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="36dbd-119">Oba následující příkazy spouštějí program pomocí kompletního simulátoru.</span><span class="sxs-lookup"><span data-stu-id="36dbd-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="36dbd-120">Vyvolání simulátoru z poznámkových bloků Juptyer</span><span class="sxs-lookup"><span data-stu-id="36dbd-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="36dbd-121">Pomocí příkazu SWEETIQ # Magic [% simulovat](xref:microsoft.quantum.iqsharp.magic-ref.simulate) spusťte operaci Q #.</span><span class="sxs-lookup"><span data-stu-id="36dbd-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="36dbd-122">Osazení simulátoru</span><span class="sxs-lookup"><span data-stu-id="36dbd-122">Seeding the simulator</span></span>

<span data-ttu-id="36dbd-123">Ve výchozím nastavení používá simulátor celého stavu generátor náhodných čísel pro simulaci náhodnosti.</span><span class="sxs-lookup"><span data-stu-id="36dbd-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="36dbd-124">Pro účely testování je někdy užitečné mít deterministické výsledky.</span><span class="sxs-lookup"><span data-stu-id="36dbd-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="36dbd-125">V programu v jazyce C# můžete to dosáhnout poskytnutím počáteční hodnoty generátoru náhodných čísel v `QuantumSimulator` konstruktoru prostřednictvím `randomNumberGeneratorSeed` parametru.</span><span class="sxs-lookup"><span data-stu-id="36dbd-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="36dbd-126">Konfigurace vláken</span><span class="sxs-lookup"><span data-stu-id="36dbd-126">Configuring threads</span></span>

<span data-ttu-id="36dbd-127">Simulátor celého stavu používá [OpenMP](http://www.openmp.org/) k paralelizovatí lineárního algebraický.</span><span class="sxs-lookup"><span data-stu-id="36dbd-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="36dbd-128">Ve výchozím nastavení používá OpenMP všechna dostupná hardwarová vlákna, což znamená, že programy s malým počtem qubits často běží pomalu, protože koordinace, která je vyžadována Dwarfs skutečnou práci.</span><span class="sxs-lookup"><span data-stu-id="36dbd-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="36dbd-129">To můžete opravit nastavením proměnné prostředí `OMP_NUM_THREADS` na malé číslo.</span><span class="sxs-lookup"><span data-stu-id="36dbd-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="36dbd-130">Jako pravidlo pro palec nakonfigurujte jedno vlákno pro až čtyři qubits a pak jedno další vlákno na qubit.</span><span class="sxs-lookup"><span data-stu-id="36dbd-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="36dbd-131">Je možné, že budete muset proměnnou upravit v závislosti na algoritmu.</span><span class="sxs-lookup"><span data-stu-id="36dbd-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="36dbd-132">Viz také</span><span class="sxs-lookup"><span data-stu-id="36dbd-132">See also</span></span>

- [<span data-ttu-id="36dbd-133">Estimatory prostředků</span><span class="sxs-lookup"><span data-stu-id="36dbd-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="36dbd-134">Simulátor Toffoli</span><span class="sxs-lookup"><span data-stu-id="36dbd-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="36dbd-135">Simulátor trasování doby využití</span><span class="sxs-lookup"><span data-stu-id="36dbd-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)