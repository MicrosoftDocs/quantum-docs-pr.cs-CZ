---
title: Úplný simulátor pro vývoj všech stavů v sadě Microsoft Docs
description: Přehled plného stavu simulátoru pro vývoj všech stavů v sadě Microsoft 's Development Kit
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: ab0e65765d27e301a59948d7c02105a523022e68
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184674"
---
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="87db2-103">Úplný simulátor pro vývoj všech stavů v sadě</span><span class="sxs-lookup"><span data-stu-id="87db2-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="87db2-104">Sada pro vývoj všech stavových prostředí poskytuje úplný stav simulátoru, který se podobá [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) od Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="87db2-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="87db2-105">Tento simulátor se dá použít ke spouštění a ladění algoritmů pro plnění a napsaných v Q # ve vašem počítači.</span><span class="sxs-lookup"><span data-stu-id="87db2-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="87db2-106">Tento simulátor při přístavování se zveřejňuje prostřednictvím `QuantumSimulator` třídy.</span><span class="sxs-lookup"><span data-stu-id="87db2-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="87db2-107">Chcete-li použít simulátor, jednoduše vytvořte instanci této třídy a předejte ji do `Run` metody operace s přístupnými událostmi, které chcete spustit spolu se zbytkem parametrů:</span><span class="sxs-lookup"><span data-stu-id="87db2-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="87db2-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="87db2-108">IDisposable</span></span>

<span data-ttu-id="87db2-109">Třída `QuantumSimulator` implementuje <xref:System.IDisposable>, takže by měla být volána metoda `Dispose`, jakmile se již instance simulátoru nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="87db2-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="87db2-110">Nejlepším způsobem, jak to provést, je zabalení simulátoru v rámci příkazu `using`, jako v příkladu výše.</span><span class="sxs-lookup"><span data-stu-id="87db2-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="87db2-111">Sazení</span><span class="sxs-lookup"><span data-stu-id="87db2-111">Seed</span></span>

<span data-ttu-id="87db2-112">`QuantumSimulator` používá generátor náhodných čísel pro simulaci náhodnosti.</span><span class="sxs-lookup"><span data-stu-id="87db2-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="87db2-113">Pro účely testování je někdy užitečné mít deterministické výsledky.</span><span class="sxs-lookup"><span data-stu-id="87db2-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="87db2-114">To lze provést poskytnutím počáteční hodnoty generátoru náhodných čísel v konstruktoru `QuantumSimulator`pomocí parametru `randomNumberGeneratorSeed`:</span><span class="sxs-lookup"><span data-stu-id="87db2-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="87db2-115">Vláken</span><span class="sxs-lookup"><span data-stu-id="87db2-115">Threads</span></span>

<span data-ttu-id="87db2-116">`QuantumSimulator` používá [OpenMP](http://www.openmp.org/) k paralelizovatí lineárního algebraický požadovaného.</span><span class="sxs-lookup"><span data-stu-id="87db2-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="87db2-117">Ve výchozím nastavení používá nástroj OpenMP všechna dostupná hardwarová vlákna, což znamená, že programy s malým počtem qubits budou často běžet pomalu, protože požadovaná koordinace bude dwarf2 skutečnou práci.</span><span class="sxs-lookup"><span data-stu-id="87db2-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="87db2-118">To se dá opravit nastavením proměnné prostředí `OMP_NUM_THREADS` na malé číslo.</span><span class="sxs-lookup"><span data-stu-id="87db2-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="87db2-119">V rámci velmi hrubého pravidla palce je 1 vlákno vhodné až do přibližně 4 qubits a další vlákno na qubit je dobré, i když je to vysoce závislé na vašem algoritmu.</span><span class="sxs-lookup"><span data-stu-id="87db2-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

