---
title: Od začátku do konce s NWChem | Microsoft Docs
description: Komplexní s NWChem docs
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 8f727ea4599e06b41ced561c624c4e773b9887d9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185813"
---
# <a name="end-to-end-with-nwchem"></a>Konec až do konce s NWChem #

Na této stránce vás seznámíme s příkladem získání počtu bran pro simulaci přípravných počtů, počínaje vstupní balíčkí [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) .
Než budete pokračovat v tomto příkladu, ujistěte se, že jste nainstalovali Docker, a to podle pokynů k [instalaci a ověření](xref:microsoft.quantum.chemistry.concepts.installation).

Další informace:
- [Struktura vstupních balíčku NWChem](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [Příkazy vstupního balíčku pro použití s vývojovou sadou pro všechna ta](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [Instalace knihovny a závislostí chemického složení](xref:microsoft.quantum.chemistry.concepts.installation)
- [Počítání prostředků](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> Tento příklad vyžaduje, aby se spustilo prostředí Windows PowerShell Core.
> Stáhněte si PowerShell Core pro Windows, macOS nebo Linux na https://github.com/PowerShell/PowerShell.

## <a name="importing-required-powershell-modules"></a>Import požadovaných modulů prostředí PowerShell ##

Pokud jste to ještě neudělali, naklonujte [úložiště Microsoft/](https://github.com/Microsoft/Quantum)propracovaného prostředí, které obsahuje ukázky a pomůcky pro práci s vývojovou sadou pro všechna ta.

```powershell
git clone https://github.com/Microsoft/Quantum
```

Po naklonování `Microsoft/Quantum`proveďte `cd` do složky `utilities/` a naimportujte modul PowerShell pro práci s Docker a NWChem:

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> Ve výchozím nastavení systém Windows zabraňuje spuštění jakýchkoli skriptů nebo modulů v rámci bezpečnostního opatření.
> Pokud chcete, aby moduly jako `Invoke-NWChem.psm1` běžely ve Windows, možná budete muset změnit zásady spouštění.
> Uděláte to tak, že spustíte příkaz `Set-ExecutionPolicy`:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> Zásady spouštění se pak po ukončení PowerShellu vrátí.
> Pokud chcete uložit zásady spouštění, použijte jinou hodnotu pro `-Scope`:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

Nyní byste měli mít k dispozici příkaz `Convert-NWChemToBroombridge`:

```powershell
Get-Command -Module InvokeNWChem
```

Dál naimportujeme příkaz `Get-GateCount`, který je k dispozici v ukázce **GetGateCount** .
Úplné podrobnosti najdete v [pokynech uvedených v ukázce](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount).
V dalším kroku spusťte následující příkaz, kde v závislosti na vašem operačním systému nahradíte `<runtime>` buď pomocí `win10-x64`, `osx-x64`nebo `linux-x64`:

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

Nyní byste měli mít k dispozici příkaz `Get-GateCount`:

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>Vstupní balíčky ##

Balíček NWChem Získá textový soubor s názvem _vstupní balíček_ , který určuje, že se má vyřešit problém chemického incidentu, spolu s dalšími parametry, jako je nastavení přidělení paměti.
V tomto příkladu použijeme jednu z předem připravených vstupních balíčku, které jsou součástí NWChem.
Nejdřív naklonujte [úložiště nwchemgit/nwchem](https://github.com/nwchemgit/nwchem):

> [!NOTE]
> Vzhledem k tomu, že se jedná o velmi velké úložiště, můžeme pomocí argumentu `--depth 1` ušetřit velkou šířku pásma a místo na disku.
> To je ale nepovinné.
> Klonování bude pracovat přesně bez `--depth 1`.

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

`nwchemgit/nwchem` úložiště obsahuje řadu vstupních sad, které jsou určené pro použití s vývojovou sadou pro všechna vozidla, uvedená v části [`QA/chem_library_tests` složka](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).
V tomto příkladu použijeme `H4` vstupní balíček:

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

Uvedená molekula je systémem 4 atomy vodíků, které jsou uspořádány v určité geometrii, která závisí na jednom úhlu, parametr `alpha`, jak je uvedeno v názvu `h4_sto6g_alpha.nw` balíčku. H4 je známý [molekulový srovnávací test](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) pro výpočetní chemii od 1970s. Parametr `sto6g` je indikativní, že balíček implementuje reprezentaci s ohledem na Slater typu Orbital, konkrétně reprezentace s ohledem na [základ ši-NG nastavené](https://en.wikipedia.org/wiki/STO-nG_basis_sets) na 6 gaussovskéch základních funkcí. Tento vstupní balíček dále obsahuje několik pokynů pro NWChem tensor (TCE), které přímo NWChem k vytváření informací potřebných pro spolupráci s prostředím pro vývoj všech provozních údajů:

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>Vytváření a využívání výstupu Broombridge z NWChem ##

Teď máme všechno, co potřebujeme k vytváření a využívání dokumentů Broombridge.
Pokud chcete spustit NWChem a vytvořit dokument Broombridge pro vstupní balíček `h4_sto6g_0.000.nw`, spusťte `Convert-NWChemToBroombridge`:

> [!NOTE]
> Při prvním spuštění tohoto příkazu vám Docker stáhne `nwchemorg/nwchem-qc` image za vás.
> V závislosti na rychlosti připojení může to chvíli trvat, což může mít za to, že je možné získat příležitost k navýšení kávy.

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

Tím se vytvoří dokument Broombridge s názvem `h4_sto6g_0.000.yaml`, který můžeme použít s `Get-GateCount`:

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
- Vyzkoušejte si jiné předdefinované vstupní balíčky, třeba změnou parametru `alpha` v `h4_sto6g_alpha.nw`, 
- Zkuste upravit balíčky, a to tak, že upravíte NWChem balíčky přímo, například prozkoumávání `STO-nG` modelů pro různé volby n, 
- Vyzkoušejte jiné předdefinované vstupní balíčky NWChem, které jsou k dispozici na adrese `nwchem/qa/chem_library_tests`,
- Vyzkoušejte sadu předdefinovaných srovnávacích testů Broombridge YAML, které byly vygenerovány z NWChem a jsou k dispozici jako součást [úložiště Microsoft/](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML). Tyto srovnávací testy zahrnují: 
    - malé molekuly, jako je molekulový vodík (H2), beryllium (), lithium Hydride (LiH),
    - větší molekuly, jako je ozon (O3), beta-karoten, cytosine a spousta dalších. 
- Vyzkoušejte grafické šipky front-endu [EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , které vycházejí z rozhraní Microsoft Quantum Development Kit. 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>Vytváření výstupu Broombridge ze šipek EMSL ##

Pokud chcete začít používat EMSL šipky na front-endu, přejděte [tady](https://arrows.emsl.pnnl.gov/api/qsharp_chem)do prohlížeče. 

> [!NOTE]
> Spouštění šipek EMSL ve webovém prohlížeči vyžaduje, aby byl povolený JavaScript. Informace o tom, jak povolit JavaScript v prohlížeči, najdete v těchto [pokynech](https://www.enable-javascript.com/) . 

Nejprve zadejte molekulu do pole dotazu, které uvádí ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

Můžete zadat mnoho molekul podle jejich Colloquial názvu, jako je "Kofein" místo "1, 3, 7-trimethylxanthine". 

Potom klikněte na tlačítko, které uvádí ``theory{qsharp_chem}``. Tím se doplní pole dotazu o instrukci, která umožní, aby se výstup vyexportoval ve formátu Broombridge YAML. 

Nyní se ``Run Arrows``hodiny. V závislosti na velikosti vstupu může to chvíli trvat. Nebo v případě, že konkrétní model již byl vypočítán dříve, lze provést extrémně rychle, protože bude pouze pro vyhledávání v databázi. V obou případech přejdete na novou stránku, která obsahuje spoustu informací o konkrétním běhu NWChem proti balíčku určenému vaším zadáním. 

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

Klikněte na ``download``, která uloží místní kopii s jedinečným názvem souboru, například ``qsharp_chem48443.yaml`` (konkrétní název se bude pro každé spuštění lišit). Tento soubor pak můžete dál zpracovat tak, jak je uvedeno výše, například, s 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
pro získání počtu prostředků. 

Můžete se setkat s 3D tvůrcem molekul, ke kterému se dá dostat z karty ``Arrows Entry - 3D Builder`` na úvodní stránce šipky pro EMSL. Kliknutím na [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D obrázek zobrazené molekuly umožníte jeho úpravu. Můžete přesunout atomy kolem, přetáhnout atomy od sebe, aby se změny mezi molekulové vzdálenosti měnily, přidaly/odebraly atomy atd. Po přidání ``theory{qsharp_chem}`` do pole dotazu můžete pro každou z těchto možností vygenerovat instanci schématu YAML a další prozkoumat ji pomocí knihovny pro složení neBroombridgech hodnot. 
