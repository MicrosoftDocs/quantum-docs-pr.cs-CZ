---
title: Příkazy magic IQ#
description: 'Rychlá referenční stránka pro příkazy SWEETIQ # Magic s poznámkovým blokům Q # Jupyter'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431015"
---
# <a name="iq-magic-commands"></a>Příkazy magic IQ#

### <a name="general"></a>Obecné

- `%config`: Nastaví nebo získá předvolby konfigurace.
- `%estimate`: Spustí danou funkci nebo operaci na cílovém počítači QuantumSimulator.
- `%lsmagic`: Vrátí seznam všech aktuálně dostupných příkazů Magic.
- `%package`: Poskytuje možnost načtení balíčku NuGet.
- `%performance`: Oznamuje aktuální metriku výkonu pro toto jádro.
- `%simulate`: Spustí danou funkci nebo operaci na cílovém počítači QuantumSimulator.
- `%toffoli`: Spustí danou funkci nebo operaci na cílovém počítači simulátoru ToffoliSimulator.
- `%who`: Poskytuje akce související s aktuálním pracovním prostorem.
- `%workspace`: Vrátí seznam všech operací a funkcí definovaných v aktuální relaci, a to buď interaktivně, nebo načten z aktuálního pracovního prostoru.

### <a name="chemistry"></a>Složení

- `%chemistry.broombridge`: Načte a vrátí reprezentaci Broombridge elektronické struktury z daného souboru. yaml.
- `%chemistry.encode`: Zakóduje Hamiltonian fermion do formátu příspotřebního příznaku Q #.
- `%chemistry.fh.add_terms`: Přidá výrazy do fermion Hamiltonian.
- `%chemistry.fh.load`: Načte Hamiltonian fermion pro problém s elektronickými strukturami. Problém se načte ze souboru nebo předá jako argument.
- `%chemistry.inputstate.load`: Načte problém elektronické struktury Broombridge a vrátí vybraný vstupní stav.

### <a name="from-microsoftquantumkatas-package"></a>Z balíčku Microsoft. proKatasme

- `%kata`: Provede jeden test a oznámí, zda byl test úspěšně úspěšný.
- `%check_kata`: Kontroluje referenční implementaci pro jeden test Kata.
    Konkrétně nahrazuje referenční implementaci pro jeden úkol na buňku a oznamuje, zda byl test úspěšně úspěšný.
