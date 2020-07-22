---
title: Prostředky pro procesory Estimator – pro vývojová prostředí
description: 'Přečtěte si o QDK prostředcích Microsoft Estimator, které vydávají odhad prostředků potřebných ke spuštění dané instance operace Q # v počítači s více operačními systémy.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 0909a050e89d6295664e54ab63cfda5d407a8f12
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870531"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Prostředky QDK (estimatoring Development Kit)

Jak název implikuje, `ResourcesEstimator` Třída odhadne prostředky potřebné ke spuštění dané instance operace Q # v počítači s více operačními systémy. To dosahuje provedením operace s neskutečným simulací stavu počítače s více operačními počítači. z tohoto důvodu odhaduje prostředky pro operace Q #, které používají tisíce qubits, za předpokladu, že klasická část kódu běží v přiměřené době.

Prostředky Estimator jsou postavené na [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro), který poskytuje bohatší sadu metrik a nástrojů, které vám pomůžou ladit programy Q #.

## <a name="invoking-and-running-the-resources-estimator"></a>Vyvolání a spuštění prostředků Estimator

Pomocí prostředků Estimator můžete spustit jakoukoli operaci Q #. Další podrobnosti najdete v tématu [způsoby spuštění programu Q #](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>Vyvolání prostředků estimator z C # 

Stejně jako u jiných cílových počítačů nejprve vytvoříte instanci `ResourceEstimator` třídy a pak ji předáte jako první parametr `Run` metody operace.

Všimněte si, že na rozdíl od `QuantumSimulator` třídy `ResourceEstimator` třída neimplementuje <xref:System.IDisposable> rozhraní, takže je nemusíte v rámci `using` příkazu uzavřít.

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

Použijte metodu [estimate_resources ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) z knihovny Pythonu s importovanou operací Q #:

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Vyvolání prostředků estimator z příkazového řádku

Při spuštění programu Q # z příkazového řádku použijte parametr **--simulátor** (nebo **-s** ) k určení `ResourcesEstimator` cílového počítače. Následující příkaz spustí program pomocí Estimator prostředků: 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Vyvolání prostředků estimator z poznámkových bloků Juptyer

K provedení operace Q # použijte [odhad příkazu%](xref:microsoft.quantum.iqsharp.magic-ref.simulate) sweetiq # Magic.

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>Programové načítání odhadovaných dat

Kromě tabulky TSV můžete programově načíst prostředky odhadované během běhu prostřednictvím `Data` vlastnosti prostředků Estimator. `Data`Vlastnost poskytuje `System.DataTable` instanci se dvěma sloupci: `Metric` a `Sum` , indexované názvy metrik.

Následující kód ukazuje, jak načíst a vytisknout celkový počet a `QubitClifford` operace, které `T` `CNOT` používá operace Q #:

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
|__Míra__    |Počet spuštění všech měření.  |
|__R__    |Počet spuštění všech rotací s jedním qubit, s výjimkou `T` operací Clifford a Pauli.  |
|__T__    |Počet spuštění `T` operací a jejich sdružených, včetně `T` operací, T_x = H. t. h a T_y = hy. t. hy.  |
|__Úrovní__|Dolní mez pro hloubku okruhu nečinnosti, kterou spouští operace Q #. Ve výchozím nastavení metrika hloubky počítá jenom `T` brány. Další podrobnosti najdete v tématu s [čítačem hloubky](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Width (Šířka)__    |Dolní mez pro maximální počet qubits přidělených během běhu operace Q #. Možná nebude možné dosáhnout současně __hloubkové__ a __šířky__ dolní meze.  |
|__BorrowedWidth__    |Maximální počet qubits, který byl vypůjčen v rámci operace Q #.  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>Zajištění pravděpodobnosti výsledků měření

Můžete použít <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> z <xref:microsoft.quantum.diagnostics> oboru názvů k poskytnutí informací o očekávané pravděpodobnosti operace měření. Další informace najdete v části [simulátor trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Viz také

- [Simulátor trasování doby využití](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Simulátor Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulátor plného stavu pro plný stav](xref:microsoft.quantum.machines.full-state-simulator) 