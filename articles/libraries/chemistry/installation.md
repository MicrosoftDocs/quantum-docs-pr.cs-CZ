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
# <a name="chemistry-library-installation-and-validation"></a><span data-ttu-id="a4a7a-103">Instalace a ověření knihovny chemie</span><span class="sxs-lookup"><span data-stu-id="a4a7a-103">Chemistry Library Installation and Validation</span></span>

<span data-ttu-id="a4a7a-104">Sada pro vývoj pro všechna ta umožňuje, aby se pro každou z [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) balíčku NuGet podporovaly aplikace.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-104">The Quantum Development Kit provides support for quantum chemistry applications through the [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet package.</span></span>
<span data-ttu-id="a4a7a-105">Stejně jako u jiných balíčků NuGet je jednoduché přidat knihovnu chemie do projektu.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-105">As with other NuGet packages, it's straightforward to add the chemistry library to your project.</span></span>

<span data-ttu-id="a4a7a-106">**Visual Studio 2019:** Pokud používáte sadu Visual Studio 2019, můžete přidat balíčky pro práci pomocí Správce balíčků NuGet.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-106">**Visual Studio 2019:** If you are using Visual Studio 2019, you can add the quantum chemistry packages by using the NuGet Package Manager.</span></span>
<span data-ttu-id="a4a7a-107">Správce balíčků otevřete tak, že kliknete pravým tlačítkem na projekt, do kterého chcete přidat knihovnu chemie, a vyberete spravovat balíčky NuGet..., jako na snímku obrazovky níže.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-107">To open the Package Manager, right-click on the project you'd like to add the chemistry library to and select "Manage NuGet Packages...," as in the screenshot below.</span></span>

![](~/media/vs2017-nuget-manage-packages.png)

<span data-ttu-id="a4a7a-108">Na kartě Procházet vyhledejte název balíčku "Microsoft. chemie".</span><span class="sxs-lookup"><span data-stu-id="a4a7a-108">From the Browse tab, search for the package name "Microsoft.Quantum.Chemistry."</span></span>

> [!NOTE]
> <span data-ttu-id="a4a7a-109">Ujistěte se, že zaškrtnete políčko zahrnout předběžné verze.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-109">Make sure to tick "Include prerelease."</span></span>

![](~/media/vs2017-nuget-package-search.png)

<span data-ttu-id="a4a7a-110">Zobrazí se seznam balíčků, které jsou k dispozici ke stažení.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-110">This will list the packages available for download.</span></span>
<span data-ttu-id="a4a7a-111">V levém podokně klikněte na Microsoft. proruku. chemie, v pravém podokně vyberte nejnovější verzi předběžného vydání a klikněte na nainstalovat:</span><span class="sxs-lookup"><span data-stu-id="a4a7a-111">Click on the "Microsoft.Quantum.Chemistry on the left-hand pane, select the latest pre-release version on the right-hand pane, and click "Install":</span></span>

![](~/media/vs2017-nuget-select-chem.png)

<span data-ttu-id="a4a7a-112">Další podrobnosti najdete v příručce k [uživatelskému rozhraní Správce balíčků](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="a4a7a-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="a4a7a-113">Alternativně můžete použít konzolu Správce balíčků a přidat do projektu knihovnu chemie pro práci s rozhraním příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-113">Alternatively, you can use the Package Manager Console to add the quantum chemistry library to your project with a command line interface.</span></span>

![](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="a4a7a-114">V konzole správce balíčků spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="a4a7a-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Chemistry
```

<span data-ttu-id="a4a7a-115">Další podrobnosti najdete v [Průvodci konzolou správce balíčků](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="a4a7a-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="a4a7a-116">**Příkazový řádek nebo Visual Studio Code:** Pomocí příkazového řádku na svém vlastním nebo z Visual Studio Code můžete pomocí příkazu `dotnet` přidat do projektu odkaz na balíček NuGet:</span><span class="sxs-lookup"><span data-stu-id="a4a7a-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a><span data-ttu-id="a4a7a-117">Ověření instalace</span><span class="sxs-lookup"><span data-stu-id="a4a7a-117">Verifying Your Installation</span></span> 

<span data-ttu-id="a4a7a-118">Podobně jako v ostatních částech vývojové sady pro práci s více operačními systémy obsahuje knihovna složení množství plně dokumentovaných ukázek, které vám pomůžou rychle začít pracovat.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-118">Like the rest of the Quantum Development Kit, the quantum chemistry library comes with a number of fully documented samples to help you get up and running quickly.</span></span>
<span data-ttu-id="a4a7a-119">K otestování instalace pomocí těchto ukázek naklonujte [hlavní úložiště ukázek](https://github.com/Microsoft/Quantum)a pak spusťte jednu z ukázek.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum), then run one of the samples.</span></span>  <span data-ttu-id="a4a7a-120">Například pro spuštění ukázky [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) :</span><span class="sxs-lookup"><span data-stu-id="a4a7a-120">For example, to run the [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

<span data-ttu-id="a4a7a-121">Chcete-li ověřit instalaci knihovny pro stanovení doby platnosti, pomocí Microsoft Visual Studio po klonování úložiště:</span><span class="sxs-lookup"><span data-stu-id="a4a7a-121">To verify the installation of the quantum chemistry library using Microsoft Visual Studio after cloning the repository:</span></span>
    1. <span data-ttu-id="a4a7a-122">Ve složce chemická aplikace otevřete řešení ChemistrySamples. sln.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-122">Open the ChemistrySamples.sln solution in the Chemistry folder.</span></span>  
    2. <span data-ttu-id="a4a7a-123">Vyberte Samples/1.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-123">Select Samples/1.</span></span> <span data-ttu-id="a4a7a-124">Jednoduché molekuly/MolecularHydrogen jako spouštěný projekt.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-124">Simple Molecules/MolecularHydrogen as the StartUp project.</span></span>
    3. <span data-ttu-id="a4a7a-125">Stiskněte klávesu F5 ke spuštění ukázky pro odhad fáze nákladů na molekulový vodík.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-125">Press F5 to run the molecular Hydrogen quantum phase estimation demo.</span></span>

<span data-ttu-id="a4a7a-126">Další informace o odhadu hodnot úrovní energie najdete v tématu [získání odhadů úrovně energie](xref:microsoft.quantum.chemistry.examples.energyestimate) .</span><span class="sxs-lookup"><span data-stu-id="a4a7a-126">See [Obtaining energy level estimates](xref:microsoft.quantum.chemistry.examples.energyestimate) for more information on estimating the values of energy levels.</span></span>   


## <a name="using-the-quantum-development-kit-with-nwchem"></a><span data-ttu-id="a4a7a-127">Použití nástroje pro vývoj pro všechna ta v sadě NWChem</span><span class="sxs-lookup"><span data-stu-id="a4a7a-127">Using the Quantum Development Kit with NWChem</span></span> ##

<span data-ttu-id="a4a7a-128">Ukázka MolecularHydrogen používá molekulová vstupní data, která jsou konfigurována ručně.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-128">The MolecularHydrogen sample uses molecular input data that is manually configured.</span></span>  <span data-ttu-id="a4a7a-129">I když je to v malých příkladech jemné, je chemie ve velkém měřítku vyžadovat Hamiltonians s miliony nebo miliardami podmínek.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-129">While this is fine for small examples, quantum chemistry at scale require Hamiltonians with millions or billions of terms.</span></span> <span data-ttu-id="a4a7a-130">Takové Hamiltonians, generované škálovatelnými výpočetními složeními, jsou příliš velké pro import rukou.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-130">Such Hamiltonians, generated by scalable computational chemistry packages are too large to import by hand.</span></span> 

<span data-ttu-id="a4a7a-131">Knihovna chemickéch procesorů pro práci s aplikacemi pro vývoj po závažnosti je navržená tak, aby dobře spolupracovala s výpočetními balíčky, zejména s výpočetními platformami [**NWChem**](http://www.nwchem-sw.org/) , které vyvinula laboratoř pro molekulární vědy (EMSL) v oblasti Tichomoří – severozápadní v národní laboratoři.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-131">The quantum chemistry library for the Quantum Development Kit is designed to work well with computational chemistry packages, most notably the [**NWChem**](http://www.nwchem-sw.org/) computational chemistry platform developed by the Environmental Molecular Sciences Laboratory (EMSL) at Pacific Northwest National Laboratory.</span></span>
<span data-ttu-id="a4a7a-132">Konkrétně balíček `Microsoft.Quantum.Chemistry` poskytuje nástroje pro načítání instancí chemického plnění, které představují problémy s simulací ve [schématu Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), podporované také pro export pomocí nejnovějších verzí NWChem.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-132">In particular, the `Microsoft.Quantum.Chemistry` package provides tools for loading instances of quantum chemistry simulation problems represented in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), also supported for export by recent versions of NWChem.</span></span>

<span data-ttu-id="a4a7a-133">Pokud chcete začít pracovat s NWChem společně s vývojovou sadou pro práci s více operačními systémy, doporučujeme jednu z následujících metod:</span><span class="sxs-lookup"><span data-stu-id="a4a7a-133">To get up and running using NWChem together with the Quantum Development Kit, we suggest one of the following methods:</span></span>
- <span data-ttu-id="a4a7a-134">Začněte používat stávající soubory Broombridge dodávané s ukázkami v [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="a4a7a-134">Get started using existing Broombridge files provided with the samples at [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span></span>
- <span data-ttu-id="a4a7a-135">Pro Microsoft Quantum Development Kit, což je webový front-end pro NWChem, můžete pomocí [Tvůrce šipek EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem) vygenerovat nové Broombridge naformátované molekulární vstupní soubory.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-135">Use the [EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) which is a web-based frontend to NWChem, to generate new Broombridge-formated molecular input files.</span></span>  
- <span data-ttu-id="a4a7a-136">Použijte k spuštění NWChem [Image Docker](https://hub.docker.com/r/nwchemorg/nwchem-qc/) , kterou poskytuje PNNL, nebo</span><span class="sxs-lookup"><span data-stu-id="a4a7a-136">Use the [Docker image](https://hub.docker.com/r/nwchemorg/nwchem-qc/) provided by PNNL to run NWChem, or</span></span>
- <span data-ttu-id="a4a7a-137">[Zkompilujte NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) pro vaši platformu.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-137">[Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) for your platform.</span></span>

<span data-ttu-id="a4a7a-138">Další informace o tom, jak pracovat s NWChem pro chemické modely a analyzovat pomocí knihovny programu pro vytváření více koncových procesorů, najdete v článku [komplexním s NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) .</span><span class="sxs-lookup"><span data-stu-id="a4a7a-138">See [End-to-end with NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) for more information on how to work with NWChem to chemical models to analyze with the Quantum Developmen Kit chemistry library.</span></span>

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a><span data-ttu-id="a4a7a-139">Začínáme s používáním souborů Broombridge poskytovaných v ukázkách</span><span class="sxs-lookup"><span data-stu-id="a4a7a-139">Getting started using Broombridge files provided with the samples</span></span>

<span data-ttu-id="a4a7a-140">Ve složce [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) v úložišti pro všechny procesory pro vývoj z více procesorů najdete datové soubory molekul s Broombridge formátem.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-140">The [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) folder in the Quantum Development Kit Samples repository contains Broombridge-formated molecule data files.</span></span>  

<span data-ttu-id="a4a7a-141">V jednoduchém příkladu můžete použít ukázku knihovny chemie, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) načíst Hamiltonian z jednoho ze souborů Broombridge a provést odhady brány pro simulaci nezatížených nákladů algorigthms:</span><span class="sxs-lookup"><span data-stu-id="a4a7a-141">As a simple example, use the chemistry library sample, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) to load the Hamiltonian from one of Broombridge files and perform gate estimates of quantum simulation algorigthms:</span></span>

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

<span data-ttu-id="a4a7a-142">Další informace o tom, jak zadat molekuly reprezentované Broombridge schématem, najdete v tématu [načtení Hamiltonian ze souboru](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .</span><span class="sxs-lookup"><span data-stu-id="a4a7a-142">See [Loading a Hamiltonian from file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) for more information on how to input molecules represented by the Broombridge schema.</span></span>  

<span data-ttu-id="a4a7a-143">Další informace o odhadu prostředků najdete v tématu [získání počtu prostředků](xref:microsoft.quantum.chemistry.examples.resourcecounts) .</span><span class="sxs-lookup"><span data-stu-id="a4a7a-143">See [Obtaining resource counts](xref:microsoft.quantum.chemistry.examples.resourcecounts) for more information on resource estimation.</span></span>  

### <a name="getting-started-using-the-emsl-arrows-builder"></a><span data-ttu-id="a4a7a-144">Začínáme s používáním tvůrce šipek EMSL</span><span class="sxs-lookup"><span data-stu-id="a4a7a-144">Getting started using the EMSL Arrows Builder</span></span>

<span data-ttu-id="a4a7a-145">Šipky EMSL jsou nástroj, který pomocí NWChem a chemických výpočetních databází generuje data molekul.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-145">EMSL Arrows is a tool that uses NWChem and chemical computational databases to generate molecule data.</span></span>  <span data-ttu-id="a4a7a-146">[EMSL šipky Builder pro Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) umožňuje zadat svůj model pomocí několika tvůrců molekulárního modelu a vygenerovat datový Broombridge, který bude používat sada pro vývoj všech počítačů.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-146">[EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) allows you to enter your model using multiple molecular model builders and generate the Broombridge datafile to be used by the Quantum Development Kit.</span></span>  

<span data-ttu-id="a4a7a-147">Na stránce EMSL klikněte na kartu [' instuctions '] a použijte pokyny [' jednoduché příklady] pro generování Broombridge souborů.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-147">From the EMSL page, click on the ['Instuctions'] tab, and follow the ['Simple Examples'] instructions to generate Broombridge files.</span></span>  <span data-ttu-id="a4a7a-148">Pak zkuste spustit [' GetGateCount '] pro zobrazení odhadů prostředků u těchto molekul.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-148">Then try running the ['GetGateCount'] to see the quantum resource estimates for these molecules.</span></span>

### <a name="installing-nwchem-from-source"></a><span data-ttu-id="a4a7a-149">Instalace NWChem ze zdroje</span><span class="sxs-lookup"><span data-stu-id="a4a7a-149">Installing NWChem from Source</span></span>

<span data-ttu-id="a4a7a-150">Úplné pokyny k instalaci NWChem ze zdroje [jsou k dispozici prostřednictvím PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span><span class="sxs-lookup"><span data-stu-id="a4a7a-150">Full instructions on how to install NWChem from source [are provided by PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span></span>

> [!TIP]
> <span data-ttu-id="a4a7a-151">Pokud chcete používat NWChem ze systému Windows 10, je systém Windows pro Linux skvělý volbou.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-151">If you wish to use NWChem from Windows 10, the Windows Subsystem for Linux is a great option.</span></span>
> <span data-ttu-id="a4a7a-152">Po instalaci [Ubuntu 18,04 LTS pro Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)spusťte `ubuntu18.04` z oblíbeného terminálu a podle pokynů uvedených výše nainstalujte NWChem ze zdroje.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-152">Once you have installed [Ubuntu 18.04 LTS for Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), run `ubuntu18.04` from your favorite terminal and follow the instructions above to install NWChem from source.</span></span>

<span data-ttu-id="a4a7a-153">Po zkompilování NWChem ze zdroje můžete spustit skript `yaml_driver`, který poskytuje NWChem pro rychlé vytváření instancí Broombridge ze vstupních balíčku NWChem:</span><span class="sxs-lookup"><span data-stu-id="a4a7a-153">Once you have compiled NWChem from source, you can run the `yaml_driver` script provided with NWChem to quickly produce Broombridge instances from NWChem input decks:</span></span>

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

<span data-ttu-id="a4a7a-154">Tento příkaz vytvoří nový soubor `input.yaml` ve formátu Broombridge v rámci aktuálního adresáře.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-154">This command will create a new `input.yaml` file in the Broombridge format within your current directory.</span></span>

### <a name="using-nwchem-with-docker"></a><span data-ttu-id="a4a7a-155">Použití NWChem s Docker</span><span class="sxs-lookup"><span data-stu-id="a4a7a-155">Using NWChem with Docker</span></span>

<span data-ttu-id="a4a7a-156">Předem připravené image pro použití NWChem jsou k dispozici pro různé platformy přes [Docker Hub](https://hub.docker.com).</span><span class="sxs-lookup"><span data-stu-id="a4a7a-156">Pre-built images for using NWChem are available cross-platform via [Docker Hub](https://hub.docker.com).</span></span>
<span data-ttu-id="a4a7a-157">Pokud chcete začít, postupujte podle pokynů k instalaci Docker pro vaši platformu:</span><span class="sxs-lookup"><span data-stu-id="a4a7a-157">To get started, follow the Docker installation instructions for your platform:</span></span>

- [<span data-ttu-id="a4a7a-158">Nainstalovat Docker pro Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a4a7a-158">Install Docker for Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [<span data-ttu-id="a4a7a-159">Nainstalovat Docker pro macOS</span><span class="sxs-lookup"><span data-stu-id="a4a7a-159">Install Docker for macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)
- [<span data-ttu-id="a4a7a-160">Nainstalovat Docker for Windows 10</span><span class="sxs-lookup"><span data-stu-id="a4a7a-160">Install Docker for Windows 10</span></span>](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> <span data-ttu-id="a4a7a-161">Pokud používáte Docker for Windows, budete muset sdílet jednotku obsahující dočasný adresář (obvykle se jedná o `C:\` disk) pomocí démona Docker.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-161">If you are using Docker for Windows, you will need to share the drive containing your temporary directory (usually this is the `C:\` drive) with the Docker daemon.</span></span> <span data-ttu-id="a4a7a-162">Další podrobnosti najdete v [dokumentaci k Docker](https://docs.docker.com/docker-for-windows/#shared-drives) .</span><span class="sxs-lookup"><span data-stu-id="a4a7a-162">See the [Docker documentation](https://docs.docker.com/docker-for-windows/#shared-drives) for more details.</span></span>

<span data-ttu-id="a4a7a-163">Po instalaci Docker můžete buď použít modul prostředí PowerShell, který je součástí sady pro vývoj všech stavů, pro spuštění bitové kopie, nebo můžete bitovou kopii spustit ručně.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-163">Once you have Docker installed, you can either use the PowerShell module provided with the Quantum Development Kit samples to run the image, or you can run the image manually.</span></span>
<span data-ttu-id="a4a7a-164">Podrobné informace o použití PowerShellu najdete tady. Pokud chcete použít bitovou kopii Docker ručně, přečtěte si dokumentaci dodanou [s imagí](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span><span class="sxs-lookup"><span data-stu-id="a4a7a-164">We detail using PowerShell here; if you would like to use the Docker image manually, please see the [documentation provided with the image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span></span>

#### <a name="running-nwchem-through-powershell-core"></a><span data-ttu-id="a4a7a-165">Spuštění NWChem prostřednictvím PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="a4a7a-165">Running NWChem through PowerShell Core</span></span>

<span data-ttu-id="a4a7a-166">Pokud chcete použít image NWChem Docker s využitím vývojářské sady pro všechna množství, poskytujeme malý modul PowerShellu, který zpracovává přesun souborů v NWChem za vás.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-166">To use the NWChem Docker image with the Quantum Development Kit, we provide a small PowerShell module that handles moving files in and out of NWChem for you.</span></span>
<span data-ttu-id="a4a7a-167">Pokud ještě nemáte nainstalované prostředí PowerShell Core, můžete ho stáhnout z [úložiště PowerShellu na GitHubu](https://github.com/PowerShell/PowerShell#get-powershell).</span><span class="sxs-lookup"><span data-stu-id="a4a7a-167">If you don't already have PowerShell Core installed, you can download it cross-platform from the [PowerShell repository on GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="a4a7a-168">PowerShell Core se používá také pro některé ukázky k předvedení interoperability s pracovními postupy pro datové vědy a obchodní analýzy.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-168">PowerShell Core is also used for some samples to demonstrate interoperability with data science and business analytics workflows.</span></span>

<span data-ttu-id="a4a7a-169">Po instalaci prostředí PowerShell Core importujte `InvokeNWChem.psm1`, aby byly v aktuální relaci dostupné příkazy NWChem:</span><span class="sxs-lookup"><span data-stu-id="a4a7a-169">Once you have PowerShell Core installed, import `InvokeNWChem.psm1` to make NWChem commands available in your current session:</span></span>

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

<span data-ttu-id="a4a7a-170">Tím se v aktuální relaci prostředí PowerShell zpřístupní příkaz `Convert-NWChemToBroombridge`.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-170">This will make the `Convert-NWChemToBroombridge` command available in your current PowerShell session.</span></span>
<span data-ttu-id="a4a7a-171">Pokud si chcete stáhnout potřebné image z Docker a použít je ke spouštění vstupních balíčku NWChem a k zachycení výstupu do Broombridge, spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="a4a7a-171">To download any needed images from Docker and use them to run NWChem input decks and capture output to Broombridge, run the following:</span></span>

```powershell
Convert-NWChemToBroombridge ./input.nw
```

<span data-ttu-id="a4a7a-172">Tím se vytvoří soubor Broombridge spuštěním NWChem na `input.nw`.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-172">This will create a Broombridge file by running NWChem on `input.nw`.</span></span>
<span data-ttu-id="a4a7a-173">Ve výchozím nastavení bude mít výstup Broombridge stejný název a cestu jako vstupní balíček s příponou `.nw` nahrazenou `.yaml`.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-173">By default, the Broombridge output will have the same name and path as the input deck, with the `.nw` extension replaced by `.yaml`.</span></span>
<span data-ttu-id="a4a7a-174">To lze přepsat pomocí parametru `-DestinationPath` pro `Convert-NWChemToBroombridge`.</span><span class="sxs-lookup"><span data-stu-id="a4a7a-174">This can be overridden by using the `-DestinationPath` parameter to `Convert-NWChemToBroombridge`.</span></span>
<span data-ttu-id="a4a7a-175">Další informace lze získat pomocí integrované funkce pomoci prostředí PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a4a7a-175">More information can be obtained by using PowerShell's built-in help functionality:</span></span>

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
