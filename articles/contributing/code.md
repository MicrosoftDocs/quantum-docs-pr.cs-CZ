---
title: Přispívající kód | Microsoft Docs
description: Přispívání kódu
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: cca50e6c63d4bb982aa5f0a59fc19d08ecbec508
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185898"
---
# <a name="contributing-code"></a>Přispívání kódu #

Kromě vytváření sestav a vylepšení dokumentace může být přispívat kód do vývojové sady pro plnění kódu velmi přímým způsobem, jak pomáhat vašim partnerům v komunitě programování.
Díky přispívání kódu vám může pomoct opravit problémy, poskytnout nové příklady, usnadnit používání stávajících knihoven nebo dokonce přidat zcela nové funkce.

V této příručce podíváme se na to, co vyhledáme, když zkontrolujeme žádosti o přijetí změn, abychom vám pomohli přispět k vašemu příspěvku.

## <a name="what-we-look-for"></a>Co podíváme na ##

Ideální příspěvek v kódu staví na stávající práci v úložišti pro vývojová prostředí pro řešení problémů, rozbalí existující funkce nebo přidá nové funkce, které spadají do oboru úložiště.
Když přijmeme příspěvek kódu, bude se jednat o součást samotného vývojového prostředí, takže nové funkce budou zveřejněny, udržovány a vyvíjeny stejným způsobem jako zbytek vývojové sady pro plnění.
Proto je užitečné, pokud je funkce přidaná v příspěvku dobře testována a je dokumentována.

### <a name="unit-tests"></a>Testování částí ###

Funkce Q #, operace a uživatelsky definované typy, které vytvářejí knihovny, jako je například Canon, se automaticky testují jako součást vývoje v úložišti [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) .
Když se otevře nová žádost o přijetí změn, například naše konfigurace [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) ověří, že změny v žádosti o přijetí změn neruší žádné stávající funkce, na kterých je komunita programování.
Tyto testy jsou napsány pomocí balíčku Microsoft. probíhající [. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) , který zpřístupňuje funkce Q # a jako testy pro [xUnit](https://xunit.github.io/) Framework.

[`Standard/tests/Standard.Tests.csproj`](https://github.com/microsoft/QuantumLibraries/blob/master/Standard/tests/Standard.Tests.csproj) používá tuto integraci xUnit ke spuštění jakýchkoli funkcí nebo operací končících `Test`.
Například následující funkce se používá k zajištění, že funkce <xref:microsoft.quantum.canon.fst> a <xref:microsoft.quantum.canon.snd> vrátí v reprezentativním příkladu správné výstupy.
Pokud je výstup `Fst` nebo `Snd` nesprávný, je příkaz `fail` použit k selhání testu.

```qsharp
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

Složitější podmínky lze kontrolovat pomocí postupů v [části testování](xref:microsoft.quantum.libraries.diagnostics) Průvodce standardními knihovnami.
Například následující test kontroluje, že `H(q); X(q); H(q);` jako volaný <xref:microsoft.quantum.canon.applywith> funguje stejně jako `Z(q)`.

```qsharp
operation WithTest () : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

Při přidávání nových funkcí je vhodné také přidat nové testy, abyste se ujistili, že váš příspěvek vede k tomu, co má.
To pomáhá ostatním komunitám udržovat a vyvíjet vaše funkce a zejména pomáhá ostatním vývojářům zjistit, že se můžou spolehnout na vaši funkci.

> [!NOTE]
> To funguje i v tomto případě.
> Pokud existuje nějaká funkce, ve které chybí některé testy, Pomozte nám přidat pokrytí testu, což nám umožní skvělé příspěvky na komunitu.

V místním prostředí lze testy jednotek spustit pomocí Průzkumníka testů sady Visual Studio nebo příkazu `dotnet test`, abyste před otevřením žádosti o přijetí změn mohli svůj příspěvek zkontrolovat.

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="when-well-reject-a-pull-request"></a>Po odmítnutí žádosti o získání dat odmítneme ##

V některých případech odmítneme žádost o získání příspěvku.
Pokud k tomu dojde, neznamená to, že je to špatné, protože existuje několik důvodů, proč nemusí být možné přijmout konkrétní příspěvek.
Možná nejčastěji je přínosem komunity pro programování po nedostatečném zájmu, ale nejedná se o správné místo pro vývoj v sadě
V takových případech důrazně doporučujeme, abyste si vlastní úložiště---část síly pro vývojová prostředí pro práci s nástroji pro plnění. je to, že je snadné dělat a distribuovat vlastní knihovny pomocí GitHubu a NuGet.org stejným způsobem, jakým distribuujeme Canon a chemie. knihovny ještě dnes.

V jinou dobu můžeme bezdůvodně odmítnout dobrý příspěvek, protože ještě nejste připraveni na jeho údržbu a vývoj.
To všechno může být obtížné, takže si naplánujeme, na jaké funkce máme v plánu možnost pracovat.
Může to být jiný případ, kdy vydání funkce jako knihovny třetích stran může mít spoustu smyslů.
Alternativně můžeme požádat o pomoc při úpravě funkce, aby lépe vyhovovala vašemu plánu, abychom mohli co nejlépe udělat, abychom s ním mohli pracovat.

Také požádáme o změny žádosti o přijetí změn, pokud to vyžaduje další dokumentaci nebo testy jednotek, které nám pomohou ji využít, nebo pokud se liší ve stylu od zbylých knihoven Q #, které jim pro uživatele umožní najít vaši funkci.
V těchto případech se pokusíme nabídnout několik rad v revizích kódu o tom, co je možné přidat nebo změnit, abychom mohli přispět k tomu, aby mohl být váš příspěvek snáze zahrnutý.

Nakonec nemůžeme přijmout příspěvky, které způsobují poškození komunity s nárokem na výpočetní výkon, jak je uvedeno v [kódu chování pro Microsoft Open Source](https://opensource.microsoft.com/codeofconduct/).
Chceme zajistit, aby příspěvky poskytovaly celou komunitu pro výpočetní výkon, jak jsou v aktuální milované rozmanitosti, a v budoucnu i v budoucnu.
Oceňujeme vám vaši technickou podporu při realizaci tohoto cíle.

## <a name="next-steps"></a>Další kroky ##

Děkujeme, že se vám pomůže zajistit vývojovou sadu pro všechna ta, což je skvělý prostředek pro celou komunitu programování.
Další informace najdete v následující příručce ke stylu Q #.

> [!div class="nextstepaction"]
> [Seznamte se s pokyny pro styl Q #](xref:microsoft.quantum.contributing.style)
