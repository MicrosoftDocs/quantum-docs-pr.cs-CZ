---
title: Prostředky pro procesory Estimator – pro vývojová prostředí
description: Přečtěte si o QDK prostředcích Microsoft Estimator, které vyodhadují prostředky potřebné ke spuštění dané instance Q# operace na počítači s více operačními systémy.
author: anpaz
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3aa94c8b34ad7247fbdeab4bf4dcb96ce746014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847467"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Prostředky QDK (estimatoring Development Kit)

Jak název implikuje, `ResourcesEstimator` Třída odhadne prostředky potřebné ke spuštění dané instance Q# operace v počítači s více operačními systémy. To dosahuje tím, že spustí operaci bez skutečného simulace stavu počítače s více operačními systémy. z tohoto důvodu odhaduje prostředky pro Q# operace, které používají tisíce qubits, za předpokladu, že klasická část kódu běží v rozumnou dobu.

Prostředky Estimator jsou postavené na [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)pro stav, který poskytuje bohatší sadu metrik a nástrojů pro ladění Q# programů.

## <a name="invoking-and-running-the-resources-estimator"></a>Vyvolání a spuštění prostředků Estimator

Pomocí prostředků Estimator můžete spustit jakoukoli Q# operaci. Další podrobnosti najdete v tématu [způsoby spuštění Q# programu](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>Vyvolání prostředků estimator z C # 

Stejně jako u jiných cílových počítačů nejdřív vytvoříte instanci třídy `ResourcesEstimator` a předáte ji jako první parametr metody `Run` příslušné operace.

Na rozdíl od třídy `QuantumSimulator` ale třída `ResourcesEstimator` neimplementuje rozhraní <xref:System.IDisposable>, a proto ji není nutné uzavírat příkazem `using`.

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

|Metric|Popis|
|----|----|
|__CNOT__    |Počet spuštění `CNOT` operací (označovaný také jako řízené operace Pauli X).|
|__QubitClifford__ |Počet spuštění všech qubitch operací Clifford a Pauli.|
|__Measure__    |Počet spuštění všech měření.  |
|__R__    |Počet spuštění všech rotací s jedním qubit, s výjimkou `T` operací Clifford a Pauli.  |
|__T__    |Počet spuštění `T` operací a jejich sdružených, včetně `T` operací, T_x = H. t. h a T_y = hy. t. hy.  |
|__Úrovní__|Hloubka okruhu nečinnosti, kterou spouští Q# operace (viz [níže](#depth-width-and-qubitcount)). Ve výchozím nastavení metrika hloubky počítá jenom `T` brány. Další podrobnosti najdete v tématu s [čítačem hloubky](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Width (Šířka)__|Šířka okruhu nečinnosti, kterou spouští Q# operace (viz [níže](#depth-width-and-qubitcount)). Ve výchozím nastavení metrika hloubky počítá jenom `T` brány. Další podrobnosti najdete v tématu o [čítači šířky](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).   |
|__QubitCount__    |Dolní mez pro maximální počet qubits přidělených během běhu Q# operace. Tato metrika nemusí být kompatibilní s __hloubkou__ (viz níže).  |
|__BorrowedWidth__    |Maximální počet qubits, které byly v rámci operace vypůjčeny Q# .  |


## <a name="depth-width-and-qubitcount"></a>Hloubka, Šířka a QubitCount

Vykázaný odhad hloubky a šířky jsou vzájemně kompatibilní.
(Dřív bylo možné dosáhnout obou čísel, ale pro hloubku a šířku se vyžadovaly různé okruhy.) V současné době je možné obě metriky v této dvojici dosáhnout stejným okruhem.

Nahlásí se následující metriky:

__Hloubka:__ Pro kořenovou operaci – čas potřebný ke spuštění za předpokladu, že se nakonfigurovali časy brány.
Pro operace nazvané nebo následné operace rozdílového času mezi nejnovějším časem dostupnosti qubit na začátku a na konci operace.

__Šířka:__ Pro kořenovou operaci – počet qubits, které se skutečně používají ke spuštění (a operace, kterou volá).
Pro operace nazvané nebo následné operace – kolik dalších qubits bylo použito pro qubits, které již bylo na začátku operace použito.

Upozorňujeme, že znovu použitý qubits nepřispívá k tomuto číslu.
To znamená, že pokud před zahájením operace A zadáte několik qubits, a všechny qubit vyžádané touto operací a (a operace volané z A) byly splněné znovu pomocí dříve vydaných verzí qubits, Šířka operace A je hlášena jako 0. Úspěšně se vypůjčila qubits, která nepřispívá k šířce.

__QubitCount:__ Pro kořenovou operaci – minimální počet qubits, který by byl dostatečný pro provedení této operace (a operací, které se z něho volaly).
Pro operace, které volaly nebo následné operace – minimální počet qubits, který by byl dostatečný pro provedení této operace samostatně. Toto číslo nezahrnuje vstupní qubits. Zahrnuje vypůjčené qubits.

Podporují se dva režimy provozu. Režim je vybrán nastavením QCTraceSimulatorConfiguration. OptimizeDepth.

__OptimizeDepth = false:__ Toto je výchozí režim. QubitManager se doporučuje znovu použít qubits a pak znovu použít vydaný qubits před přidělením nových. __Šířka__ kořenové operace se změní na minimální šířku (s nižší mezí). Je hlášena kompatibilní __Hloubka__ , na které je možné dosáhnout. __QubitCount__ bude stejná jako __Šířka__ pro kořenovou operaci, při které se nepředpokládá žádné výpůjčky.

__OptimizeDepth = true:__ QubitManager se nedoporučuje z qubit opětovného použití a optimalizace založené na heuristikě pro qubit opakované použití se provádí během a po spuštění. __Hloubka__ kořenové operace se změní na minimální hloubku (s nižší mezí). Pro tuto hloubku je uvedena kompatibilní __Šířka__ (je možné dosáhnout současně). Z důvodu optimalizace šířky můžou být brány, které se později v programu naplánovaly, naplánované předtím, než se dříve v programu nastaly, ale qubits se naplánují tak, aby se znovu použily tak, že hloubka zůstane minimální. Jak se qubits opakovaně používají na základě časových hodnot, doporučuje se, aby časy v bráně byly nakonfigurované jako celočíselné hodnoty. Není zaručena optimální __Šířka__ . Další informace najdete v části [Šířka a hloubka](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs)dokumentu White Paper v trasování.

## <a name="providing-the-probability-of-measurement-outcomes"></a>Určování pravděpodobnosti výsledků měření

Můžete použít <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> z <xref:Microsoft.Quantum.Diagnostics> oboru názvů k poskytnutí informací o očekávané pravděpodobnosti operace měření. Další informace najdete v části [simulátor trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Viz také

- [Simulátor trasování doby využití](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Kvantový simulátor Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulátor celkového kvantového stavu](xref:microsoft.quantum.machines.full-state-simulator) 
