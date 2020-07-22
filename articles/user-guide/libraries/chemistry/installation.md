---
title: 'Instalace knihovny Microsoft Q # chemie'
description: Naučte se, jak nainstalovat knihovnu Microsoft pro seznámení podle složení a jak ji používat s NWChem výpočetními chemie.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 0e870bb3421dddb632375a2fc8633249954f8c8b
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871528"
---
# <a name="chemistry-library-installation"></a>Instalace knihovny chemie

Ukázka [ **MolecularHydrogen** ](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) používá molekulová vstupní data, která jsou konfigurována ručně.
I když je to v malých příkladech jemný, je chemie ve velkém rozsahu vyžaduje Hamiltonians s miliony nebo miliardami podmínek.
Takové Hamiltonians, generované škálovatelnými výpočetními balíčky výpočtů, je příliš velké pro import rukou.

Knihovna chemickéch procesorů pro práci s aplikacemi pro vývoj po závažnosti je navržená tak, aby dobře spolupracovala s výpočetními balíčky, zejména s výpočetními platformami [**NWChem**](http://www.nwchem-sw.org/) , které vyvinula laboratoř pro molekulární vědy (EMSL) v oblasti Tichomoří – severozápadní v národní laboratoři.
Konkrétně [balíček **Microsoft. Broombridge. chemie** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) poskytuje nástroje pro načítání instancí pro načítající se problémy s simulací, které jsou znázorněné ve [schématu](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)a jsou podporované také pro export pomocí nejnovějších verzí NWChem.

Knihovna pro vytváření nenáročného vývojového prostředí poskytuje také nástroj příkazového řádku `qdk-chem` pro převod mezi staršími formáty a [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

Tato část podrobně popisuje, jak používat vývojová prostředí pro práci s NWChem a Broombridge, nebo starší formáty a `qdk-chem` .

## <a name="using-the-quantum-development-kit-with-nwchem"></a>Použití nástroje pro vývoj pro všechna ta v sadě NWChem

Pokud chcete začít pracovat s NWChem společně s vývojovou sadou pro práci s více operačními systémy, použijte jednu z následujících metod:

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

Po zkompilování NWChem ze zdroje můžete spustit skript, který je `yaml_driver` součástí NWChem, a rychle tak vytvářet instance Broombridge ze vstupních balíčku NWChem:

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Tento příkaz vytvoří nový `input.yaml` soubor ve formátu Broombridge v rámci aktuálního adresáře.

### <a name="using-nwchem-with-docker"></a>Použití NWChem s Docker

Předem připravené image pro použití NWChem jsou k dispozici pro různé platformy přes [Docker Hub](https://hub.docker.com).
Pokud chcete začít, postupujte podle pokynů k instalaci Docker pro vaši platformu:

- [Nainstalovat Docker pro Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [Nainstalovat Docker pro macOS](https://docs.docker.com/docker-for-mac/install/)
- [Nainstalovat Docker for Windows 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Pokud používáte Docker for Windows, budete muset sdílet jednotku obsahující dočasný adresář (obvykle se jedná o `C:\` jednotku) pomocí démona Docker. Další podrobnosti najdete v [dokumentaci k Docker](https://docs.docker.com/docker-for-windows/#shared-drives) .

Po instalaci Docker můžete buď použít modul prostředí PowerShell, který je součástí sady pro vývoj všech stavů, pro spuštění bitové kopie, nebo můžete bitovou kopii spustit ručně.
Podrobné informace o použití PowerShellu najdete tady. Pokud chcete použít bitovou kopii Docker ručně, přečtěte si dokumentaci dodanou [s imagí](https://hub.docker.com/r/nwchemorg/nwchem-qc/).

#### <a name="running-nwchem-through-powershell-core"></a>Spuštění NWChem prostřednictvím PowerShell Core

Pokud chcete použít image NWChem Docker s využitím vývojářské sady pro všechna množství, poskytujeme malý modul PowerShellu, který zpracovává přesun souborů v NWChem za vás.
Pokud ještě nemáte nainstalované prostředí PowerShell Core, můžete ho stáhnout z [úložiště PowerShellu na GitHubu](https://github.com/PowerShell/PowerShell#get-powershell).

> [!NOTE]
> PowerShell Core se používá také pro některé ukázky k předvedení interoperability s pracovními postupy pro datové vědy a obchodní analýzy.

Po instalaci prostředí PowerShell Core proveďte import, `InvokeNWChem.psm1` aby příkazy NWChem byly dostupné v aktuální relaci:

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

Tím se příkaz zpřístupní `Convert-NWChemToBroombridge` v aktuální relaci prostředí PowerShell.
Pokud si chcete stáhnout potřebné image z Docker a použít je ke spouštění vstupních balíčku NWChem a k zachycení výstupu do Broombridge, spusťte následující příkaz:

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Tím se vytvoří soubor Broombridge spuštěním NWChem na `input.nw` .
Ve výchozím nastavení bude mít výstup Broombridge stejný název a cestu jako vstupní balíček s `.nw` příponou nahrazenou `.yaml` .
To lze přepsat pomocí `-DestinationPath` parametru do `Convert-NWChemToBroombridge` .
Další informace lze získat pomocí integrované funkce pomoci prostředí PowerShell:

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```

## <a name="using-the-quantum-development-kit-with-qdk-chem"></a>Používání vývojové sady pro práci s využitím`qdk-chem`

K instalaci `qdk-chem` můžete použít .NET Core SDK na příkazovém řádku:

```dotnetcli
dotnet tool install --global Microsoft.Quantum.Chemistry.Tools
```

Po nainstalování `qdk-chem` můžete použít `--help` možnost k získání dalších informací o funkcích nabízených `qdk-chem` nástrojem.

Chcete-li převést na a z Broombridge, můžete použít `qdk-chem convert` příkaz:

```
qdk-chem convert --from fcidump --to broombridge data.fcidump --out data.yml
```

`qdk-chem convert`Příkaz může také přijmout svá data ze standardního vstupu a může zapisovat do standardního výstupu. to je zvláště užitečné v rámci skriptů a pro integraci s nástroji, které exportují do starších formátů.
Příklad v prostředí Bash:

```bash
cat data.fcidump | qdk-convert --from fcidump --to broombridge - > data.yml
```
