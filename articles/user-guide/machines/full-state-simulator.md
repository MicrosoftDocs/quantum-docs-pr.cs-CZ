---
title: Plný stav simulátoru pro náročné na všechna ta – vývojová sada
description: Naučte se spouštět Q# programy v Microsoft Quantum Development Kit úplný stav simulátoru.
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 632af681c5818ab7246c0f5849a8b8e716b570cb
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833375"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="f8fba-103">Simulátor úplného stavu pro sadu QDK (pro vytváření plně stavů)</span><span class="sxs-lookup"><span data-stu-id="f8fba-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="f8fba-104">QDK poskytuje úplný stav simulátoru, který simuluje počítač s více podsystémy na vašem místním počítači.</span><span class="sxs-lookup"><span data-stu-id="f8fba-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="f8fba-105">Pomocí kompletního simulátoru stavu můžete spouštět a ladit algoritmy, které jsou napsané v rámci Q# , a to s využitím až 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="f8fba-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="f8fba-106">Úplný stav simulátoru je podobný simulátoru při používání služby Microsoft Research na platformě  [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) .</span><span class="sxs-lookup"><span data-stu-id="f8fba-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="f8fba-107">Vyvolání a spuštění simulátoru úplného stavu</span><span class="sxs-lookup"><span data-stu-id="f8fba-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="f8fba-108">Vystavíte plný stav simulátoru prostřednictvím `QuantumSimulator` třídy.</span><span class="sxs-lookup"><span data-stu-id="f8fba-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="f8fba-109">Další podrobnosti najdete v tématu [způsoby spuštění Q# programu](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="f8fba-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="f8fba-110">Vyvolání simulátoru z C #</span><span class="sxs-lookup"><span data-stu-id="f8fba-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="f8fba-111">Vytvořte instanci `QuantumSimulator` třídy a pak ji předejte `Run` metodě operace s více poli, spolu s dalšími parametry.</span><span class="sxs-lookup"><span data-stu-id="f8fba-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="f8fba-112">Vzhledem k tomu `QuantumSimulator` , že třída implementuje <xref:System.IDisposable> rozhraní, je nutné zavolat `Dispose` metodu, jakmile již nepotřebujete instanci simulátoru.</span><span class="sxs-lookup"><span data-stu-id="f8fba-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="f8fba-113">Nejlepším způsobem, jak to provést, je zabalit deklaraci a operace simulátoru do příkazu [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) , který automaticky volá `Dispose` metodu.</span><span class="sxs-lookup"><span data-stu-id="f8fba-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="f8fba-114">Vyvolání simulátoru z Pythonu</span><span class="sxs-lookup"><span data-stu-id="f8fba-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="f8fba-115">Použijte metodu [simulovat ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) z Q# knihovny Pythonu s importovanou Q# operací:</span><span class="sxs-lookup"><span data-stu-id="f8fba-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="f8fba-116">Vyvolání simulátoru z příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="f8fba-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="f8fba-117">Při spuštění Q# programu z příkazového řádku je úplným výchozím cílovým počítačem simulátor celého stavu.</span><span class="sxs-lookup"><span data-stu-id="f8fba-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="f8fba-118">Volitelně můžete pomocí parametru **--simulátor** (nebo **-s** ) určit požadovaný cílový počítač.</span><span class="sxs-lookup"><span data-stu-id="f8fba-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="f8fba-119">Oba následující příkazy spouštějí program pomocí kompletního simulátoru.</span><span class="sxs-lookup"><span data-stu-id="f8fba-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="f8fba-120">Vyvolání simulátoru z poznámkových bloků Juptyer</span><span class="sxs-lookup"><span data-stu-id="f8fba-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="f8fba-121">Pomocí příkazu I Q# Magic [% simulovat](xref:microsoft.quantum.iqsharp.magic-ref.simulate) spusťte Q# operaci.</span><span class="sxs-lookup"><span data-stu-id="f8fba-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="f8fba-122">Osazení simulátoru</span><span class="sxs-lookup"><span data-stu-id="f8fba-122">Seeding the simulator</span></span>

<span data-ttu-id="f8fba-123">Ve výchozím nastavení používá simulátor celého stavu generátor náhodných čísel pro simulaci náhodnosti.</span><span class="sxs-lookup"><span data-stu-id="f8fba-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="f8fba-124">Pro účely testování je někdy užitečné mít deterministické výsledky.</span><span class="sxs-lookup"><span data-stu-id="f8fba-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="f8fba-125">V programu v jazyce C# můžete to dosáhnout poskytnutím počáteční hodnoty generátoru náhodných čísel v `QuantumSimulator` konstruktoru prostřednictvím `randomNumberGeneratorSeed` parametru.</span><span class="sxs-lookup"><span data-stu-id="f8fba-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="f8fba-126">Konfigurace vláken</span><span class="sxs-lookup"><span data-stu-id="f8fba-126">Configuring threads</span></span>

<span data-ttu-id="f8fba-127">Simulátor celého stavu používá [OpenMP](http://www.openmp.org/) k paralelizovatí lineárního algebraický.</span><span class="sxs-lookup"><span data-stu-id="f8fba-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="f8fba-128">Ve výchozím nastavení používá OpenMP všechna dostupná hardwarová vlákna, což znamená, že programy s malým počtem qubits často běží pomalu, protože koordinace, která je vyžadována Dwarfs skutečnou práci.</span><span class="sxs-lookup"><span data-stu-id="f8fba-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="f8fba-129">To můžete opravit nastavením proměnné prostředí `OMP_NUM_THREADS` na malé číslo.</span><span class="sxs-lookup"><span data-stu-id="f8fba-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="f8fba-130">Jako pravidlo pro palec nakonfigurujte jedno vlákno pro až čtyři qubits a pak jedno další vlákno na qubit.</span><span class="sxs-lookup"><span data-stu-id="f8fba-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="f8fba-131">Je možné, že budete muset proměnnou upravit v závislosti na algoritmu.</span><span class="sxs-lookup"><span data-stu-id="f8fba-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8fba-132">Viz také</span><span class="sxs-lookup"><span data-stu-id="f8fba-132">See also</span></span>

- [<span data-ttu-id="f8fba-133">Estimátor kvantových prostředků</span><span class="sxs-lookup"><span data-stu-id="f8fba-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="f8fba-134">Kvantový simulátor Toffoli</span><span class="sxs-lookup"><span data-stu-id="f8fba-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="f8fba-135">Simulátor trasování doby využití</span><span class="sxs-lookup"><span data-stu-id="f8fba-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)