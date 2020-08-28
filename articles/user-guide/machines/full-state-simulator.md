---
title: Plný stav simulátoru pro náročné na všechna ta – vývojová sada
description: Naučte se spouštět Q# programy v Microsoft Quantum Development Kit úplný stav simulátoru.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: a27cece9858d62814b9d80c47e61c5d7d3b8c885
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992214"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a>Simulátor úplného stavu pro sadu QDK (pro vytváření plně stavů)

QDK poskytuje úplný stav simulátoru, který simuluje počítač s více podsystémy na vašem místním počítači. Pomocí kompletního simulátoru stavu můžete spouštět a ladit algoritmy, které jsou napsané v rámci Q# , a to s využitím až 30 qubits. Úplný stav simulátoru je podobný simulátoru při používání služby Microsoft Research na platformě  [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) .

## <a name="invoking-and-running-the-full-state-simulator"></a>Vyvolání a spuštění simulátoru úplného stavu

Vystavíte plný stav simulátoru prostřednictvím `QuantumSimulator` třídy. Další podrobnosti najdete v tématu [způsoby spuštění Q# programu](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-simulator-from-c"></a>Vyvolání simulátoru z C #

Vytvořte instanci `QuantumSimulator` třídy a pak ji předejte `Run` metodě operace s více poli, spolu s dalšími parametry.
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

Vzhledem k tomu `QuantumSimulator` , že třída implementuje <xref:System.IDisposable> rozhraní, je nutné zavolat `Dispose` metodu, jakmile již nepotřebujete instanci simulátoru. Nejlepším způsobem, jak to provést, je zabalit deklaraci a operace simulátoru do příkazu [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) , který automaticky volá `Dispose` metodu.

### <a name="invoking-the-simulator-from-python"></a>Vyvolání simulátoru z Pythonu

Použijte metodu [simulovat ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) z Q# knihovny Pythonu s importovanou Q# operací:

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a>Vyvolání simulátoru z příkazového řádku

Při spuštění Q# programu z příkazového řádku je úplným výchozím cílovým počítačem simulátor celého stavu. Volitelně můžete pomocí parametru **--simulátor** (nebo **-s** ) určit požadovaný cílový počítač. Oba následující příkazy spouštějí program pomocí kompletního simulátoru. 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a>Vyvolání simulátoru z poznámkových bloků Juptyer

Pomocí příkazu I Q# Magic [% simulovat](xref:microsoft.quantum.iqsharp.magic-ref.simulate) spusťte Q# operaci.

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a>Osazení simulátoru

Ve výchozím nastavení používá simulátor celého stavu generátor náhodných čísel pro simulaci náhodnosti. Pro účely testování je někdy užitečné mít deterministické výsledky. V programu v jazyce C# můžete to dosáhnout poskytnutím počáteční hodnoty generátoru náhodných čísel v `QuantumSimulator` konstruktoru prostřednictvím `randomNumberGeneratorSeed` parametru.

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a>Konfigurace vláken

Simulátor celého stavu používá [OpenMP](http://www.openmp.org/) k paralelizovatí lineárního algebraický. Ve výchozím nastavení používá OpenMP všechna dostupná hardwarová vlákna, což znamená, že programy s malým počtem qubits často běží pomalu, protože koordinace, která je vyžadována Dwarfs skutečnou práci. To můžete opravit nastavením proměnné prostředí `OMP_NUM_THREADS` na malé číslo. Jako pravidlo pro palec nakonfigurujte jedno vlákno pro až čtyři qubits a pak jedno další vlákno na qubit. Je možné, že budete muset proměnnou upravit v závislosti na algoritmu.

## <a name="see-also"></a>Viz také

- [Estimátor kvantových prostředků](xref:microsoft.quantum.machines.resources-estimator)
- [Kvantový simulátor Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulátor trasování doby využití](xref:microsoft.quantum.machines.qc-trace-simulator.intro)