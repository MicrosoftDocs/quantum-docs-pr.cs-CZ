---
title: Kvantové simulátory a programy v Q#
description: Popisuje kvantové simulátory dostupné jako cílové počítače pro programy v Q#.
author: QuantumWriter
ms.author: v-benbra
ms.date: 6/17/2020
ms.topic: article
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6a2a4bb829301f9db9bd14f3240556a403b9a54f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833421"
---
# <a name="quantum-simulators"></a>Kvantové simulátory

Kvantové simulátory jsou softwarové programy spouštěné na klasických počítačích. Fungují jako *cílové počítače* pro programy v Q# a umožňují spouštět a testovat kvantové programy v prostředí, které předpovídá, jak budou qubity bude reagovat na různé operace. V tomto článku se dozvíte, které kvantové simulátory jsou součástí sady Quantum Development Kit (QDK), a seznámíte se s různými způsoby předání programů v Q# simulátorům, například prostřednictvím příkazového řádku nebo pomocí kódu ovladače napsaného v klasickém jazyce.  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a>Kvantové simulátory sady Quantum Development Kit (QDK)

Kvantový simulátor zodpovídá za poskytnutí implementací kvantových primitiv pro daný algoritmus. Mezi ně patří primitivní operace, jako je `H`, `CNOT` a `Measure`, a také nástroje pro správu a sledování qubitů. Sada QDK obsahuje různé třídy kvantových simulátorů reprezentujících různé modely spouštění pro stejný kvantový algoritmus. 


Každý typ kvantového simulátoru může zajišťovat odlišnou implementaci těchto primitiv. Například [simulátor celkového stavu](xref:microsoft.quantum.machines.full-state-simulator) spouští kvantový algoritmus kompletní simulací [kvantového stavového vektoru](xref:microsoft.quantum.glossary#quantum-state), zatímco [simulátor trasování kvantového počítače](xref:microsoft.quantum.machines.qc-trace-simulator.intro) vůbec nebere aktuální kvantový stav v úvahu. Místo toho sleduje hradla, qubity a další prostředky použité v algoritmu.

### <a name="quantum-machine-classes"></a>Třídy kvantových počítačů

V budoucnu bude sady QDK definovat další třídy kvantových počítačů s podporou dalších typů simulace a s podporou spouštění algoritmů na kvantovém hardwaru. Díky tomu, že umožňujeme neměnnost algoritmů při změnách implementace samotného počítače, usnadňujeme testování a ladění algoritmů v simulaci a následné spouštění na reálném hardwaru s jistotou, že se algoritmus nezměnil.

Sada QDK zahrnuje několik tříd kvantových počítačů, které jsou definované v oboru názvů `Microsoft.Quantum.Simulation.Simulators`.

|Simulátor |Třída|Popis|
|-----|------|---|
|[Simulátor celkového stavu](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | Spouští a ladí kvantové algoritmy a je omezený na zhruba 30 qubitů. |
|[Jednoduchý estimátor prostředků](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | Provádí nejvyšší úroveň analýz prostředků vyžadovaných ke spuštění kvantového algoritmu a podporuje tisíce qubitů.|
|[Trasovací estimátor prostředků](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |Spouští pokročilejší analýzy vyžadovaných prostředků v rámci celého grafu volání a podporuje tisíce qubitů.|
|[Simulátor Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |Simuluje kvantové algoritmy, které jsou omezené na kvantové operace `X` a `CNOT` vícenásobně řízené operace `X` a podporuje miliony qubitů. |

## <a name="invoking-the-quantum-simulator"></a>Vyvolání kvantového simulátoru

V tématu [Způsoby spuštění programu v Q#](xref:microsoft.quantum.guide.host-programs) jsou popsané tři způsoby předávání kódu Q# do kvantového simulátoru: 

* Použití příkazového řádku
* Použití hostitelského programu v Pythonu
* Použití hostitelského programu v C#

Kvantové počítače jsou instancemi normálních tříd .NET, takže jsou vytvořeny vyvoláním jejich konstruktoru stejně jako u jakékoli jiné třídy .NET. Jak to uděláte, závisí na způsobu spuštění programu v Q#.

## <a name="next-steps"></a>Další kroky

* Podrobné informace o vyvolání cílových počítačů pro programy v Q# v různých prostředích najdete v tématu [Způsoby spuštění programu v Q#](xref:microsoft.quantum.guide.host-programs).
