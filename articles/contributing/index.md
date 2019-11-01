---
title: Přispívání pro sadu Quantum Development Kit | Microsoft Docs
description: Přispívání pro sadu Quantum Development Kit
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing
ms.openlocfilehash: 4be86c5045ece62ae3af40090a2cd344d965e65f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/30/2019
ms.locfileid: "73057389"
---
# <a name="contributing-to-the-quantum-development-kit"></a>Přispívání pro sadu Quantum Development Kit #

Sada Quantum Development Kit je víc než jen kolekce nástrojů pro psaní kvantových programů.
Je součástí rozsáhlé komunity lidí, kteří objevují kvantové výpočty, provádějí výzkum v oblasti kvantových algoritmů, vyvíjejí nové aplikace pro kvantová zařízení nebo pracují jiným způsobem na maximálním využití kvantového programování.
V rámci této komunity se sada Quantum Development Kit zaměřuje na to, aby kvantovým vývojářům nabízela funkce, které potřebují, pro široké spektrum prostředí.
Vaše příspěvky pro sadu Quantum Development Kit pomůžou při realizaci tohoto cíle tím, že se budou zlepšovat nástroje používané jinými kvantovými vývojáři a způsob dokumentace těchto nástrojů, a také vytvářením nových funkcí, díky nimž bude celá komunita kvantového programování lepším místem pro objevování a tvorbu.
Velice vám děkujeme za vaše laskavé příspěvky a za příležitost ke spolupráci na maximálním vylepšování naší komunity.

V tomto průvodci uvádíme několik rad, jak dosáhnout co největšího užitku z příspěvku pro širší komunitu kvantového programování.

## <a name="building-community"></a>Vytváření komunity ##

Hlavní věcí při přispívání je neustále mít na zřeteli komunitu, které přispíváte.
Díky respektu a profesionálnímu chování k partnerům v komunitě kvantového programování i v širším měřítku můžete pomoct zajistit, aby vaše snaha přispívala k existenci té nejlepší a nejvstřícnější možné komunity.

Jako součást této snahy dodržují všechny projekty sady Quantum Development Kit [pravidla chování pro open source společnosti Microsoft](https://opensource.microsoft.com/codeofconduct/).
Další informace najdete v [nejčastějších dotazech k pravidlům chování](https://opensource.microsoft.com/codeofconduct/faq/). S případnými dalšími dotazy nebo připomínkami se obracejte na adresu [opencode@microsoft.com](mailto:opencode@microsoft.com).

## <a name="what-kinds-of-contributions-help-the-community"></a>Jaké druhy příspěvků komunitě pomůžou? ##

Komunitě kvantového programování je možné pomáhat prostřednictvím příspěvků mnoha různými způsoby.
V tomto průvodci se zaměříme na tři způsoby, které jsou pro sadu Quantum Development Kit obzvlášť relevantní.
Všechny tyto způsoby jsou zásadním předpokladem vytváření kvantové komunity, která lidem dává možnosti.
Rozhodně se však nejedná o vyčerpávající seznam – doporučujeme vám prozkoumat další způsoby pomoci komunitě při realizaci slibné budoucnosti kvantového programování!

- **Zasílání zpráv o chybách.** Prvním krokem při odstraňování chyb a dalších druhů problémů je jejich identifikace. Pokud v sadě Quantum Development Kit objevíte chybu a dáte nám o tom vědět, pomůžete nám odstranit ji, a tím vylepšit celou sadu nástrojů pro komunitu kvantového programování.
- **Vylepšování dokumentace.** Každou dokumentaci je možné vylepšit, přidat do ní další podrobnosti nebo ji upravit, aby byla přístupnější.
- **Přispívání kódem.** Jedním z nejpřímějších způsobů přispívání je samozřejmě přidávání nového kódu do sady Quantum Development Kit.

Všechny tyto různé druhy příspěvků jsou nesmírně cenné a velmi si jich vážíme.
V zbývající části průvodce vám poradíme s postupem u jednotlivých druhů příspěvků.

## <a name="where-do-contributions-go"></a>Co se s příspěvky stane? ##

Sada Quantum Development Kit obsahuje mnoho různých částí, které společně tvoří platformu pro psaní kvantových programů.
Každý z těchto různých kousků je umístěn v jiném úložišti, takže jednou z prvních věcí k řešení je najít pro každý příspěvek to nejlepší místo.

- [**microsoft/Quantum:** ](https://github.com/Microsoft/Quantum) Ukázky a nástroje, které vám pomůžou začít používat sadu Quantum Development Kit.
- [**microsoft/QuantumLibraries:** ](https://github.com/Microsoft/QuantumLibraries) Standardní knihovny a knihovny specifické pro konkrétní doménu pro sadu Quantum Development Kit.
- [**microsoft/QuantumKatas:** ](https://github.com/Microsoft/QuantumKatas) Programovací cvičení umožňující postupovat vlastním tempem při studiu kvantových výpočtů a programovacího jazyka Q#.
- [**microsoft/qsharp-compiler:** ](https://github.com/microsoft/qsharp-compiler) Kompilátor jazyka Q#, rozšíření sady Visual Studio a rozšíření editoru Visual Studio Code.
- [**microsoft/qsharp-runtime:** ](https://github.com/microsoft/qsharp-runtime) Architektura pro simulace, generování kódu a cílové počítače simulací pro sadu Quantum Development Kit.
- [**microsoft/iqsharp:** ](https://github.com/microsoft/iqsharp) Funkce jádra Jupyter a hostitele Pythonu pro jazyk Q# a také image Dockeru pro používání IQ# v cloudových prostředích.
- [**MicrosoftDocs/quantum-docs-pr:** ](https://github.com/MicrosoftDocs/quantum-docs-pr) Zdrojový kód pro dokumentaci publikovanou na webu https://docs.microsoft.com/quantum.

> [!NOTE]
> V současné době bohužel nemůžeme přijímat příspěvky pro kód a dokumentaci v úložišti [**microsoft/Quantum-NC**](https://github.com/microsoft/Quantum-NC), budeme však velmi vděční za zprávy o chybách.

Existuje ještě několik dalších, specializovanějších úložišť, která se zaměřují na různé události nebo na doplňkové funkce související se sadou Quantum Development Kit.

- [**msr-quarc/qsharp.sty:** ](https://github.com/msr-quarc/qsharp.sty) Podpora formátování LaTeX pro syntaxi jazyka Q#.
- [**msr-quarc/intern-workshop-2019:** ](https://github.com/msr-quarc/intern-workshop-2019) Poznámkový blok IQ# pro kurz k Deutschovu-Jozsovu algoritmu na workshopu pro stážisty v roce 2019.

## <a name="next-steps"></a>Další kroky ##

Děkujeme, že jste se stali součástí komunity sady Quantum Development Kit. Těšíme se na vaše příspěvky!
Pokud se o přispívání chcete dozvědět víc, pokračujte jedním z následujících průvodců.

> [!div class="nextstepaction"]
> [Naučte se zasílat zprávy o chybách](xref:microsoft.quantum.contributing.reporting)

> [!div class="nextstepaction"]
> [Naučte se přispívat do dokumentace](xref:microsoft.quantum.contributing.docs)

> [!div class="nextstepaction"]
> [Naučte se otvírat žádosti o přijetí změn](xref:microsoft.quantum.contributing.pulls)

