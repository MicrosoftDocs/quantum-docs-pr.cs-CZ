---
title: Estimator prostředky pro vývoj pro všechna ta
description: 'Přečtěte si o Estimatorech prostředků, které odhadují prostředky potřebné ke spuštění dané instance operace Q # v počítači s více operačními systémy.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 01d242ed405bdd326f65e534f82ff378a464ee7d
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426881"
---
# <a name="the-resources-estimator-target-machine"></a>Cílový počítač prostředků Estimator

Jak název napovídá, `ResourcesEstimator` odhaduje prostředky potřebné ke spuštění dané instance operace Q # v počítači s operačním systémem.
To dosahuje provedením operace s neskutečným simulací stavu počítače s více operačními počítači. z tohoto důvodu může odhadnout prostředky pro operace Q #, které používají tisíce qubits, pokud klasická část kódu může běžet v rozumnou dobu.

## <a name="usage"></a>Využití

`ResourcesEstimator`Je to pouze jiný typ cílového počítače, takže jej lze použít ke spuštění jakékoli operace Q #. 

Jako jiné cílové počítače, pokud ho chcete použít v hostitelském programu C#, vytvořte instanci a předejte ji jako první parametr `Run` metody operace:

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

Jak ukazuje příklad, `ResourcesEstimator` poskytuje `ToTSV()` metodu pro generování tabulky s hodnotami, které jsou odděleny tabulátory (TSV), které lze uložit do souboru nebo zapsat do konzoly pro účely analýzy. Výstup výše uvedeného programu by měl vypadat přibližně takto:

```Output
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
> Při `ResourcesEstimator` každém spuštění neresetuje své výpočty, pokud se stejná instance používá ke spuštění jiné operace, bude mít za následek agregaci počtů nad stávajícími výsledky.
> Pokud potřebujete resetovat výpočty mezi běhy, vytvořte novou instanci pro každé spuštění.


## <a name="programmatically-retrieving-the-estimated-data"></a>Programové načítání odhadovaných dat

Kromě tabulky TSV lze odhadované prostředky načíst programově prostřednictvím `ResourcesEstimator` `Data` Vlastnosti. `Data`poskytuje `System.DataTable` instanci se dvěma sloupci: `Metric` a `Sum` , indexované názvy metrik.

Následující kód ukazuje, jak načíst a vytisknout celkový počet a `QubitClifford` `T` `CNOT` brány používané operací Q #:

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

Následuje seznam metrik odhadovaných podle `ResourcesEstimator` :

* __CNOT__: počet spuštěných bran Pauli X pro CNOT (označovaný také jako řízená ovládaná brána X).
* __QubitClifford__: počet spuštěných jednotlivých bran qubit Clifford a Pauli.
* __Measure__: počet provedených měření.
* __R__: počet spuštěných jednoduchých qubit otočení s výjimkou bran T, Clifford a Pauli.
* __T__: Počet bran t a jejich sdružených, včetně brány T, T_x = H. t. H a T_y = hy. T. hy, proveden.
* __Hloubka__: Hloubka okruhu nečinnosti, kterou provede operace Q #. Ve výchozím nastavení se tato hloubka počítá jenom u bran T. Podrobnosti najdete v části s informacemi o [čítači hloubky](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .
* __Width__: maximální počet qubits přidělených během provádění operace Q #.
* __BorrowedWidth__: maximální počet qubitsů v rámci operace Q # byl vypůjčen.


## <a name="providing-the-probability-of-measurement-outcomes"></a>Určování pravděpodobnosti výsledků měření

<xref:microsoft.quantum.intrinsic.assertprob>z <xref:microsoft.quantum.intrinsic> oboru názvů lze použít k poskytnutí informací o očekávané pravděpodobnosti měření, které vám pomůžou při provádění programu Q #. Ilustruje to následující příklad:

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

V případě, že `ResourcesEstimator` dojde k `AssertProb` tomu, bude zaznamenáno měření `PauliZ` `source` a `q` měl by být uveden výsledek `Zero` s pravděpodobností 0,5. Při `M` pozdějším spuštění nalezne zaznamenané hodnoty pravděpodobnosti výsledku a `M` vrátí `Zero` nebo `One` s pravděpodobností 0,5.


## <a name="see-also"></a>Viz také

`ResourcesEstimator`Je postaven na [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro)počítačů s procesorem, který poskytuje bohatší sadu metrik, schopnost nahlásit metriky na plný graf volání a funkce, jako je například [Kontrola různých vstupů](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) , pomůžou najít chyby v programech Q #. Další informace najdete v dokumentaci [simulátoru trasování](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .

