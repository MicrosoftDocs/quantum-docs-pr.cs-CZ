---
title: Přispívání kódu do Microsoft QDK
description: Naučte se, jak do Microsoft Quantum Development Kit (QDK) přispívat kód Sample a Library.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
no-loc:
- Q#
- $$v
ms.openlocfilehash: 956b0957a5261b8a77bf18d776fbcc2853bfbfe7
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866905"
---
# <a name="contributing-code"></a>Přispívání do kódu

Kromě vytváření sestav a vylepšení dokumentace může být přispívat kód do vývojové sady pro plnění kódu velmi přímým způsobem, jak pomáhat vašim partnerům v komunitě programování.
Díky přispívání kódu vám může pomoct opravit problémy, poskytnout nové příklady, usnadnit používání stávajících knihoven nebo dokonce přidat zcela nové funkce.

V této příručce podíváme se na to, co vyhledáme, když zkontrolujeme žádosti o přijetí změn, abychom vám pomohli přispět k vašemu příspěvku.

## <a name="what-we-look-for"></a>Co podíváme na

Ideální příspěvek v kódu staví na stávající práci v úložišti pro vývojová prostředí pro řešení problémů, rozbalí existující funkce nebo přidá nové funkce, které spadají do oboru úložiště.
Když přijmeme příspěvek kódu, bude se jednat o součást samotného vývojového prostředí, takže nové funkce budou zveřejněny, udržovány a vyvíjeny stejným způsobem jako zbytek vývojové sady pro plnění.
Proto je užitečné, pokud je funkce přidaná v příspěvku dobře testována a je dokumentována.

### <a name="unit-tests"></a>Testování částí

Q#Funkce, operace a uživatelsky definované typy, které vytvářejí knihovny, jako je například Canon, se automaticky testují jako součást vývoje v úložišti [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) .
Když se otevře nová žádost o přijetí změn, například naše konfigurace [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) ověří, že změny v žádosti o přijetí změn neruší žádné stávající funkce, na kterých je komunita programování.

S nejnovější Q# verzí je test jednotky definován pomocí `@Test("QuantumSimulator")` atributu. Argument může být buď "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", nebo jakýkoli plně kvalifikovaný název určující cíl spuštění. Ke stejnému vyžádání může být připojeno několik atributů definujících různé cíle provádění. Některé z našich testů stále používají zastaralý balíček [Microsoft. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) , který zpřístupňuje všechny Q# funkce a operace končící rozhraním `Test` [xUnit](https://xunit.github.io/) . Tento balíček již není potřeba pro definování testů jednotek. 

Následující funkce se používá k zajištění, že <xref:microsoft.quantum.canon.fst> funkce a <xref:microsoft.quantum.canon.snd> vrátí v reprezentativním příkladu správné výstupy.
Pokud výstup `Fst` nebo `Snd` není správný, `fail` příkaz slouží k selhání testu.

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

Složitější podmínky lze kontrolovat pomocí postupů v [části testování](xref:microsoft.quantum.libraries.diagnostics) Průvodce standardními knihovnami.
Například následující testy, které `H(q); X(q); H(q);` jsou volány, mají za <xref:microsoft.quantum.canon.applywith> úkol stejné jako `Z(q)` .

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
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

Místně můžete testy jednotek spustit pomocí Průzkumníka testů sady Visual Studio nebo `dotnet test` příkazu, abyste před otevřením žádosti o přijetí změn mohli svůj příspěvek zkontrolovat.

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->


## <a name="when-well-reject-a-pull-request"></a>Po odmítnutí žádosti o získání dat odmítneme

V některých případech odmítneme žádost o získání příspěvku.
Pokud k tomu dojde, neznamená to, že je to špatné, protože existuje několik důvodů, proč nemusí být možné přijmout konkrétní příspěvek.
Možná nejčastěji je přínosem komunity pro programování po nedostatečném zájmu, ale nejedná se o správné místo pro vývoj v sadě
V takových případech důrazně doporučujeme, abyste si vlastní úložiště---část síly pro vývojová prostředí pro práci s více podprocesy, což je snadné vytvoření a distribuce vlastních knihoven pomocí GitHubu a NuGet.org stejným způsobem jako knihovny Canon a chemie ještě dnes.

V jinou dobu můžeme bezdůvodně odmítnout dobrý příspěvek, protože ještě nejste připraveni na jeho údržbu a vývoj.
To všechno může být obtížné, takže si naplánujeme, na jaké funkce máme v plánu možnost pracovat.
Může to být jiný případ, kdy vydání funkce jako knihovny třetích stran může mít spoustu smyslů.
Alternativně můžeme požádat o pomoc při úpravě funkce, aby lépe vyhovovala vašemu plánu, abychom mohli co nejlépe udělat, abychom s ním mohli pracovat.

Také požádáme o změny žádosti o přijetí změn, pokud to vyžaduje další dokumentaci nebo testy jednotek, které nám pomohou ji využít, nebo pokud se liší ve stylu od zbytku Q# knihoven, které by uživatelům usnadnily hledání vaší funkce.
V těchto případech se pokusíme nabídnout několik rad v revizích kódu o tom, co je možné přidat nebo změnit, abychom mohli přispět k tomu, aby mohl být váš příspěvek snáze zahrnutý.

Nakonec nemůžeme přijmout příspěvky, které způsobují poškození komunity s nárokem na výpočetní výkon, jak je uvedeno v [kódu chování pro Microsoft Open Source](https://opensource.microsoft.com/codeofconduct/).
Chceme zajistit, aby příspěvky poskytovaly celou komunitu pro výpočetní výkon, jak jsou v aktuální milované rozmanitosti, a v budoucnu i v budoucnu.
Oceňujeme vám vaši technickou podporu při realizaci tohoto cíle.

## <a name="next-steps"></a>Další kroky

Děkujeme, že se vám pomůže zajistit vývojovou sadu pro všechna ta, což je skvělý prostředek pro celou komunitu programování.
Pokud se chcete dozvědět víc, pokračujte prosím následujícím vodítkem na Q# styl.

> [!div class="nextstepaction"]
> [Seznamte se s Q# pokyny ke stylům](xref:microsoft.quantum.contributing.style)

V závislosti na tom, jaký typ kódu přispíváte, může docházet k dalším akcím, které vám pomůžou zajistit, aby váš příspěvek byl co nejvíc pro komunitu co nejužitečnější.

> [!div class="nextstepaction"]
> [Další informace o přispívání ukázek](xref:microsoft.quantum.contributing.samples)
