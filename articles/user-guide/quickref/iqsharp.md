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
# <a name="iq-magic-commands"></a><span data-ttu-id="cd3a5-103">Příkazy magic IQ#</span><span class="sxs-lookup"><span data-stu-id="cd3a5-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="cd3a5-104">Obecné</span><span class="sxs-lookup"><span data-stu-id="cd3a5-104">General</span></span>

- <span data-ttu-id="cd3a5-105">`%config`: Nastaví nebo získá předvolby konfigurace.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-105">`%config`: Sets or gets configuration preferences.</span></span>
- <span data-ttu-id="cd3a5-106">`%estimate`: Spustí danou funkci nebo operaci na cílovém počítači QuantumSimulator.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-106">`%estimate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="cd3a5-107">`%lsmagic`: Vrátí seznam všech aktuálně dostupných příkazů Magic.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-107">`%lsmagic`: Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="cd3a5-108">`%package`: Poskytuje možnost načtení balíčku NuGet.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-108">`%package`: Provides the ability to load a Nuget package.</span></span>
- <span data-ttu-id="cd3a5-109">`%performance`: Oznamuje aktuální metriku výkonu pro toto jádro.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-109">`%performance`: Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="cd3a5-110">`%simulate`: Spustí danou funkci nebo operaci na cílovém počítači QuantumSimulator.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-110">`%simulate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="cd3a5-111">`%toffoli`: Spustí danou funkci nebo operaci na cílovém počítači simulátoru ToffoliSimulator.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-111">`%toffoli`: Runs a given function or operation on the ToffoliSimulator simulator target machine.</span></span>
- <span data-ttu-id="cd3a5-112">`%who`: Poskytuje akce související s aktuálním pracovním prostorem.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-112">`%who`: Provides actions related to the current workspace.</span></span>
- <span data-ttu-id="cd3a5-113">`%workspace`: Vrátí seznam všech operací a funkcí definovaných v aktuální relaci, a to buď interaktivně, nebo načten z aktuálního pracovního prostoru.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-113">`%workspace`: Returns a list of all operations and functions defined in the current session, either interactively or loaded from the current workspace.</span></span>

### <a name="chemistry"></a><span data-ttu-id="cd3a5-114">Složení</span><span class="sxs-lookup"><span data-stu-id="cd3a5-114">Chemistry</span></span>

- <span data-ttu-id="cd3a5-115">`%chemistry.broombridge`: Načte a vrátí reprezentaci Broombridge elektronické struktury z daného souboru. yaml.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-115">`%chemistry.broombridge`: Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="cd3a5-116">`%chemistry.encode`: Zakóduje Hamiltonian fermion do formátu příspotřebního příznaku Q #.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-116">`%chemistry.encode`: Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="cd3a5-117">`%chemistry.fh.add_terms`: Přidá výrazy do fermion Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-117">`%chemistry.fh.add_terms`: Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="cd3a5-118">`%chemistry.fh.load`: Načte Hamiltonian fermion pro problém s elektronickými strukturami.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-118">`%chemistry.fh.load`: Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="cd3a5-119">Problém se načte ze souboru nebo předá jako argument.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-119">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="cd3a5-120">`%chemistry.inputstate.load`: Načte problém elektronické struktury Broombridge a vrátí vybraný vstupní stav.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-120">`%chemistry.inputstate.load`: Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="from-microsoftquantumkatas-package"></a><span data-ttu-id="cd3a5-121">Z balíčku Microsoft. proKatasme</span><span class="sxs-lookup"><span data-stu-id="cd3a5-121">From Microsoft.Quantum.Katas package</span></span>

- <span data-ttu-id="cd3a5-122">`%kata`: Provede jeden test a oznámí, zda byl test úspěšně úspěšný.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-122">`%kata`: Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="cd3a5-123">`%check_kata`: Kontroluje referenční implementaci pro jeden test Kata.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-123">`%check_kata`: Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="cd3a5-124">Konkrétně nahrazuje referenční implementaci pro jeden úkol na buňku a oznamuje, zda byl test úspěšně úspěšný.</span><span class="sxs-lookup"><span data-stu-id="cd3a5-124">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
