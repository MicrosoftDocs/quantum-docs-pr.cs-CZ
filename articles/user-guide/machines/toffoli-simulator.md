---
title: Simulátor Toffolich procesorů – pro vývojová prostředí
description: Přečtěte si o simulátoru Microsoft QDKe Toffoli, ke speciálnímu simulátoru pro každý účel, který je možné použít s miliony qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: a6ceee592e628215511ec83475d9e25bf54674f7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870613"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a>Simulátor QDK (Toffoliing Development Kit)

Simulátor QDK Toffoli je simulátor pro zvláštní účely s omezeným oborem a podporuje pouze `X` operace, `CNOT` a s více řízenými neřízenými hodnotami `X` . K dispozici je všechny klasické logiky a výpočty.

I když je simulátor Toffoliější s omezenou funkčností než [simulátor úplného stavu](xref:microsoft.quantum.machines.full-state-simulator), je výhodou možnost simulovat mnohem více qubits. Simulátor Toffoli se dá použít s miliony qubits, zatímco kompletní simulátor stavu je omezený na přibližně 30 qubits. To je užitečné, například pomocí Oracle pro vyhodnocení logických funkcí – můžou být implementovány pomocí omezené sady podporovaných algoritmů a testovány na velký počet qubits.

## <a name="invoking-the-toffoli-simulator"></a>Vyvolání simulátoru Toffoli

Simulátor Toffoli vystavíte prostřednictvím `ToffoliSimulator` třídy. Další podrobnosti najdete v tématu [způsoby spuštění programu Q #](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-toffoli-simulator-from-c"></a>Vyvolání simulátoru Toffoli z C #

Stejně jako u jiných cílových počítačů nejprve vytvoříte instanci `ToffoliSimulator` třídy a pak ji předáte jako první parametr `Run` metody operace.

Všimněte si, že na rozdíl od `QuantumSimulator` třídy `ToffoliSimulator` třída neimplementuje <xref:System.IDisposable> rozhraní, takže je nemusíte v rámci `using` příkazu uzavřít.

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>Vyvolání simulátoru Toffoli z Pythonu

Použijte metodu [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) z knihovny Pythonu s importovanou operací Q #:

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>Volání simulátoru Toffoli z příkazového řádku

Při spuštění programu Q # z příkazového řádku použijte parametr **--simulátor** (nebo **-s** ) k zadání cílového počítače simulátoru Toffoli. Následující příkaz spustí program pomocí Estimator prostředků: 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>Vyvolání simulátoru Toffoli z notebooků Juptyer

Pomocí příkazu SWEETIQ # Magic [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) spusťte operaci Q #.

```
%toffoli myOperation
```

## <a name="supported-operations"></a>Podporované operace

Simulátor Toffoli podporuje:

* Rotace a exponentiated Pauls, například `R` a `Exp` , když se výsledná operace rovná `X` nebo matice identity.
* Operace měření a [vyhodnocení](xref:microsoft.quantum.diagnostics.assertmeasurement) , ale pouze v Pauli `Z` . Všimněte si, že pravděpodobnost operace měření je vždy **rovna 0** nebo **1**. simulátor Toffoli neobsahuje náhodnost.
* `DumpMachine`a `DumpRegister` funkce.
Obě funkce výstupují aktuální `Z` stav jednotlivých qubit, jeden qubit na řádek.

## <a name="specifying-the-number-of-qubits"></a>Určení počtu qubits

Ve výchozím nastavení `ToffoliSimulator` instance přiděluje prostor pro 65 536 qubits.
Pokud váš algoritmus vyžaduje více qubits, můžete určit počet qubit zadáním hodnoty `qubitCount` parametru konstruktoru.
Každý další qubit vyžaduje jenom jeden bajt paměti, takže se neúčtují žádné významné náklady na přeodhadování počtu qubits, které budete potřebovat.

Příklad:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a>Viz také

- [Estimatory prostředků](xref:microsoft.quantum.machines.resources-estimator)
- [Simulátor trasování doby využití](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Simulátor plného stavu pro plný stav](xref:microsoft.quantum.machines.full-state-simulator) 