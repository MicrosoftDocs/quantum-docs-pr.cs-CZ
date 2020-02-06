---
title: Instalace a ověření knihovny chemie | Microsoft Docs
description: Instalace a ověření knihovny chemie
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: de13d1814821c612ed74a347dc8ffb5881063576
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036470"
---
# <a name="chemistry-library-installation-and-validation"></a>Instalace a ověření knihovny chemie

Sada pro vývoj pro všechna ta umožňuje, aby se pro každou z [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) balíčku NuGet podporovaly aplikace.
Stejně jako u jiných balíčků NuGet je jednoduché přidat knihovnu chemie do projektu.

**Visual Studio 2019:** Pokud používáte sadu Visual Studio 2019, můžete přidat balíčky pro práci pomocí Správce balíčků NuGet.
Správce balíčků otevřete tak, že kliknete pravým tlačítkem na projekt, do kterého chcete přidat knihovnu chemie, a vyberete spravovat balíčky NuGet..., jako na snímku obrazovky níže.

![](~/media/vs2017-nuget-manage-packages.png)

Na kartě Procházet vyhledejte název balíčku "Microsoft. chemie".

> [!NOTE]
> Ujistěte se, že zaškrtnete políčko zahrnout předběžné verze.

![](~/media/vs2017-nuget-package-search.png)

Zobrazí se seznam balíčků, které jsou k dispozici ke stažení.
V levém podokně klikněte na Microsoft. proruku. chemie, v pravém podokně vyberte nejnovější verzi předběžného vydání a klikněte na nainstalovat:

![](~/media/vs2017-nuget-select-chem.png)

Další podrobnosti najdete v příručce k [uživatelskému rozhraní Správce balíčků](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Alternativně můžete použít konzolu Správce balíčků a přidat do projektu knihovnu chemie pro práci s rozhraním příkazového řádku.

![](~/media/vs2017-nuget-console-menu.png)

V konzole správce balíčků spusťte následující příkaz:

```
Install-Package Microsoft.Quantum.Chemistry
```

Další podrobnosti najdete v [Průvodci konzolou správce balíčků](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Příkazový řádek nebo Visual Studio Code:** Pomocí příkazového řádku na svém vlastním nebo z Visual Studio Code můžete pomocí příkazu `dotnet` přidat do projektu odkaz na balíček NuGet:

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a>Ověření instalace 

Podobně jako v ostatních částech vývojové sady pro práci s více operačními systémy obsahuje knihovna složení množství plně dokumentovaných ukázek, které vám pomůžou rychle začít pracovat.
K otestování instalace pomocí těchto ukázek naklonujte [hlavní úložiště ukázek](https://github.com/Microsoft/Quantum)a pak spusťte jednu z ukázek.  Například pro spuštění ukázky [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) :

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

Chcete-li ověřit instalaci knihovny pro stanovení doby platnosti, pomocí Microsoft Visual Studio po klonování úložiště:
    1. Ve složce chemická aplikace otevřete řešení ChemistrySamples. sln.  
    2. Vyberte Samples/1. Jednoduché molekuly/MolecularHydrogen jako spouštěný projekt.
    3. Stiskněte klávesu F5 ke spuštění ukázky pro odhad fáze nákladů na molekulový vodík.

Další informace o odhadu hodnot úrovní energie najdete v tématu [získání odhadů úrovně energie](xref:microsoft.quantum.chemistry.examples.energyestimate) .   


## <a name="using-the-quantum-development-kit-with-nwchem"></a>Použití nástroje pro vývoj pro všechna ta v sadě NWChem ##

Ukázka MolecularHydrogen používá molekulová vstupní data, která jsou konfigurována ručně.  I když je to v malých příkladech jemné, je chemie ve velkém měřítku vyžadovat Hamiltonians s miliony nebo miliardami podmínek. Takové Hamiltonians, generované škálovatelnými výpočetními složeními, jsou příliš velké pro import rukou. 

Knihovna chemickéch procesorů pro práci s aplikacemi pro vývoj po závažnosti je navržená tak, aby dobře spolupracovala s výpočetními balíčky, zejména s výpočetními platformami [**NWChem**](http://www.nwchem-sw.org/) , které vyvinula laboratoř pro molekulární vědy (EMSL) v oblasti Tichomoří – severozápadní v národní laboratoři.
Konkrétně balíček `Microsoft.Quantum.Chemistry` poskytuje nástroje pro načítání instancí chemického plnění, které představují problémy s simulací ve [schématu Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), podporované také pro export pomocí nejnovějších verzí NWChem.

Pokud chcete začít pracovat s NWChem společně s vývojovou sadou pro práci s více operačními systémy, doporučujeme jednu z následujících metod:
- Začněte používat stávající soubory Broombridge dodávané s ukázkami v [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).
- Pro Microsoft Quantum Development Kit, což je webový front-end pro NWChem, můžete pomocí [Tvůrce šipek EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem) vygenerovat nové Broombridge naformátované molekulární vstupní soubory.  
- Použijte k spuštění NWChem [Image Docker](https://hub.docker.com/r/nwchemorg/nwchem-qc/) , kterou poskytuje PNNL, nebo
- [Zkompilujte NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) pro vaši platformu.

Další informace o tom, jak pracovat s NWChem pro chemické modely a analyzovat pomocí knihovny programu pro vytváření více koncových procesorů, najdete v článku [komplexním s NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) .

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>Začínáme s používáním souborů Broombridge poskytovaných v ukázkách

Ve složce [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) v úložišti pro všechny procesory pro vývoj z více procesorů najdete datové soubory molekul s Broombridge formátem.  

V jednoduchém příkladu můžete použít ukázku knihovny chemie, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) načíst Hamiltonian z jednoho ze souborů Broombridge a provést odhady brány pro simulaci nezatížených nákladů algorigthms:

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

Další informace o tom, jak zadat molekuly reprezentované Broombridge schématem, najdete v tématu [načtení Hamiltonian ze souboru](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .  

Další informace o odhadu prostředků najdete v tématu [získání počtu prostředků](xref:microsoft.quantum.chemistry.examples.resourcecounts) .  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>Začínáme s používáním tvůrce šipek EMSL

Šipky EMSL jsou nástroj, který pomocí NWChem a chemických výpočetních databází generuje data molekul.  [EMSL šipky Builder pro Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) umožňuje zadat svůj model pomocí několika tvůrců molekulárního modelu a vygenerovat datový Broombridge, který bude používat sada pro vývoj všech počítačů.  

Na stránce EMSL klikněte na kartu [' instuctions '] a použijte pokyny [' jednoduché příklady] pro generování Broombridge souborů.  Pak zkuste spustit [' GetGateCount '] pro zobrazení odhadů prostředků u těchto molekul.

### <a name="installing-nwchem-from-source"></a>Instalace NWChem ze zdroje

Úplné pokyny k instalaci NWChem ze zdroje [jsou k dispozici prostřednictvím PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).

> [!TIP]
> Pokud chcete používat NWChem ze systému Windows 10, je systém Windows pro Linux skvělý volbou.
> Po instalaci [Ubuntu 18,04 LTS pro Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)spusťte `ubuntu18.04` z oblíbeného terminálu a podle pokynů uvedených výše nainstalujte NWChem ze zdroje.

Po zkompilování NWChem ze zdroje můžete spustit skript `yaml_driver`, který poskytuje NWChem pro rychlé vytváření instancí Broombridge ze vstupních balíčku NWChem:

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Tento příkaz vytvoří nový soubor `input.yaml` ve formátu Broombridge v rámci aktuálního adresáře.

### <a name="using-nwchem-with-docker"></a>Použití NWChem s Docker

Předem připravené image pro použití NWChem jsou k dispozici pro různé platformy přes [Docker Hub](https://hub.docker.com).
Pokud chcete začít, postupujte podle pokynů k instalaci Docker pro vaši platformu:

- [Nainstalovat Docker pro Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [Nainstalovat Docker pro macOS](https://docs.docker.com/docker-for-mac/install/)
- [Nainstalovat Docker for Windows 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Pokud používáte Docker for Windows, budete muset sdílet jednotku obsahující dočasný adresář (obvykle se jedná o `C:\` disk) pomocí démona Docker. Další podrobnosti najdete v [dokumentaci k Docker](https://docs.docker.com/docker-for-windows/#shared-drives) .

Po instalaci Docker můžete buď použít modul prostředí PowerShell, který je součástí sady pro vývoj všech stavů, pro spuštění bitové kopie, nebo můžete bitovou kopii spustit ručně.
Podrobné informace o použití PowerShellu najdete tady. Pokud chcete použít bitovou kopii Docker ručně, přečtěte si dokumentaci dodanou [s imagí](https://hub.docker.com/r/nwchemorg/nwchem-qc/).

#### <a name="running-nwchem-through-powershell-core"></a>Spuštění NWChem prostřednictvím PowerShell Core

Pokud chcete použít image NWChem Docker s využitím vývojářské sady pro všechna množství, poskytujeme malý modul PowerShellu, který zpracovává přesun souborů v NWChem za vás.
Pokud ještě nemáte nainstalované prostředí PowerShell Core, můžete ho stáhnout z [úložiště PowerShellu na GitHubu](https://github.com/PowerShell/PowerShell#get-powershell).

> [!NOTE]
> PowerShell Core se používá také pro některé ukázky k předvedení interoperability s pracovními postupy pro datové vědy a obchodní analýzy.

Po instalaci prostředí PowerShell Core importujte `InvokeNWChem.psm1`, aby byly v aktuální relaci dostupné příkazy NWChem:

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

Tím se v aktuální relaci prostředí PowerShell zpřístupní příkaz `Convert-NWChemToBroombridge`.
Pokud si chcete stáhnout potřebné image z Docker a použít je ke spouštění vstupních balíčku NWChem a k zachycení výstupu do Broombridge, spusťte následující příkaz:

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Tím se vytvoří soubor Broombridge spuštěním NWChem na `input.nw`.
Ve výchozím nastavení bude mít výstup Broombridge stejný název a cestu jako vstupní balíček s příponou `.nw` nahrazenou `.yaml`.
To lze přepsat pomocí parametru `-DestinationPath` pro `Convert-NWChemToBroombridge`.
Další informace lze získat pomocí integrované funkce pomoci prostředí PowerShell:

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
