---
title: Simulátor plného stavu
description: 'Zjistěte, jak spustit programy Q # v simulátoru Microsoft Quantum Development Kit úplný stav.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906113"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Úplný simulátor pro vývoj všech stavů v sadě

Sada pro vývoj všech stavových prostředí poskytuje úplný stav simulátoru, který se podobá [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) od Microsoft Research.
Tento simulátor se dá použít ke spouštění a ladění algoritmů pro plnění a napsaných v Q # ve vašem počítači.

Tento simulátor při přístavování se zveřejňuje prostřednictvím `QuantumSimulator` třídy. Chcete-li použít simulátor, jednoduše vytvořte instanci této třídy a předejte ji do `Run` metody operace s přístupnými událostmi, které chcete spustit spolu se zbytkem parametrů:

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

Třída `QuantumSimulator` implementuje <xref:System.IDisposable>, takže by měla být volána metoda `Dispose`, jakmile se již instance simulátoru nepoužívá. Nejlepším způsobem, jak to provést, je zabalení simulátoru v rámci příkazu `using`, jako v příkladu výše.

## <a name="seed"></a>sazení

`QuantumSimulator` používá generátor náhodných čísel pro simulaci náhodnosti. Pro účely testování je někdy užitečné mít deterministické výsledky. To lze provést poskytnutím počáteční hodnoty generátoru náhodných čísel v konstruktoru `QuantumSimulator`pomocí parametru `randomNumberGeneratorSeed`:

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Vlákna

`QuantumSimulator` používá [OpenMP](http://www.openmp.org/) k paralelizovatí lineárního algebraický požadovaného. Ve výchozím nastavení používá OpenMP všechna dostupná hardwarová vlákna, což znamená, že programy s malým počtem qubitů budou často běžet pomalu, protože požadovaná koordinace bude převyšovat skutečnou práci. To se dá opravit nastavením proměnné prostředí `OMP_NUM_THREADS` na malé číslo. Hrubým odhadem je 1 vlákno vhodné až do přibližně 4 qubitů, a pak je dobré další vlákno na každý qubit, i když to velmi závisí na vašem algoritmu.

