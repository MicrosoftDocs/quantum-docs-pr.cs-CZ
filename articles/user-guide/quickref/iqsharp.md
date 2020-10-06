---
title: Q#Příkazy Magic
description: Rychlá referenční stránka pro Q# příkazy Magic s Q# Jupyter poznámkovým blokem
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4549afb84bf0084160079e3cef3a7f94dffcda3e
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771348"
---
# <a name="ino-locq-magic-commands"></a>Q#Příkazy Magic

### <a name="general"></a>Obecné

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Umožňuje nastavení nebo dotazování možností konfigurace.
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Spustí danou funkci nebo operaci na cílovém počítači ResourcesEstimator.
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Vrátí seznam všech aktuálně dostupných příkazů Magic.
- [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen): Vypíše aktuálně otevřené obory názvů a jejich aliasy.
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Poskytuje možnost načtení balíčku NuGet.
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Oznamuje aktuální metriku výkonu pro toto jádro.
- [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project): Poskytuje možnost zobrazit nebo přidat Q# odkazy na projekt. 
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Spustí danou funkci nebo operaci na cílovém počítači QuantumSimulator.
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Spustí danou funkci nebo operaci na cílovém počítači ToffoliSimulator.
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Zobrazí seznam Q# operací, které jsou k dispozici v aktuální relaci.
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Poskytuje akce související s aktuálním pracovním prostorem.

### <a name="azure-quantum-integration"></a>Integrace Azure pro všechna úložiště

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Připojuje se k pracovnímu prostoru Azure ve službě Azure nebo zobrazuje stav aktuálního připojení.
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Odešle úlohu do pracovního prostoru Azure pro stav a čeká na dokončení.
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Zobrazí seznam úloh v aktuálním pracovním prostoru Azure.
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Zobrazí výsledky úlohy v aktuálním pracovním prostoru Azure ve službě Azure.
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Zobrazí stav úlohy v aktuálním pracovním prostoru Azure.
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Odešle úlohu do pracovního prostoru Azure ve službě.
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Nastaví nebo zobrazí aktivní cíl spuštění pro Q# odeslání úlohy v pracovním prostoru Azure ve službě Azure.

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>Chemie (z balíčku Microsoft.. chemie)

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Načte a vrátí reprezentaci Broombridge elektronické struktury z daného souboru. yaml.
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Kóduje fermion Hamiltonian na formát, který je spotřební přísystémem Q# .
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Přidá výrazy do fermion Hamiltonian.
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Načte Hamiltonian fermion pro problém s elektronickými strukturami. Problém se načte ze souboru nebo předá jako argument.
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Načte problém elektronické struktury Broombridge a vrátí vybraný vstupní stav.

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas (z balíčku Microsoft.. katas)

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Spustí jeden test a oznámí, zda byl test úspěšně úspěšný.
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Kontroluje referenční implementaci pro jeden test Kata.
    Konkrétně nahrazuje referenční implementaci pro jeden úkol na buňku a oznamuje, zda byl test úspěšně úspěšný.
