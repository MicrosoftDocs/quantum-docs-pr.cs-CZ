---
title: Ukázkový program pro NWChem
description: Pomocí NWChem Input balíčku si můžete projít příkladem získání počtu bran pro simulaci pro práci s více instancemi.
author: cgranade
ms.author: chgranad
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
no-loc:
- Q#
- $$v
ms.openlocfilehash: 986ff2c2ff144c57bd01ddeea0467d0168fd9334
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835753"
---
# <a name="end-to-end-with-nwchem"></a>Kompletní použití NWChem #

V tomto článku se seznámíte s příkladem získání počtu bran pro simulaci přípravných počtů, počínaje vstupní balíčkí [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) .
Než budete pokračovat v tomto příkladu, ujistěte se, že jste nainstalovali Docker, a to podle pokynů k [instalaci a ověření](xref:microsoft.quantum.chemistry.concepts.installation).

Další informace najdete tady:
- [Struktura vstupních balíčku NWChem](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [Příkazy vstupního balíčku pro použití s vývojovou sadou pro všechna ta](https://github.com/nwchemgit/nwchem/tree/main/contrib/quasar)
- [Instalace knihovny a závislostí chemického složení](xref:microsoft.quantum.chemistry.concepts.installation)
- [Počítání prostředků](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> Tento příklad vyžaduje, aby se spustilo prostředí Windows PowerShell Core.
> Stáhněte si PowerShell Core pro Windows, macOS nebo Linux na https://github.com/PowerShell/PowerShell .

## <a name="importing-required-powershell-modules"></a>Import požadovaných modulů prostředí PowerShell ##

Pokud jste to ještě neudělali, naklonujte [úložiště Microsoft/](https://github.com/Microsoft/Quantum)propracovaného prostředí, které obsahuje ukázky a pomůcky pro práci s vývojovou sadou pro všechna ta.

```powershell
git clone https://github.com/Microsoft/Quantum
```

Po klonování `Microsoft/Quantum` proveďte `cd` do `utilities/` složky a importujte modul PowerShell pro práci s Docker a NWChem:

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> Ve výchozím nastavení systém Windows zabraňuje spuštění všech skriptů nebo modulů v rámci bezpečnostního opatření.
> Aby bylo možné moduly, jako je například `Invoke-NWChem.psm1` spouštění v systému Windows, je třeba zásady změnit.
> Uděláte to tak, že spustíte `Set-ExecutionPolicy` příkaz:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> Zásada se vrátí po ukončení PowerShellu.
> Pokud chcete zásady uložit, použijte jinou hodnotu pro `-Scope` :
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

Nyní byste měli mít `Convert-NWChemToBroombridge` k dispozici příkaz:

```powershell
Get-Command -Module InvokeNWChem
```

Dále naimportujeme příkaz, který `Get-GateCount` je součástí ukázky **GetGateCount** .
Úplné podrobnosti najdete v [pokynech uvedených v ukázce](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount).
Dále spusťte následující příkaz, v `<runtime>` `win10-x64` `osx-x64` `linux-x64` závislosti na operačním systému nahraďte hodnotu, nebo.

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

Nyní byste měli mít `Get-GateCount` k dispozici příkaz:

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>Vstupní balíčky ##

Balíček NWChem Získá textový soubor s názvem _vstupní balíček_ , který určuje, že se má vyřešit problém chemického incidentu, spolu s dalšími parametry, jako je nastavení přidělení paměti.
V tomto příkladu použijeme jednu z předem připravených vstupních balíčku, které jsou součástí NWChem.
Nejdřív naklonujte [úložiště nwchemgit/nwchem](https://github.com/nwchemgit/nwchem):

> [!NOTE]
> Vzhledem k tomu, že se jedná o velmi velké úložiště, můžeme pomocí argumentu ušetřit celou šířku pásma a místo na disku `--depth 1` .
> To je ale nepovinné.
> Klonování bude fungovat přesně bez `--depth 1` .

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

`nwchemgit/nwchem`Úložiště se dodává s řadou vstupních sad, které jsou určené pro použití s vývojovou sadou pro všechna vozidla, uvedená v části [ `QA/chem_library_tests` Složka](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests).
V tomto příkladu použijeme `H4` vstupní balíček:

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

Uvedená molekula je systém o 4 atomech vodíků, které jsou uspořádány v určité geometrii, která závisí na jednom úhlu, parametr, který je `alpha` uveden v názvu `h4_sto6g_alpha.nw` balíčku. H4 je známý [molekulový srovnávací test](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) pro výpočetní chemii od 1970s. Parametr `sto6g` je indikativní, že balíček implementuje reprezentaci s ohledem na Slater typu Orbital, konkrétně reprezentace s ohledem na [základnu ši-NG nastavená](https://en.wikipedia.org/wiki/STO-nG_basis_sets) na 6 gaussovskéch základních funkcí. Tento vstupní balíček dále obsahuje několik pokynů pro NWChem tensor (TCE), které přímo NWChem k vytváření informací potřebných pro spolupráci s prostředím pro vývoj všech provozních údajů:

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>Vytváření a využívání výstupu Broombridge z NWChem ##

Teď máte všechno, co potřebujete k tvorbě a využívání dokumentů Broombridge.
Chcete-li spustit NWChem a vytvořit dokument Broombridge pro `h4_sto6g_0.000.nw` vstupní balíček, spusťte příkaz `Convert-NWChemToBroombridge` :

> [!NOTE]
> Při prvním spuštění tohoto příkazu vám Docker stáhne `nwchemorg/nwchem-qc` Image za vás.
> V závislosti na rychlosti připojení může to chvíli trvat, což může mít za to, že je možné získat příležitost k navýšení kávy.

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

Tím se vytvoří dokument Broombridge s názvem `h4_sto6g_0.000.yaml` , který můžete použít s `Get-GateCount` :

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

Nyní byste měli vidět výstup konzoly, který obsahuje odhad prostředků, jako je například T-Count, počet rotací, počet CNOT a další. pro různé metody simulace počtu procesorů:

```powershell 
IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Trotter
TCount              : 0
RotationsCount      : 92
CNOTCount           : 520
ElapsedMilliseconds : 327

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Qubitization
TCount              : 438
RotationsCount      : 516
CNOTCount           : 2150
ElapsedMilliseconds : 528

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Optimized Qubitization
TCount              : 3540
RotationsCount      : 18
CNOTCount           : 7932
ElapsedMilliseconds : 721
```

Existuje spousta věcí, které můžete dělat tady: 
- Vyzkoušejte si jiné předdefinované vstupní balíčky, např. změnou parametru `alpha` v `h4_sto6g_alpha.nw` , 
- Zkuste upravit balíčky, a to tak, že přímo upravíte balíčky NWChem, třeba zkoumání `STO-nG` modelů různých možností n, 
- Vyzkoušejte jiné předdefinované vstupní balíčky NWChem, které jsou k dispozici `nwchem/qa/chem_library_tests` na adrese.
- Vyzkoušejte sadu předdefinovaných srovnávacích testů Broombridge YAML, které byly vygenerovány z NWChem a jsou k dispozici jako součást [úložiště Microsoft/](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML). Tyto srovnávací testy zahrnují: 
    - malé molekuly, jako je molekulový vodík (H2), beryllium (), lithium Hydride (LiH),
    - větší molekuly, jako je ozon (O3), beta-karoten, cytosine a spousta dalších. 
- Vyzkoušejte grafické šipky front-endu [EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , které vycházejí z rozhraní Microsoft Quantum Development Kit. 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>Vytváření výstupu Broombridge ze šipek EMSL ##

Pokud chcete začít používat EMSL šipky na front-endu, přejděte [tady](https://arrows.emsl.pnnl.gov/api/qsharp_chem)do prohlížeče. 

> [!NOTE]
> Spouštění šipek EMSL ve webovém prohlížeči vyžaduje, aby byl povolený JavaScript. Informace o tom, jak povolit JavaScript v prohlížeči, najdete v těchto [pokynech](https://www.enable-javascript.com/) . 

Nejprve zadejte molekulu do pole dotazu, které říká ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

Můžete zadat mnoho molekul podle jejich Colloquial názvu, jako je "Kofein" místo "1, 3, 7-trimethylxanthine". 

Potom klikněte na tlačítko, které uvádí ``theory{qsharp_chem}`` . Tím se doplní pole dotazu o instrukci, která umožní, aby se výstup vyexportoval ve formátu Broombridge YAML. 

Nyní se hodiny přihlásí ``Run Arrows`` . V závislosti na velikosti vstupu může to chvíli trvat. Nebo v případě, že konkrétní model již byl vypočítán dříve, lze provést extrémně rychle, protože bude pouze pro vyhledávání v databázi. V obou případech přejdete na novou stránku, která obsahuje spoustu informací o konkrétním běhu NWChem proti balíčku určenému vaším zadáním. 

Soubor Broombridge YAML můžete stáhnout a uložit z části, která začíná následující hlavičkou: 
```powershell
+==================================================+
||              Molecular Calculation             ||
+==================================================+

Id     = 48443

NWOutput = Link to NWChem Output (download)

Datafiles:
qsharp_chem.yaml-2018-10-23-14:37:42 (download)
...
```

Klikněte na ``download`` , který uloží místní kopii s jedinečným názvem souboru, třeba ``qsharp_chem48443.yaml`` (konkrétní název se bude pro každé spuštění lišit). Tento soubor pak můžete dál zpracovat tak, jak je uvedeno výše, například, s 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
pro získání počtu prostředků. 

Můžete se setkat s 3D tvůrcem molekul, ke kterému se dá dostat z ``Arrows Entry - 3D Builder`` karty na úvodní stránce šipky EMSL. Kliknutím na [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D obrázek zobrazené molekuly umožníte jeho úpravu. Můžete přesunout atomy kolem, přetáhnout atomy od sebe, aby se změny mezi molekulové vzdálenosti měnily, přidaly/odebraly atomy atd. Po přidání do pole dotazu můžete pro každou z těchto možností ``theory{qsharp_chem}`` vygenerovat instanci schématu BROOMBRIDGE YAML a dále ji prozkoumat pomocí knihovny pro složení množství času. 
