---
title: Přispívání kódu do Microsoft QDK
description: Naučte se, jak do Microsoft Quantum Development Kit (QDK) přispívat kód Sample a Library.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.code
no-loc:
- Q#
- $$v
ms.openlocfilehash: 54ef15db2b850e6a3bff38945c57129361517bfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856676"
---
# <a name="contributing-code"></a><span data-ttu-id="55317-103">Přispívání do kódu</span><span class="sxs-lookup"><span data-stu-id="55317-103">Contributing Code</span></span>

<span data-ttu-id="55317-104">Kromě vytváření sestav a vylepšení dokumentace může být přispívat kód do vývojové sady pro plnění kódu velmi přímým způsobem, jak pomáhat vašim partnerům v komunitě programování.</span><span class="sxs-lookup"><span data-stu-id="55317-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="55317-105">Díky přispívání kódu vám může pomoct opravit problémy, poskytnout nové příklady, usnadnit používání stávajících knihoven nebo dokonce přidat zcela nové funkce.</span><span class="sxs-lookup"><span data-stu-id="55317-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="55317-106">V této příručce podíváme se na to, co vyhledáme, když zkontrolujeme žádosti o přijetí změn, abychom vám pomohli přispět k vašemu příspěvku.</span><span class="sxs-lookup"><span data-stu-id="55317-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="55317-107">Co podíváme na</span><span class="sxs-lookup"><span data-stu-id="55317-107">What We Look For</span></span>

<span data-ttu-id="55317-108">Ideální příspěvek v kódu staví na stávající práci v úložišti pro vývojová prostředí pro řešení problémů, rozbalí existující funkce nebo přidá nové funkce, které spadají do oboru úložiště.</span><span class="sxs-lookup"><span data-stu-id="55317-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="55317-109">Když přijmeme příspěvek kódu, bude se jednat o součást samotného vývojového prostředí, takže nové funkce budou zveřejněny, udržovány a vyvíjeny stejným způsobem jako zbytek vývojové sady pro plnění.</span><span class="sxs-lookup"><span data-stu-id="55317-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="55317-110">Proto je užitečné, pokud je funkce přidaná v příspěvku dobře testována a je dokumentována.</span><span class="sxs-lookup"><span data-stu-id="55317-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="55317-111">Testování částí</span><span class="sxs-lookup"><span data-stu-id="55317-111">Unit Tests</span></span>

<span data-ttu-id="55317-112">Q#Funkce, operace a uživatelsky definované typy, které vytvářejí knihovny, jako je například Canon, se automaticky testují jako součást vývoje v úložišti [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) .</span><span class="sxs-lookup"><span data-stu-id="55317-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="55317-113">Když se otevře nová žádost o přijetí změn, například naše konfigurace [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) ověří, že změny v žádosti o přijetí změn neruší žádné stávající funkce, na kterých je komunita programování.</span><span class="sxs-lookup"><span data-stu-id="55317-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>

<span data-ttu-id="55317-114">S nejnovější Q# verzí jsou testy jednotek definovány pomocí `@Test("QuantumSimulator")` atributu.</span><span class="sxs-lookup"><span data-stu-id="55317-114">With the latest Q# version, unit tests are defined using the `@Test("QuantumSimulator")` attribute.</span></span> <span data-ttu-id="55317-115">Argument může být buď "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", nebo jakýkoli plně kvalifikovaný název určující cíl spuštění.</span><span class="sxs-lookup"><span data-stu-id="55317-115">The argument may be either "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", or any fully qualified name specifying the run target.</span></span> <span data-ttu-id="55317-116">Ke stejnému možnému použití může být připojeno několik atributů definujících různé cíle spuštění.</span><span class="sxs-lookup"><span data-stu-id="55317-116">Several attributes defining different run targets may be attached to the same callable.</span></span> <span data-ttu-id="55317-117">Některé z našich testů stále používají zastaralý balíček [Microsoft. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) , který zpřístupňuje všechny Q# funkce a operace končící rozhraním `Test` [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="55317-117">Some of our tests still use the deprecated [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package that exposes all Q# functions and operations ending in `Test` to the [xUnit](https://xunit.github.io/) framework.</span></span> <span data-ttu-id="55317-118">Tento balíček již není potřeba pro definování testů jednotek.</span><span class="sxs-lookup"><span data-stu-id="55317-118">This package is no longer needed for defining unit tests.</span></span> 

<span data-ttu-id="55317-119">Následující funkce se používá k zajištění, že <xref:Microsoft.Quantum.Canon.Fst> funkce a <xref:Microsoft.Quantum.Canon.Snd> vrátí v reprezentativním příkladu správné výstupy.</span><span class="sxs-lookup"><span data-stu-id="55317-119">The following function is used to ensure that the <xref:Microsoft.Quantum.Canon.Fst> and <xref:Microsoft.Quantum.Canon.Snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="55317-120">Pokud výstup `Fst` nebo `Snd` není správný, `fail` příkaz slouží k selhání testu.</span><span class="sxs-lookup"><span data-stu-id="55317-120">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

```qsharp
@Test("QuantumSimulator")
function PairTest () : Unit {
    let pair = (12, PauliZ);

    if (Fst(pair) != 12) {
        let actual = Fst(pair);
        fail $"Expected 12, actual {actual}.";
    }

    if (Snd(pair) != PauliZ) {
        let actual = Snd(pair);
        fail $"Expected PauliZ, actual {actual}.";
    }
}
```

<span data-ttu-id="55317-121">Složitější podmínky lze kontrolovat pomocí postupů v [části testování](xref:microsoft.quantum.libraries.diagnostics) Průvodce standardními knihovnami.</span><span class="sxs-lookup"><span data-stu-id="55317-121">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="55317-122">Například následující testy, které `H(q); X(q); H(q);` jsou volány, mají za <xref:Microsoft.Quantum.Canon.ApplyWith> úkol stejné jako `Z(q)` .</span><span class="sxs-lookup"><span data-stu-id="55317-122">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:Microsoft.Quantum.Canon.ApplyWith> does the same thing as `Z(q)`.</span></span>

```qsharp
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="55317-123">Při přidávání nových funkcí je vhodné také přidat nové testy, abyste se ujistili, že váš příspěvek vede k tomu, co má.</span><span class="sxs-lookup"><span data-stu-id="55317-123">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="55317-124">To pomáhá ostatním komunitám udržovat a vyvíjet vaše funkce a zejména pomáhá ostatním vývojářům zjistit, že se můžou spolehnout na vaši funkci.</span><span class="sxs-lookup"><span data-stu-id="55317-124">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="55317-125">To funguje i v tomto případě.</span><span class="sxs-lookup"><span data-stu-id="55317-125">This works the other way around, too!</span></span>
> <span data-ttu-id="55317-126">Pokud existuje nějaká funkce, ve které chybí některé testy, Pomozte nám přidat pokrytí testu, což nám umožní skvělé příspěvky na komunitu.</span><span class="sxs-lookup"><span data-stu-id="55317-126">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="55317-127">Místně můžete testy jednotek spustit pomocí Průzkumníka testů sady Visual Studio nebo `dotnet test` příkazu, abyste před otevřením žádosti o přijetí změn mohli svůj příspěvek zkontrolovat.</span><span class="sxs-lookup"><span data-stu-id="55317-127">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="pull-requests"></a><span data-ttu-id="55317-128">Žádosti o přijetí změn</span><span class="sxs-lookup"><span data-stu-id="55317-128">Pull Requests</span></span>

<span data-ttu-id="55317-129">Až budete připraveni přispívat do práce, odešlete žádost o přijetí změn prostřednictvím GitHubu do odpovídajícího úložiště.</span><span class="sxs-lookup"><span data-stu-id="55317-129">When you are ready to contribute your work, please send a Pull Request via GitHub to the corresponding repository.</span></span>
<span data-ttu-id="55317-130">Tým bude kontrolovat a poskytovat zpětnou vazbu.</span><span class="sxs-lookup"><span data-stu-id="55317-130">The team will review and provide feedback.</span></span> <span data-ttu-id="55317-131">Všechny komentáře musí být zodpovězeny a vyřešeny a všechny kontroly musí být před sloučením kódu do větve úspěšné `main` .</span><span class="sxs-lookup"><span data-stu-id="55317-131">All comments need to be answered and resolved and all checks need to pass before the code is merged to the `main` branch.</span></span>

## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="55317-132">Po odmítnutí žádosti o získání dat odmítneme</span><span class="sxs-lookup"><span data-stu-id="55317-132">When We'll Reject a Pull Request</span></span>

<span data-ttu-id="55317-133">V některých případech odmítneme žádost o získání příspěvku.</span><span class="sxs-lookup"><span data-stu-id="55317-133">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="55317-134">Pokud k tomu dojde, neznamená to, že je to špatné, protože existuje několik důvodů, proč nemusí být možné přijmout konkrétní příspěvek.</span><span class="sxs-lookup"><span data-stu-id="55317-134">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="55317-135">Možná nejčastěji je přínosem komunity pro programování po nedostatečném zájmu, ale nejedná se o správné místo pro vývoj v sadě</span><span class="sxs-lookup"><span data-stu-id="55317-135">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="55317-136">V takových případech důrazně doporučujeme, abyste si vlastní úložiště---část síly pro vývojová prostředí pro práci s více podprocesy, což je snadné vytvoření a distribuce vlastních knihoven pomocí GitHubu a NuGet.org stejným způsobem jako knihovny Canon a chemie ještě dnes.</span><span class="sxs-lookup"><span data-stu-id="55317-136">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="55317-137">V jinou dobu můžeme bezdůvodně odmítnout dobrý příspěvek, protože ještě nejste připraveni na jeho údržbu a vývoj.</span><span class="sxs-lookup"><span data-stu-id="55317-137">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="55317-138">To všechno může být obtížné, takže si naplánujeme, na jaké funkce máme v plánu možnost pracovat.</span><span class="sxs-lookup"><span data-stu-id="55317-138">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="55317-139">Může to být jiný případ, kdy vydání funkce jako knihovny třetích stran může mít spoustu smyslů.</span><span class="sxs-lookup"><span data-stu-id="55317-139">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="55317-140">Alternativně můžeme požádat o pomoc při úpravě funkce, aby lépe vyhovovala vašemu plánu, abychom mohli co nejlépe udělat, abychom s ním mohli pracovat.</span><span class="sxs-lookup"><span data-stu-id="55317-140">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="55317-141">Také požádáme o změny žádosti o přijetí změn, pokud to vyžaduje další dokumentaci nebo testy jednotek, které nám pomohou ji využít, nebo pokud se liší ve stylu od zbytku Q# knihoven, které by uživatelům usnadnily hledání vaší funkce.</span><span class="sxs-lookup"><span data-stu-id="55317-141">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="55317-142">V těchto případech se pokusíme nabídnout několik rad v revizích kódu o tom, co je možné přidat nebo změnit, abychom mohli přispět k tomu, aby mohl být váš příspěvek snáze zahrnutý.</span><span class="sxs-lookup"><span data-stu-id="55317-142">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="55317-143">Nakonec nemůžeme přijmout příspěvky, které způsobují poškození komunity s nárokem na výpočetní výkon, jak je uvedeno v [kódu chování pro Microsoft Open Source](https://opensource.microsoft.com/codeofconduct/).</span><span class="sxs-lookup"><span data-stu-id="55317-143">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="55317-144">Chceme zajistit, aby příspěvky poskytovaly celou komunitu pro výpočetní výkon, jak jsou v aktuální milované rozmanitosti, a v budoucnu i v budoucnu.</span><span class="sxs-lookup"><span data-stu-id="55317-144">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="55317-145">Oceňujeme vám vaši technickou podporu při realizaci tohoto cíle.</span><span class="sxs-lookup"><span data-stu-id="55317-145">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="55317-146">Další kroky</span><span class="sxs-lookup"><span data-stu-id="55317-146">Next steps</span></span>

<span data-ttu-id="55317-147">Děkujeme, že se vám pomůže zajistit vývojovou sadu pro všechna ta, což je skvělý prostředek pro celou komunitu programování.</span><span class="sxs-lookup"><span data-stu-id="55317-147">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="55317-148">Pokud se chcete dozvědět víc, pokračujte prosím následujícím vodítkem na Q# styl.</span><span class="sxs-lookup"><span data-stu-id="55317-148">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="55317-149">Seznamte se s Q# pokyny ke stylům</span><span class="sxs-lookup"><span data-stu-id="55317-149">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)

<span data-ttu-id="55317-150">V závislosti na tom, jaký typ kódu přispíváte, může docházet k dalším akcím, které vám pomůžou zajistit, aby váš příspěvek byl co nejvíc pro komunitu co nejužitečnější.</span><span class="sxs-lookup"><span data-stu-id="55317-150">Depending on what kind of code you're contributing, there may be additional things to keep in mind that can help you make your contribution do as much good for the community as possible.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="55317-151">Další informace o přispívání ukázek</span><span class="sxs-lookup"><span data-stu-id="55317-151">Learn about contributing samples</span></span>](xref:microsoft.quantum.contributing.samples)
