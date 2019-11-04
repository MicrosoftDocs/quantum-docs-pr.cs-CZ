---
title: Kvantové simulátory a hostitelské aplikace | Microsoft Docs
description: Tento článek popisuje, jak ovládat kvantové simulátory z klasického jazyka .NET, obvykle buď C#, nebo Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442217"
---
# <a name="quantum-simulators-and-host-applications"></a>Kvantové simulátory a hostitelské aplikace

## <a name="what-youll-learn"></a>Co se naučíte

> [!div class="checklist"]
> * Jak se spouštějí kvantové algoritmy
> * Jaké kvantové simulátory jsou součástí této verze
> * Jak napsat ovladač v C# pro váš kvantový algoritmus

## <a name="the-quantum-development-kit-execution-model"></a>Spouštěcí model sady Quantum Development Kit

V článku [Jak napsat kvantový program](xref:microsoft.quantum.write-program) jsme spustili kvantový algoritmus tak, že jsme předali objekt `QuantumSimulator` metodě `Run` třídy algoritmu.
Třída `QuantumSimulator` provádí kvantový algoritmus úplnou simulací kvantového stavového vektoru, což je ideální pro spouštění a testování programu `Teleport`.
Další informace o kvantových stavových vektorech najdete v článku [Průvodce koncepty](xref:microsoft.quantum.concepts.intro).

Ke spuštění kvantového algoritmu se dají použít i jiné cílové počítače.
Počítač odpovídá za poskytnutí implementací kvantových primitiv pro daný algoritmus.
Mezi ně patří primitivní operace, jako je H, CNOT a M (měření), a také nástroje pro správu a sledování qubitů.
Různé třídy kvantových počítačů představují různé modely spuštění pro stejný kvantový algoritmus.

Každý typ kvantového počítače může zajišťovat odlišnou implementaci těchto primitiv.
Například trasovací simulátor kvantového počítače, zahrnutý ve vývojové sadě, neprovádí vůbec žádnou simulaci.
Místo toho sleduje hradla, qubity a další prostředky použité v algoritmu.

### <a name="quantum-machines"></a>Kvantové počítače

V budoucnu budeme definovat další třídy kvantových počítačů s podporou jiných typů simulace a s podporou spouštění algoritmů na topologických kvantových počítačích.
Díky tomu, že umožňujeme neměnnost algoritmů při změnách implementace samotného počítače, usnadňujeme testování a ladění algoritmů v simulaci a následné spouštění na reálném hardwaru s jistotou, že se algoritmus nezměnil.

### <a name="whats-included-in-this-release"></a>Co je zahrnuto v této verzi

Tato vydaná verze kvantové vývojové sady zahrnuje několik tříd kvantových počítačů.
Všechny jsou definovány v oboru názvů `Microsoft.Quantum.Simulation.Simulators`.

* [Úplný simulátor stavových vektorů](xref:microsoft.quantum.machines.full-state-simulator), třída `QuantumSimulator`.
* [Jednoduchý estimátor prostředků](xref:microsoft.quantum.machines.resources-estimator), třída `ResourcesEstimator`, umožňuje na nejvyšší úrovni analýzu prostředků vyžadovaných ke spuštění kvantového algoritmu.
* [Trasovací estimátor prostředků](xref:microsoft.quantum.machines.qc-trace-simulator.intro), třída `QCTraceSimulator` umožňuje pokročilejší analýzu vyžadovaných prostředků v rámci celého grafu volání.
* [Simulátor Toffoli](xref:microsoft.quantum.machines.toffoli-simulator), třída `ToffoliSimulator`.

## <a name="writing-a-host-application"></a>Vytvoření hostitelské aplikace

V článku [Jak napsat kvantový program](xref:microsoft.quantum.write-program) jsme pro náš teleportovací algoritmus napsali jednoduchý ovladač v jazyce C#. Ovladač C# má 4 hlavní úkoly:

* Sestavení cílového počítače
* Výpočet všech argumentů vyžadovaných pro kvantový algoritmus
* Spuštění kvantového algoritmu v simulátoru
* Zpracování výsledku operace

Teď se podíváme na každý krok podrobněji.

### <a name="constructing-the-target-machine"></a>Sestavení cílového počítače

Kvantové počítače jsou instancemi normálních tříd .NET, takže jsou vytvořeny vyvoláním jejich konstruktoru stejně jako u jakékoli jiné třídy .NET.
Některé simulátory, včetně `QuantumSimulator`, implementují rozhraní .NET <xref:System.IDisposable?displayProperty=nameWithType>, a proto je třeba je zabalit do příkazu C# `using`.

### <a name="computing-arguments-for-the-algorithm"></a>Výpočet argumentů pro algoritmus

V našem příkladu `Teleport` jsme vypočítali některé poměrně umělé argumenty, které předáme našemu kvantovému algoritmu.
Častěji ale kvantový algoritmus vyžaduje mnoho vstupních dat a je jednodušší poskytnout mu je z klasického ovladače.

Například u chemických simulací vyžaduje kvantový algoritmus velké tabulky integrálů molekulárních orbitálních interakcí.
Obecně se načítají ze souboru, který je k dispozici při spuštění algoritmu.
Protože jazyk Q# nemá mechanismy pro přístup k systému souborů, je shromáždění takovýchto dat a jejich předání metodě `Run` kvantového algoritmu úlohou pro klasický ovladač.

Další případ, kdy klasický ovladač hraje klíčovou roli, je u variačních metod.
V této třídě algoritmů se kvantový stav připravuje na základě klasických parametrů, a teprve tento stav se pak použije k výpočtu požadované výsledné hodnoty.
Parametry se pak upraví na základě určitého gradientního algoritmu nebo strojového učení a kvantový výpočet se spustí znovu.
V takových případech je nejlepší implementovat samotný gradientní algoritmus čistě klasicky a volat ho z klasického ovladače. Výsledky gradientního algoritmu se pak předají k dalšímu výpočtu kvantovému algoritmu.

### <a name="running-the-quantum-algorithm"></a>Spuštění kvantového algoritmu

Tato část je obecně velmi přímočará.
Každá operace Q# se zkompiluje do třídy, která poskytuje statickou metodu `Run`.
Argumenty se této metodě předávají jako zploštěná řazená kolekce argumentů samotné operace, plus dodatečný první argument, který specifikuje požadovaný simulátor. Pro operaci, která očekává pojmenovanou řazenou kolekci členů typu `(a: String, (b: Double, c: Double))` bude mít její zploštěný protějšek typ `(String a, Double b, Double c)`.


Při předávání argumentů metodě `Run` je třeba brát v úvahu určité detaily:

* Pole musí být vždy zabalena v objektu `Microsoft.Quantum.Simulation.Core.QArray<T>`.
    Třída `QArray` má konstruktor, kterému je možné předat jakoukoli uspořádanou kolekci vhodných objektů (`IEnumerable<T>`).
* Prázdná řazená kolekce členů, `()` v jazyce Q#, je v C# reprezentována výrazem `QVoid.Instance`.
* Neprázdné řazené kolekce členů jsou reprezentovány jako .NET instance `ValueTuple`.
* Uživatelem definované typy se v Q# předávají jako jejich základní typy.
* Chcete-li metodě `Run` předat operaci nebo funkci, musíte získat instanci třídy operace nebo funkce pomocí metody `Get<>` simulátoru.

### <a name="processing-the-results"></a>Zpracování výsledků

Výsledek kvantového výpočtu je vrácen v návratové hodnotě metody `Run`.
Metoda `Run` se spouští asynchronně a proto vrací instanci třídy <xref:System.Threading.Tasks.Task`1>.
Samotné výsledky operace je možné získat několika způsoby. Nejjednodušší je použít z třídy `Task` vlastnost [`Result`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
ale fungovat budou i jiné techniky, třeba použití metody [`Wait`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) nebo klíčového slova C# [`await`](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await).

Stejně jako u argumentů jsou v Q# řazené kolekce členů reprezentovány jako instance `ValueTuple` a pole jako instance `QArray`.
Uživatelem definované typy se vracejí jako jejich základní typy.
Prázdná řazená kolekce členů `()` se vrací jako instance třídy `QVoid`.

Mnoho kvantových algoritmů vyžaduje k získání smysluplné odpovědi podstatné zpracování výsledků.
Například kvantová část Shorova algoritmu je jen začátkem náročného výpočtu, který najde samotný rozklad čísla.

Ve většině případů je jednodušší a snazší tento typ výpočtů provádět v klasickém ovladači.
Pouze klasický ovladač může tyto výsledky zobrazit uživateli a zapsat je na disk.
Klasický ovladač bude mít také přístup k analytickým knihovnám a dalším matematickým funkcím, které nejsou v Q# dostupné.


## <a name="failures"></a>Selhání

Když se při provádění operace narazí na příkaz `fail` jazyka Q#, vyvolá se výjimka `ExecutionFailException`.

Vzhledem k použití třídy `System.Task` v metodě `Run` se výjimka vyvolaná v důsledku příkazu `fail` zabalí do objektu `System.AggregateException`.
Chcete-li zjistit skutečnou příčinu selhání, je třeba iterovat přes  
`InnerExceptions` objektu `AggregateException`, například:

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a>Další klasické jazyky

Uvedené příklady jsou sice v C#, F# a Pythonu, ale Quantum Development Kit podporuje psaní klasických hostitelů i v jiných jazycích.
Například když budete chtít napsat hostitelský program ve Visual Basicu, [není to žádný problém](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).
