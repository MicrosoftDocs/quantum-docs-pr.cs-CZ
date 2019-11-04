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

## <a name="seed"></a>Sazení

`QuantumSimulator` používá generátor náhodných čísel pro simulaci náhodnosti. Pro účely testování je někdy užitečné mít deterministické výsledky. To lze provést poskytnutím počáteční hodnoty generátoru náhodných čísel v konstruktoru `QuantumSimulator`pomocí parametru `randomNumberGeneratorSeed`:

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Vláken

`QuantumSimulator` používá [OpenMP](http://www.openmp.org/) k paralelizovatí lineárního algebraický požadovaného. Ve výchozím nastavení používá nástroj OpenMP všechna dostupná hardwarová vlákna, což znamená, že programy s malým počtem qubits budou často běžet pomalu, protože požadovaná koordinace bude dwarf2 skutečnou práci. To se dá opravit nastavením proměnné prostředí `OMP_NUM_THREADS` na malé číslo. V rámci velmi hrubého pravidla palce je 1 vlákno vhodné až do přibližně 4 qubits a další vlákno na qubit je dobré, i když je to vysoce závislé na vašem algoritmu.

