---
title: Vytvoření kvantového generátoru náhodných čísel
description: Sestavte Q# projekt, který ukazuje základní koncepty, jako je například nadpozice, vytvořením generátor náhodných čísel.
author: bromeg
ms.author: megbrow
ms.date: 10/25/2019
ms.topic: tutorial
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: f36db426a8f0479580117cce44a67ad3a053d5de
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856352"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>Kurz: Implementace kvantového generátoru náhodných čísel v jazyku Q\#

Jednoduchý příklad algoritmu, který je v systému napsaný, Q# je generátor náhodných čísel. Tento algoritmus využívá charakter kvantové mechaniky a vytváří náhodné číslo.

## <a name="prerequisites"></a>Požadavky

- Sada Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Vytvořte Q# projekt pro [ Q# aplikaci](xref:microsoft.quantum.install.standalone), pomocí [hostitelského programu Pythonu](xref:microsoft.quantum.install.python)nebo [hostitelského programu jazyka C#](xref:microsoft.quantum.install.cs).

## <a name="write-a-no-locq-operation"></a>Zápis Q# operace

### <a name="no-locq-operation-code"></a>Q# kód operace

1. Obsah souboru Program.qs nahraďte následujícím kódem:

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

Jak je uvedeno v článku [Principy kvantových výpočtů](xref:microsoft.quantum.overview.understanding), qubit je jednotka kvantových informací, která může být v superpozici různých stavů. Při změření může mít qubit jenom hodnotu 0 nebo 1. Před měřením ale stav qubit představuje pravděpodobnost čtení 0 nebo 1 s měřením. Tento pravděpodobnostní stav se nazývá superpozice. Na základě této pravděpodobnosti můžeme generovat náhodná čísla.

V naší Q# operaci zavádíme `Qubit` datový typ, který je nativní pro Q# . Typ `Qubit` je možné přidělit jen pomocí příkazu `using`. Qubit je po přidělení vždycky ve stavu `Zero`. 

Pomocí operace `H` můžeme `Qubit` převést do superpozice. Ke změření qubitu a přečtení jeho hodnoty použijte vnitřní operaci `M`.

Když `Qubit` převedeme do superpozice a změříme ho, bude výsledkem při každém vyvolání kódu jiná hodnota.

Když je pro `Qubit` zrušeno přidělení, musí pro něj být znovu nastaven stav `Zero`, jinak simulátor ohlásí běhovou chybu. Snadný způsob, jak toho dosáhnout, je vyvolat operaci `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Vizualizace kódu pomocí Blochovy koule

Severní pól na Blochově kouli představuje klasickou hodnotu **0** a jižní pól představuje klasickou hodnotu **1**. Každá superpozice může být reprezentována bodem na kouli (reprezentovaný šipkou). Čím blíž je konec šipky k pólu, tím vyšší je pravděpodobnost, že se qubit při změření převede na klasickou hodnotu přiřazenou k příslušnému pólu. Příklad: Stav qubitu reprezentovaného červenou šipkou na obrázku níže má vyšší pravděpodobnost, že při změření bude mít hodnotu **0**.

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

Tuto reprezentaci můžeme použít k vizualizaci toho, co kód dělá:

* Nejdřív začneme s qubitem inicializovaným ve stavu **0** a pomocí funkce `H` vytvoříme superpozici, ve které jsou pravděpodobnosti hodnot **0** a **1** stejné.

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* Pak qubit změříme a výstup uložíme:

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

Jelikož je výsledek měření zcela náhodný, získali jsme náhodný bit. Pokud chceme generovat celá čísla, můžeme tuto operaci volat vícekrát. Pokud například budeme tuto operaci volat třikrát a získáme tři náhodné bity, můžeme generovat náhodná 3-bitová čísla (tedy náhodné číslo v rozsahu 0 až 7).


## <a name="creating-a-complete-random-number-generator"></a>Vytvoření kompletního generátoru náhodných čísel

Teď, když máme Q# operaci, která generuje náhodné bity, můžeme ji použít k sestavení kompletního generátoru náhodných čísel. Můžeme použít Q# aplikaci nebo použít hostitelský program.



### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a>[Q# aplikace se sadou Visual Studio nebo Visual Studio Code](#tab/tabid-qsharp)

Chcete-li vytvořit úplnou Q# aplikaci, přidejte do programu následující vstupní bod Q# : 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

Program spustí operaci nebo funkci označenou `@EntryPoint()` atributem simulátoru nebo Estimator prostředku v závislosti na konfiguraci projektu a možnostech příkazového řádku.

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

V aplikaci Visual Studio stačí stisknout kombinaci kláves CTRL + F5 ke spuštění skriptu.

V editoru VS Code při prvním použití sestavte Program.qs zadáním následujícího příkazu na terminálu:

```dotnetcli
dotnet build
```

Pro následná spuštění není potřeba ho sestavovat znovu. Pokud ho chcete spustit, zadejte následující příkaz a stiskněte Enter:

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-prompt"></a>[Python s Visual Studio Code nebo příkazový řádek](#tab/tabid-python)

Chcete-li spustit nový Q# program z Pythonu, uložte následující kód jako `host.py` :

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

Hostitelský program Pythonu pak můžete spustit z příkazového řádku:

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[C# s využitím editoru Visual Studio Code nebo sady Visual Studio](#tab/tabid-csharp)

Chcete-li spustit nový Q# program z c#, upravte `Driver.cs` tak, aby obsahovalo následující kód C#:

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

Pak můžete spustit hostitelský program C# z příkazového řádku (v aplikaci Visual Studio byste měli stisknout klávesu F5):

```bash
$ dotnet run
The random number generated is 42
```

***
