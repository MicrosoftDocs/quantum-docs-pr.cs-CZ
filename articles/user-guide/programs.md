---
title: 'Q # Introdution'
description: 'Rychlé představení programů v programu Q #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233484"
---
# <a name="q-quantum-programming-language"></a>Q # programový jazyk

Vše, co potřebujete znát o programovacím jazyce Q #, je podrobně popsané v [Průvodci jazyk q #](xref:microsoft.quantum.qsharp.index). Stejně jako cokoli ostatní, je náš [proces návrhu](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) v našem jazyce open source a Vítejte na příspěvcích.
Další informace o základech a motivaci za Q # najdete v tématu [Proč musíme q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).  
Q # se dodává jako součást QDK (pro vývoj na více instancí), kde najdete rychlý přehled, [co je to QDK?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Co je program pro vydaných hodnot?

Program pro práci s více částmi se může zobrazit jako konkrétní sada klasických podprocesů, které při volání provádějí výpočet prostřednictvím práce se systémem program napsaný v Q # nemodeluje přímo stav nečinnosti, ale místo toho popisuje, jak počítač klasického ovládacího prvku komunikuje s qubits.
To nám umožní zcela nezávislá informace o tom, co *je* stav bez nároku na každém cílovém počítači, což může mít různé interpretace v závislosti na počítači. 

Důležité je, že Q # nemá možnost introspect se do stavu qubit nebo jiných vlastností příslušnosti, což zaručuje, že program Q # může být fyzicky spuštěný v počítači s taktem.
Místo toho může program volat operace, jako je například [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) extrakce klasických informací z qubit.

Po přidělení může být qubit předán operacím a funkcím, které jsou také označovány jako *volatelné*. V některých případech to znamená, že program Q # může s qubit provádět. Všechny přímé akce ve stavu qubit jsou definovány *vnitřními* voláními, jako jsou například [`X`](xref:Microsoft.Quantum.Intrinsic.X) a [`H`](xref:Microsoft.Quantum.Intrinsic.H) – tj. volat, jejichž implementace nejsou definovány v rámci Q #, ale místo toho jsou definovány cílovým počítačem. Díky *tomu* se tyto operace skutečně provádějí jenom v cílovém počítači, který používáme ke spuštění konkrétního programu Q #.

Pokud například spustíte program na našem simulátoru, simulátor provede odpovídající matematické operace do simulovaného systému pro [nastavování](xref:microsoft.quantum.machines.full-state-simulator).
Ale pokud je cílový počítač skutečným počítačem, který se blíží k budoucnosti, volání takových operací v Q # nasměruje počítač s příznakem do provozu, aby provedl odpovídající *reálné* operace v *reálném* systému doby provozu (například přesně časované laserové Pulse).

Program Q # znovu sloučí tyto operace, jak jsou definovány cílovým počítačem, a vytvoří tak nové operace vyšší úrovně, které budou vyjadřovat výpočetní procesory.
V tomto případě Q # usnadňuje vyjádření logiky podkladových a hybridních životních stojí – klasických algoritmů, a to i v souvislosti se strukturou cílového počítače nebo simulátoru.

Jednoduchým příkladem je následující program, který přiděluje jeden qubit ve stavu $ \ket {0} $, pak na něj použije operaci Hadamard `H` a měří výsledek na `PauliZ` základě.

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

Naše hlavní množství [katas](https://github.com/microsoft/QuantumKatas#introduction) poskytují dobrý úvod k [výpočetním koncepcím](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) , jako jsou běžné operace s více operačními systémy a způsobu manipulace s qubits. Další příklady najdete také v [vnitřních operacích a funkcích](xref:microsoft.quantum.libraries.standard.prelude).



