---
title: Prostředky pro procesory Estimator – pro vývojová prostředí
description: Přečtěte si o QDK prostředcích Microsoft Estimator, které vyodhadují prostředky potřebné ke spuštění dané instance Q# operace na počítači s více operačními systémy.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1892431c3e332385a5bcefa357eb64a9fac3f381
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992237"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Prostředky QDK (estimatoring Development Kit)

Jak název implikuje, `ResourcesEstimator` Třída odhadne prostředky potřebné ke spuštění dané instance Q# operace v počítači s více operačními systémy. To dosahuje provedením operace s neskutečným simulací stavu počítače s více operačními počítači. z tohoto důvodu odhaduje prostředky pro Q# operace, které používají tisíce qubits, za předpokladu, že klasická část kódu běží v rozumnou dobu.

Prostředky Estimator jsou postavené na [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)pro stav, který poskytuje bohatší sadu metrik a nástrojů pro ladění Q# programů.

## <a name="invoking-and-running-the-resources-estimator"></a>Vyvolání a spuštění prostředků Estimator

Pomocí prostředků Estimator můžete spustit jakoukoli Q# operaci. Další podrobnosti najdete v tématu [způsoby spuštění Q# programu](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>Vyvolání prostředků estimator z C # 

Stejně jako u jiných cílových počítačů nejdřív vytvoříte instanci třídy `ResourceEstimator` a předáte ji jako první parametr metody `Run` příslušné operace.

Na rozdíl od třídy `QuantumSimulator` ale třída `ResourceEstimator` neimplementuje rozhraní <xref:System.IDisposable>, a proto ji není nutné uzavírat příkazem `using`.

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

Jak ukazuje příklad, `ResourcesEstimator` poskytuje `ToTSV()` metodu, která generuje tabulku s hodnotami oddělenými tabulátory (TSV). Tabulku můžete uložit do souboru nebo zobrazit v konzole pro účely analýzy. Následuje ukázkový výstup z předchozího programu:

```output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> `ResourcesEstimator`Instance neresetuje své výpočty při každém spuštění. Použijete-li stejnou instanci pro spuštění jiné operace, agreguje nové výsledky s existujícími výsledky. Pokud potřebujete resetovat výpočty mezi běhy, vytvořte novou instanci pro každé spuštění.

### <a name="invoking-the-resources-estimator-from-python"></a>Vyvolání prostředků estimator z Pythonu

Použijte metodu [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) z knihovny Pythonu s importovanou Q# operací:

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Vyvolání prostředků estimator z příkazového řádku

Při spuštění Q# programu z příkazového řádku použijte parametr **--simulátor** (nebo **-s** ) k určení `ResourcesEstimator` cílového počítače. Následující příkaz spustí program pomocí Estimator prostředků: 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Vyvolání prostředků estimator z poznámkových bloků Juptyer

Q#Pro spuštění operace použijte [odhad](xref:microsoft.quantum.iqsharp.magic-ref.simulate) příkazu I Magic% Q# .

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>Programové načítání odhadovaných dat

Kromě tabulky TSV můžete programově načíst prostředky odhadované během běhu prostřednictvím `Data` vlastnosti prostředků Estimator. `Data`Vlastnost poskytuje `System.DataTable` instanci se dvěma sloupci: `Metric` a `Sum` , indexované názvy metrik.

Následující kód ukazuje, jak načíst a vytisknout celkový počet `QubitClifford` `T` `CNOT` operací využívaných Q# operací:

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a>Hlášené metriky

Prostředky Estimator sledují následující metriky:

|Metrika|Popis|
|----|----|
|__CNOT__    |Počet spuštění `CNOT` operací (označovaný také jako řízené operace Pauli X).|
|__QubitClifford__ |Počet spuštění všech qubitch operací Clifford a Pauli.|
|__Measure__    |Počet spuštění všech měření.  |
|__R__    |Počet spuštění všech rotací s jedním qubit, s výjimkou `T` operací Clifford a Pauli.  |
|__T__    |Počet spuštění `T` operací a jejich sdružených, včetně `T` operací, T_x = H. t. h a T_y = hy. t. hy.  |
|__Úrovní__|Dolní mez pro hloubku okruhu provozu, kterou Q# operace spouští. Ve výchozím nastavení metrika hloubky počítá jenom `T` brány. Další podrobnosti najdete v tématu s [čítačem hloubky](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Width (Šířka)__    |Dolní mez pro maximální počet qubits přidělených během běhu Q# operace. Možná nebude možné dosáhnout současně __hloubkové__ a __šířky__ dolní meze.  |
|__BorrowedWidth__    |Maximální počet qubits, které byly v rámci operace vypůjčeny Q# .  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>Určování pravděpodobnosti výsledků měření

Můžete použít <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> z <xref:microsoft.quantum.diagnostics> oboru názvů k poskytnutí informací o očekávané pravděpodobnosti operace měření. Další informace najdete v části [simulátor trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Viz také

- [Simulátor trasování doby využití](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Kvantový simulátor Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulátor celkového kvantového stavu](xref:microsoft.quantum.machines.full-state-simulator) 