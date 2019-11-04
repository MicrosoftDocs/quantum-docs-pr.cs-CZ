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
# <a name="end-to-end-with-nwchem"></a><span data-ttu-id="7b501-103">Konec až do konce s NWChem</span><span class="sxs-lookup"><span data-stu-id="7b501-103">End-to-end with NWChem</span></span> #

<span data-ttu-id="7b501-104">Na této stránce vás seznámíme s příkladem získání počtu bran pro simulaci přípravných počtů, počínaje vstupní balíčkí [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) .</span><span class="sxs-lookup"><span data-stu-id="7b501-104">In this page, we will walk through an example of getting gate counts for quantum chemistry simulation, starting from an [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) input deck.</span></span>
<span data-ttu-id="7b501-105">Než budete pokračovat v tomto příkladu, ujistěte se, že jste nainstalovali Docker, a to podle pokynů k [instalaci a ověření](xref:microsoft.quantum.chemistry.concepts.installation).</span><span class="sxs-lookup"><span data-stu-id="7b501-105">Before proceeding with this example, make sure that you've installed Docker, following the [installation and validation guide](xref:microsoft.quantum.chemistry.concepts.installation).</span></span>

<span data-ttu-id="7b501-106">Další informace:</span><span class="sxs-lookup"><span data-stu-id="7b501-106">For more information:</span></span>
- [<span data-ttu-id="7b501-107">Struktura vstupních balíčku NWChem</span><span class="sxs-lookup"><span data-stu-id="7b501-107">Structure of NWChem input decks</span></span>](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [<span data-ttu-id="7b501-108">Příkazy vstupního balíčku pro použití s vývojovou sadou pro všechna ta</span><span class="sxs-lookup"><span data-stu-id="7b501-108">Input deck commands for use with the Quantum Development Kit</span></span>](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [<span data-ttu-id="7b501-109">Instalace knihovny a závislostí chemického složení</span><span class="sxs-lookup"><span data-stu-id="7b501-109">Installing the chemistry library and dependencies</span></span>](xref:microsoft.quantum.chemistry.concepts.installation)
- [<span data-ttu-id="7b501-110">Počítání prostředků</span><span class="sxs-lookup"><span data-stu-id="7b501-110">Resource counting</span></span>](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> <span data-ttu-id="7b501-111">Tento příklad vyžaduje, aby se spustilo prostředí Windows PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="7b501-111">This example requires Windows PowerShell Core to run.</span></span>
> <span data-ttu-id="7b501-112">Stáhněte si PowerShell Core pro Windows, macOS nebo Linux na https://github.com/PowerShell/PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b501-112">Download PowerShell Core for Windows, macOS, or Linux at https://github.com/PowerShell/PowerShell.</span></span>

## <a name="importing-required-powershell-modules"></a><span data-ttu-id="7b501-113">Import požadovaných modulů prostředí PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b501-113">Importing Required PowerShell Modules</span></span> ##

<span data-ttu-id="7b501-114">Pokud jste to ještě neudělali, naklonujte [úložiště Microsoft/](https://github.com/Microsoft/Quantum)propracovaného prostředí, které obsahuje ukázky a pomůcky pro práci s vývojovou sadou pro všechna ta.</span><span class="sxs-lookup"><span data-stu-id="7b501-114">If you haven't already done so, clone the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum), which contains samples and utilities for working with the Quantum Development Kit:</span></span>

```powershell
git clone https://github.com/Microsoft/Quantum
```

<span data-ttu-id="7b501-115">Po naklonování `Microsoft/Quantum`proveďte `cd` do složky `utilities/` a naimportujte modul PowerShell pro práci s Docker a NWChem:</span><span class="sxs-lookup"><span data-stu-id="7b501-115">Once you've cloned `Microsoft/Quantum`, perform `cd` into the `utilities/` folder and import the PowerShell module for working with Docker and NWChem:</span></span>

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> <span data-ttu-id="7b501-116">Ve výchozím nastavení systém Windows zabraňuje spuštění jakýchkoli skriptů nebo modulů v rámci bezpečnostního opatření.</span><span class="sxs-lookup"><span data-stu-id="7b501-116">By default, Windows prevents the execution of any scripts or modules as a security measure.</span></span>
> <span data-ttu-id="7b501-117">Pokud chcete, aby moduly jako `Invoke-NWChem.psm1` běžely ve Windows, možná budete muset změnit zásady spouštění.</span><span class="sxs-lookup"><span data-stu-id="7b501-117">To allow modules such as `Invoke-NWChem.psm1` to run on Windows, you may need to change the execution policy.</span></span>
> <span data-ttu-id="7b501-118">Uděláte to tak, že spustíte příkaz `Set-ExecutionPolicy`:</span><span class="sxs-lookup"><span data-stu-id="7b501-118">To do so, run the `Set-ExecutionPolicy` command:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> <span data-ttu-id="7b501-119">Zásady spouštění se pak po ukončení PowerShellu vrátí.</span><span class="sxs-lookup"><span data-stu-id="7b501-119">The execution policy will then be reverted when you exit PowerShell.</span></span>
> <span data-ttu-id="7b501-120">Pokud chcete uložit zásady spouštění, použijte jinou hodnotu pro `-Scope`:</span><span class="sxs-lookup"><span data-stu-id="7b501-120">If you would like to save the execution policy, use a different value for `-Scope`:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

<span data-ttu-id="7b501-121">Nyní byste měli mít k dispozici příkaz `Convert-NWChemToBroombridge`:</span><span class="sxs-lookup"><span data-stu-id="7b501-121">You should now have the `Convert-NWChemToBroombridge` command available:</span></span>

```powershell
Get-Command -Module InvokeNWChem
```

<span data-ttu-id="7b501-122">Dál naimportujeme příkaz `Get-GateCount`, který je k dispozici v ukázce **GetGateCount** .</span><span class="sxs-lookup"><span data-stu-id="7b501-122">Next, we'll import the `Get-GateCount` command provided with the **GetGateCount** sample.</span></span>
<span data-ttu-id="7b501-123">Úplné podrobnosti najdete v [pokynech uvedených v ukázce](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount).</span><span class="sxs-lookup"><span data-stu-id="7b501-123">For full details, see the [instructions provided with the sample](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount).</span></span>
<span data-ttu-id="7b501-124">V dalším kroku spusťte následující příkaz, kde v závislosti na vašem operačním systému nahradíte `<runtime>` buď pomocí `win10-x64`, `osx-x64`nebo `linux-x64`:</span><span class="sxs-lookup"><span data-stu-id="7b501-124">Next, run the following, substituting `<runtime>` with either `win10-x64`, `osx-x64`, or `linux-x64`, depending on your operating system:</span></span>

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

<span data-ttu-id="7b501-125">Nyní byste měli mít k dispozici příkaz `Get-GateCount`:</span><span class="sxs-lookup"><span data-stu-id="7b501-125">You should now have the `Get-GateCount` command available:</span></span>

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a><span data-ttu-id="7b501-126">Vstupní balíčky</span><span class="sxs-lookup"><span data-stu-id="7b501-126">Input Decks</span></span> ##

<span data-ttu-id="7b501-127">Balíček NWChem Získá textový soubor s názvem _vstupní balíček_ , který určuje, že se má vyřešit problém chemického incidentu, spolu s dalšími parametry, jako je nastavení přidělení paměti.</span><span class="sxs-lookup"><span data-stu-id="7b501-127">The NWChem package takes a text file called an _input deck_ which specifies a quantum chemistry problem to be solved, along with other parameters such as memory allocation settings.</span></span>
<span data-ttu-id="7b501-128">V tomto příkladu použijeme jednu z předem připravených vstupních balíčku, které jsou součástí NWChem.</span><span class="sxs-lookup"><span data-stu-id="7b501-128">For this example, we'll use one of the pre-made input decks that comes with NWChem.</span></span>
<span data-ttu-id="7b501-129">Nejdřív naklonujte [úložiště nwchemgit/nwchem](https://github.com/nwchemgit/nwchem):</span><span class="sxs-lookup"><span data-stu-id="7b501-129">First, clone the [nwchemgit/nwchem repository](https://github.com/nwchemgit/nwchem):</span></span>

> [!NOTE]
> <span data-ttu-id="7b501-130">Vzhledem k tomu, že se jedná o velmi velké úložiště, můžeme pomocí argumentu `--depth 1` ušetřit velkou šířku pásma a místo na disku.</span><span class="sxs-lookup"><span data-stu-id="7b501-130">Since this is a very large repository, we can do a shallow clone to save some bandwidth and disk space, using the `--depth 1` argument.</span></span>
> <span data-ttu-id="7b501-131">To je ale nepovinné.</span><span class="sxs-lookup"><span data-stu-id="7b501-131">This is optional, however.</span></span>
> <span data-ttu-id="7b501-132">Klonování bude pracovat přesně bez `--depth 1`.</span><span class="sxs-lookup"><span data-stu-id="7b501-132">Cloning will work just fine without `--depth 1`.</span></span>

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

<span data-ttu-id="7b501-133">`nwchemgit/nwchem` úložiště obsahuje řadu vstupních sad, které jsou určené pro použití s vývojovou sadou pro všechna vozidla, uvedená v části [`QA/chem_library_tests` složka](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).</span><span class="sxs-lookup"><span data-stu-id="7b501-133">The `nwchemgit/nwchem` repository comes with a variety of input decks intended for use with the Quantum Development Kit, listed under the [`QA/chem_library_tests` folder](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).</span></span>
<span data-ttu-id="7b501-134">V tomto příkladu použijeme `H4` vstupní balíček:</span><span class="sxs-lookup"><span data-stu-id="7b501-134">For this example, we'll use the `H4` input deck:</span></span>

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

<span data-ttu-id="7b501-135">Uvedená molekula je systémem 4 atomy vodíků, které jsou uspořádány v určité geometrii, která závisí na jednom úhlu, parametr `alpha`, jak je uvedeno v názvu `h4_sto6g_alpha.nw` balíčku.</span><span class="sxs-lookup"><span data-stu-id="7b501-135">The molecule in question is a system of 4 hydrogen atoms that are arranged in a certain geometry that depends on one angle, the parameter `alpha` as indicated in the name `h4_sto6g_alpha.nw` of the deck.</span></span> <span data-ttu-id="7b501-136">H4 je známý [molekulový srovnávací test](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) pro výpočetní chemii od 1970s.</span><span class="sxs-lookup"><span data-stu-id="7b501-136">H4 is a known [molecular benchmark](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) for computational chemistry since the 1970s.</span></span> <span data-ttu-id="7b501-137">Parametr `sto6g` je indikativní, že balíček implementuje reprezentaci s ohledem na Slater typu Orbital, konkrétně reprezentace s ohledem na [základ ši-NG nastavené](https://en.wikipedia.org/wiki/STO-nG_basis_sets) na 6 gaussovskéch základních funkcí.</span><span class="sxs-lookup"><span data-stu-id="7b501-137">The parameter `sto6g` is indicative that the deck implements a representation with respect to a Slater-type orbital, specifically, a representation with respect to an [STO-nG basis set](https://en.wikipedia.org/wiki/STO-nG_basis_sets) with 6 Gaussian basis functions.</span></span> <span data-ttu-id="7b501-138">Tento vstupní balíček dále obsahuje několik pokynů pro NWChem tensor (TCE), které přímo NWChem k vytváření informací potřebných pro spolupráci s prostředím pro vývoj všech provozních údajů:</span><span class="sxs-lookup"><span data-stu-id="7b501-138">This input deck furthermore contains several instructions to the NWChem Tensor Contraction Engine (TCE) that direct NWChem to produce the information needed for interoperating with the Quantum Development Kit:</span></span>

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a><span data-ttu-id="7b501-139">Vytváření a využívání výstupu Broombridge z NWChem</span><span class="sxs-lookup"><span data-stu-id="7b501-139">Producing and Consuming Broombridge Output from NWChem</span></span> ##

<span data-ttu-id="7b501-140">Teď máme všechno, co potřebujeme k vytváření a využívání dokumentů Broombridge.</span><span class="sxs-lookup"><span data-stu-id="7b501-140">We now have everything we need to produce and consume Broombridge documents.</span></span>
<span data-ttu-id="7b501-141">Pokud chcete spustit NWChem a vytvořit dokument Broombridge pro vstupní balíček `h4_sto6g_0.000.nw`, spusťte `Convert-NWChemToBroombridge`:</span><span class="sxs-lookup"><span data-stu-id="7b501-141">To run NWChem and produce a Broombridge document for the `h4_sto6g_0.000.nw` input deck, run `Convert-NWChemToBroombridge`:</span></span>

> [!NOTE]
> <span data-ttu-id="7b501-142">Při prvním spuštění tohoto příkazu vám Docker stáhne `nwchemorg/nwchem-qc` image za vás.</span><span class="sxs-lookup"><span data-stu-id="7b501-142">The first time you run this command, Docker will download the `nwchemorg/nwchem-qc` image for you.</span></span>
> <span data-ttu-id="7b501-143">V závislosti na rychlosti připojení může to chvíli trvat, což může mít za to, že je možné získat příležitost k navýšení kávy.</span><span class="sxs-lookup"><span data-stu-id="7b501-143">This may take a little while, depending on your connection speed, possibly providing an opportunity to get a cup of coffee.</span></span>

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

<span data-ttu-id="7b501-144">Tím se vytvoří dokument Broombridge s názvem `h4_sto6g_0.000.yaml`, který můžeme použít s `Get-GateCount`:</span><span class="sxs-lookup"><span data-stu-id="7b501-144">This will produce a Broombridge document called `h4_sto6g_0.000.yaml` that we can use with `Get-GateCount`:</span></span>

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

<span data-ttu-id="7b501-145">Nyní byste měli vidět výstup konzoly, který obsahuje odhad prostředků, jako je například T-Count, počet rotací, počet CNOT a další. pro různé metody simulace počtu procesorů:</span><span class="sxs-lookup"><span data-stu-id="7b501-145">You should now see console output which contains resource estimation such as T-count, rotations count, CNOT count, etc. for various quantum simulation methods:</span></span>

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

<span data-ttu-id="7b501-146">Existuje spousta věcí, které můžete dělat tady:</span><span class="sxs-lookup"><span data-stu-id="7b501-146">There are many things to go do from here:</span></span> 
- <span data-ttu-id="7b501-147">Vyzkoušejte si jiné předdefinované vstupní balíčky, třeba změnou parametru `alpha` v `h4_sto6g_alpha.nw`,</span><span class="sxs-lookup"><span data-stu-id="7b501-147">Try out different predefined input decks, e.g., by varying the parameter `alpha` in `h4_sto6g_alpha.nw`,</span></span> 
- <span data-ttu-id="7b501-148">Zkuste upravit balíčky, a to tak, že upravíte NWChem balíčky přímo, například prozkoumávání `STO-nG` modelů pro různé volby n,</span><span class="sxs-lookup"><span data-stu-id="7b501-148">Try modifying the decks by editing the NWChem decks directly, e.g., exploring `STO-nG` models for various choices of n,</span></span> 
- <span data-ttu-id="7b501-149">Vyzkoušejte jiné předdefinované vstupní balíčky NWChem, které jsou k dispozici na adrese `nwchem/qa/chem_library_tests`,</span><span class="sxs-lookup"><span data-stu-id="7b501-149">Try other predefined NWChem input decks that are available at `nwchem/qa/chem_library_tests`,</span></span>
- <span data-ttu-id="7b501-150">Vyzkoušejte sadu předdefinovaných srovnávacích testů Broombridge YAML, které byly vygenerovány z NWChem a jsou k dispozici jako součást [úložiště Microsoft/](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="7b501-150">Try out a suite of predefined Broombridge YAML benchmarks that were generated from NWChem and are available as part of the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span></span> <span data-ttu-id="7b501-151">Tyto srovnávací testy zahrnují:</span><span class="sxs-lookup"><span data-stu-id="7b501-151">These benchmarks include:</span></span> 
    - <span data-ttu-id="7b501-152">malé molekuly, jako je molekulový vodík (H2), beryllium (), lithium Hydride (LiH),</span><span class="sxs-lookup"><span data-stu-id="7b501-152">small molecules such as molecular hydrogen (H2), Beryllium (Be), Lithium hydride (LiH),</span></span>
    - <span data-ttu-id="7b501-153">větší molekuly, jako je ozon (O3), beta-karoten, cytosine a spousta dalších.</span><span class="sxs-lookup"><span data-stu-id="7b501-153">larger molecules such as ozone (O3), beta-carotene, cytosine, and many more.</span></span> 
- <span data-ttu-id="7b501-154">Vyzkoušejte grafické šipky front-endu [EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , které vycházejí z rozhraní Microsoft Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="7b501-154">Try out the graphical front-end [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) that features an interface to the Microsoft Quantum Development Kit.</span></span> 


## <a name="producing-broombridge-output-from-emsl-arrows"></a><span data-ttu-id="7b501-155">Vytváření výstupu Broombridge ze šipek EMSL</span><span class="sxs-lookup"><span data-stu-id="7b501-155">Producing Broombridge Output from EMSL Arrows</span></span> ##

<span data-ttu-id="7b501-156">Pokud chcete začít používat EMSL šipky na front-endu, přejděte [tady](https://arrows.emsl.pnnl.gov/api/qsharp_chem)do prohlížeče.</span><span class="sxs-lookup"><span data-stu-id="7b501-156">To get started with web-based front end EMSL Arrows, navigate a browser [here](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span></span> 

> [!NOTE]
> <span data-ttu-id="7b501-157">Spouštění šipek EMSL ve webovém prohlížeči vyžaduje, aby byl povolený JavaScript.</span><span class="sxs-lookup"><span data-stu-id="7b501-157">Running EMSL Arrows in a web browser requires JavaScript to be enabled.</span></span> <span data-ttu-id="7b501-158">Informace o tom, jak povolit JavaScript v prohlížeči, najdete v těchto [pokynech](https://www.enable-javascript.com/) .</span><span class="sxs-lookup"><span data-stu-id="7b501-158">Please refer to these [instructions](https://www.enable-javascript.com/) on how to enable JavaScript in your browser.</span></span> 

<span data-ttu-id="7b501-159">Nejprve zadejte molekulu do pole dotazu, které uvádí ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span><span class="sxs-lookup"><span data-stu-id="7b501-159">First, enter a molecule in the query box that says ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span></span> 

<span data-ttu-id="7b501-160">Můžete zadat mnoho molekul podle jejich Colloquial názvu, jako je "Kofein" místo "1, 3, 7-trimethylxanthine".</span><span class="sxs-lookup"><span data-stu-id="7b501-160">You can enter many molecules by their colloquial name, such as "caffeine" instead of "1,3,7-Trimethylxanthine".</span></span> 

<span data-ttu-id="7b501-161">Potom klikněte na tlačítko, které uvádí ``theory{qsharp_chem}``.</span><span class="sxs-lookup"><span data-stu-id="7b501-161">Next, click the button that says ``theory{qsharp_chem}``.</span></span> <span data-ttu-id="7b501-162">Tím se doplní pole dotazu o instrukci, která umožní, aby se výstup vyexportoval ve formátu Broombridge YAML.</span><span class="sxs-lookup"><span data-stu-id="7b501-162">This will populate the query box further with an instruction that will tell the run to export output in the Broombridge YAML format.</span></span> 

<span data-ttu-id="7b501-163">Nyní se ``Run Arrows``hodiny.</span><span class="sxs-lookup"><span data-stu-id="7b501-163">Now, clock on ``Run Arrows``.</span></span> <span data-ttu-id="7b501-164">V závislosti na velikosti vstupu může to chvíli trvat.</span><span class="sxs-lookup"><span data-stu-id="7b501-164">Depending on the size of the input, this might take a while.</span></span> <span data-ttu-id="7b501-165">Nebo v případě, že konkrétní model již byl vypočítán dříve, lze provést extrémně rychle, protože bude pouze pro vyhledávání v databázi.</span><span class="sxs-lookup"><span data-stu-id="7b501-165">Or, in case the particular model has already been computed before, it can be done extremely fast as it will only amount to a lookup in a database.</span></span> <span data-ttu-id="7b501-166">V obou případech přejdete na novou stránku, která obsahuje spoustu informací o konkrétním běhu NWChem proti balíčku určenému vaším zadáním.</span><span class="sxs-lookup"><span data-stu-id="7b501-166">In either case, you will be taken to a new page that contains a plethora of information about the particular run of NWChem against the deck specified by your input.</span></span> 

<span data-ttu-id="7b501-167">Soubor Broombridge YAML můžete stáhnout a uložit z části, která začíná následující hlavičkou:</span><span class="sxs-lookup"><span data-stu-id="7b501-167">You can download and save the Broombridge YAML file from the section that starts with the following header:</span></span> 
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

<span data-ttu-id="7b501-168">Klikněte na ``download``, která uloží místní kopii s jedinečným názvem souboru, například ``qsharp_chem48443.yaml`` (konkrétní název se bude pro každé spuštění lišit).</span><span class="sxs-lookup"><span data-stu-id="7b501-168">Click on ``download``, which saves a local copy with a unique file name such as ``qsharp_chem48443.yaml`` (the particular name will be different for each run).</span></span> <span data-ttu-id="7b501-169">Tento soubor pak můžete dál zpracovat tak, jak je uvedeno výše, například, s</span><span class="sxs-lookup"><span data-stu-id="7b501-169">You can then further process this file as above, e.g., with</span></span> 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
<span data-ttu-id="7b501-170">pro získání počtu prostředků.</span><span class="sxs-lookup"><span data-stu-id="7b501-170">to get resource counts.</span></span> 

<span data-ttu-id="7b501-171">Můžete se setkat s 3D tvůrcem molekul, ke kterému se dá dostat z karty ``Arrows Entry - 3D Builder`` na úvodní stránce šipky pro EMSL.</span><span class="sxs-lookup"><span data-stu-id="7b501-171">You might enjoy the 3D molecule builder that can be accessed from the ``Arrows Entry - 3D Builder`` tab on the EMSL Arrows start page.</span></span> <span data-ttu-id="7b501-172">Kliknutím na [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D obrázek zobrazené molekuly umožníte jeho úpravu.</span><span class="sxs-lookup"><span data-stu-id="7b501-172">Clicking the [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D picture of the shown molecule will let you allow to edit it.</span></span> <span data-ttu-id="7b501-173">Můžete přesunout atomy kolem, přetáhnout atomy od sebe, aby se změny mezi molekulové vzdálenosti měnily, přidaly/odebraly atomy atd. Po přidání ``theory{qsharp_chem}`` do pole dotazu můžete pro každou z těchto možností vygenerovat instanci schématu YAML a další prozkoumat ji pomocí knihovny pro složení neBroombridgech hodnot.</span><span class="sxs-lookup"><span data-stu-id="7b501-173">You can move atoms around, drag atoms apart so that their inter-molecular distances change, add/remove atoms, etc. For each of these choices, once you added ``theory{qsharp_chem}`` in the query box, you can then generate an instance of the Broombridge YAML schema and further explore it using the Quantum Chemistry Library.</span></span> 