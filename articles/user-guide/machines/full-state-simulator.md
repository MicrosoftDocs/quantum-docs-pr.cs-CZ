---
title: Simulátor plného stavu
description: 'Zjistěte, jak spustit programy Q # v simulátoru Microsoft Quantum Development Kit úplný stav.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274590"
---
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="2a324-103">Úplný simulátor pro vývoj všech stavů v sadě</span><span class="sxs-lookup"><span data-stu-id="2a324-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="2a324-104">Sada pro vývoj všech stavových prostředí poskytuje úplný stav simulátoru, který se podobá [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) od Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="2a324-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="2a324-105">Tento simulátor se dá použít ke spouštění a ladění algoritmů pro plnění a napsaných v Q # ve vašem počítači.</span><span class="sxs-lookup"><span data-stu-id="2a324-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="2a324-106">Tento simulátor při přístavování se zveřejňuje prostřednictvím `QuantumSimulator` třídy.</span><span class="sxs-lookup"><span data-stu-id="2a324-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="2a324-107">Chcete-li použít simulátor, jednoduše vytvořte instanci této třídy a předejte ji `Run` metodě operace, kterou chcete provést, spolu se zbytkem parametrů:</span><span class="sxs-lookup"><span data-stu-id="2a324-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="2a324-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="2a324-108">IDisposable</span></span>

<span data-ttu-id="2a324-109">`QuantumSimulator`Třída implementuje <xref:System.IDisposable> , takže `Dispose` by metoda měla být volána, jakmile se již nepoužívá instance simulátoru.</span><span class="sxs-lookup"><span data-stu-id="2a324-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="2a324-110">Nejlepším způsobem, jak to provést, je zabalení simulátoru v rámci `using` příkazu, jako v předchozím příkladu.</span><span class="sxs-lookup"><span data-stu-id="2a324-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="2a324-111">Sazení</span><span class="sxs-lookup"><span data-stu-id="2a324-111">Seed</span></span>

<span data-ttu-id="2a324-112">`QuantumSimulator`Používá generátor náhodných čísel pro simulaci náhodnosti.</span><span class="sxs-lookup"><span data-stu-id="2a324-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="2a324-113">Pro účely testování je někdy užitečné mít deterministické výsledky.</span><span class="sxs-lookup"><span data-stu-id="2a324-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="2a324-114">To lze provést poskytnutím počáteční hodnoty generátoru náhodných čísel v `QuantumSimulator` konstruktoru konstruktoru pomocí `randomNumberGeneratorSeed` parametru:</span><span class="sxs-lookup"><span data-stu-id="2a324-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="2a324-115">Vlákna</span><span class="sxs-lookup"><span data-stu-id="2a324-115">Threads</span></span>

<span data-ttu-id="2a324-116">`QuantumSimulator`Používá [OpenMP](http://www.openmp.org/) k paralelizovatí lineárního algebraický požadovaného.</span><span class="sxs-lookup"><span data-stu-id="2a324-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="2a324-117">Ve výchozím nastavení používá OpenMP všechna dostupná hardwarová vlákna, což znamená, že programy s malým počtem qubitů budou často běžet pomalu, protože požadovaná koordinace bude převyšovat skutečnou práci.</span><span class="sxs-lookup"><span data-stu-id="2a324-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="2a324-118">To se dá opravit nastavením proměnné prostředí `OMP_NUM_THREADS` na malé číslo.</span><span class="sxs-lookup"><span data-stu-id="2a324-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="2a324-119">Hrubým odhadem je 1 vlákno vhodné až do přibližně 4 qubitů, a pak je dobré další vlákno na každý qubit, i když to velmi závisí na vašem algoritmu.</span><span class="sxs-lookup"><span data-stu-id="2a324-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

