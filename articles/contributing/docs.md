---
title: Přispívání do dokumentace | Microsoft Docs
description: Přispívání do dokumentace
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: 1e24dd859c0b75a161f4f3c7151e2eec227075a2
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183671"
---
# <a name="improving-documentation"></a>Vylepšení dokumentace #

Dokumentace k vývojové sadě pro každé z nich přebírá několik různých forem. Tyto informace jsou snadno dostupné vývojářům ve více než jednou.

V rámci zásad [dokumentů jako kódu](https://www.writethedocs.org/guide/docs-as-code/)se veškerá dokumentace k nástroji pro vývoj všech stavů naformátuje jako kód a je spravovaná pomocí Gitu stejným způsobem jako zdrojový kód, který se používá k sestavení vývojové sady pro práci s více operačními systémem.
Ve většině případů se dokumentace pro vytváření kódu skládá z různých forem [Markdownu](https://daringfireball.net/projects/markdown/), jazyka pro zápis formátovaného textu ve formátu prostého textu, který se snadno používá v příkazovém řádku, v prostředích IDES a ve správě zdrojového kódu.
Podobně připravujeme knihovnu [MathJax](https://www.mathjax.org/) , která umožňuje formátování matematické v dokumentaci pomocí jazyka latex, jak je popsáno níže.


Každá forma dokumentace se ale v podrobnostech liší:

- Tato **koncepční dokumentace** se skládá ze sady článků, které jsou publikovány na https://docs.microsoft.com/quantum a které popisují vše od základů pro práci s počítačem a technickými specifikacemi pro formáty výměny. Tyto články jsou napsány v [DocFX Markdownu (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), což je Markdownu varianta používaná pro vytváření bohatých sad dokumentace.
- **Reference k rozhraní API** je sada stránek pro každou funkci Q #, operace a uživatelsky definované typy, které jsou publikovány na https://docs.microsoft.com/qsharp/api/. Tyto stránky dokumentují vstupy a operace pro jednotlivé možné akce, spolu s příklady a odkazy na Další informace. Odkaz rozhraní API se automaticky extrahuje z malých dokumentů DFM ve zdrojovém kódu Q # jako součást každé vydané verze.
- **Soubor readme<!---->. MD** , který je součástí jednotlivých ukázek a Kata, popisuje, jak použít tuto ukázku nebo Kata, co se zabývá a jak se vztahuje na zbytek vývojové sady pro plnění. Tyto soubory jsou zapisovány pomocí [Markdownu (GFM)](https://github.github.com/gfm/), což je složitější alternativa k DFM, která je oblíbená pro připojení dokumentace přímo k úložištím kódu.

## <a name="contributing-to-the-conceptual-documentation"></a>Přispívání do koncepční dokumentace ##

Aby bylo možné přispívat do dokumentace k Koncepční dokumentaci nebo k souboru READme, pak začíná žádost o přijetí změn pro MicrosoftDocs/podklady [ **-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/** ](https://github.com/Microsoft/Quantum)prosazení nebo [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), jak je to vhodné.
Další informace o žádostech o přijetí změn najdete níže, ale v současné době je k dispozici několik věcí, které byste měli mít na paměti při vylepšování dokumentace:

- Čtenáři přicházejí v dokumentaci k vývojové sadě pro spoustu velkých objemů dat z nejrůznějších pozadí. Všichni od vysoce školních studentů, kteří se chtějí dozvědět něco nového a zajímavého až po držení vyučujícího, by měli být schopni získat z této dokumentace něco z přečtení. V rozsahu, ve kterém je to možné, nedělejte v rámci svých čtecích zařízení rozsáhlé znalosti, protože se dají jenom vysílat. Je nejužitečnější, pokud můžete zadat jasný a přístupný popis nebo můžete poskytnout odkazy na další zdroje, kde najdete další informace.
- Sady dokumentace nejsou nastavované jako knihy nebo dokumenty. v těchto čtenářích dorazíte na to, co se může zdát jako střední. Například vyhledávací stroje nemusí navrhovat index, nebo se jim může poslat odkaz, který se snaží s tím, že je bude pomáhat. Zkuste Pomocníkovi pomáhat tím, že vždy zadáte jasný kontext, spolu s odkazy tam, kde je to vhodné.
- Někteří čtenáři naleznou abstraktní příkazy a definice, které jsou nejužitečnější, zatímco ostatní čtenáři fungují nejlépe pomocí extrapolace z konkrétních příkladů. Poskytnutím obecného případu a specifických příkladů může pomocníkům získat maximum z programu.
- Zvlášť, pokud jste napsali i kód, který je dokumentován, může být zřejmé, že nebudete mít vůbec žádné zjevné pro čtenáře. Neexistuje žádný jedinečný způsob, jak programovat, takže bez ohledu na to, jakým způsobem chytřejší nebo se čtenář může stát, nemůžou odhadnout, jaké vzory návrhu se vám pro vyjádření vašich nápadů v kódu považují za užitečné. Nemusíte mít jasné informace o tom, jak může čtenář očekávat použití kódu, což může přispět k poskytnutí tohoto kontextu.
- Mnoho členů komunity pro programování po dobu nevyužívání předpisů je školními výzkumníky a jejich příspěvky se v komunitě uznávají hlavně prostřednictvím citace. Kromě pomoci čtenářů najít další materiály, aby se zajistilo správné uvedení školních výstupů, jako jsou například dokumenty, přednášky, blogové příspěvky a softwarové nástroje, mohou pomoci akademickým přispěvatelům zajistit jejich nejlepší práci pro zlepšení komunity.
- Komunita pro programování pro velké množství je širokou a skvělou různorodou komunitou. Použití žen v prostředníkech v příkladech třetích osob (např.: "Pokud uživatel..., bude...") může fungovat jako vyloučené místo zahrnutí. Společnost Cognizant jména lidí v citacích a odkazech a správným zahrnutím znaků, které nejsou ASCII, může obsluhovat různorodost komunity tím, že se bude brát ohled na její členy. Podobně se mnoho slov v anglickém jazyce často používá Hateful způsobem, takže jejich použití v technické dokumentaci může způsobit poškození jak na jednotlivé čtenáře, tak na komunitě.

## <a name="contributing-to-the-api-references"></a>Přispívání do referencí rozhraní API ##

Aby bylo možné přispívat do odkazů rozhraní API, je nejužitečnější otevřít žádost o přijetí změn přímo na dokumentovaném kódu.
Každá funkce, operace nebo uživatelsky definovaný typ podporuje dokumentační komentář (označený `///` místo `//`).
Když kompilujete jednotlivé verze vývojářské sady pro plnění, tyto komentáře se používají ke generování odkazu rozhraní API na https://docs.microsoft.com/qsharp/api/ , včetně podrobností o vstupech a výstupech z jednotlivých vydaných odkazů, podle předpokladů, které jsou k dispozici, a příklady, jak je používat.

> [!IMPORTANT]
> Ujistěte se prosím, že jste ručně neupravili vygenerovanou dokumentaci k rozhraní API, protože tyto soubory jsou v každé nové verzi přepsány.
> Váš příspěvek připravujeme komunitě a chceme se ujistit, že vaše změny budou dál pomáhat uživatelům vydávat verze po vydání.

Zvažte například operaci `PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`.
Komentář k dokumentaci by měl uživatelům porozumět tomu, jak interpretovat `angles`, jakou operaci předpokládá od počátečního stavu `register`, jaký má vliv na `register` a tak dále.
Každou z těchto různých částí informací lze kompilátoru Q # poskytnout pomocí speciálně pojmenovaného oddílu Markdownu v komentáři k dokumentaci.
Pro příklad `PrepareTrialState`můžeme napsat něco podobného jako následující:

```qsharp
/// # Summary
/// Given a register of qubits, prepares them in a trial state by rotating each
/// independently.
///
/// # Description
/// This operation prepares the input register by performing a
/// $Y$ rotation on each qubit by an angle given in `angles`.
///
/// # Input
/// ## angles
/// An array of parameters
/// ## register
/// A register of qubits initially in the $\ket{00\cdots0}$ state.
///
/// # Example
/// To prepare an equal superposition $\ket{++\cdots+}$ over all input qubits:
/// ```qsharp
/// PrepareTrialState(ConstantArray(Length(register), PI() / 2.0), register);
/// ```
///
/// # Remarks
/// This operation is generally useful in the inner loop of an optimization
/// algorithm.
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.Ry
operation PrepareTrialState(angles : Double[], register : Qubit[]) : Unit {
    // ...
}
```

Kromě obecné praxe psaní dokumentace k rozhraní API, které vám pomůžou při psaní komentářů k rozhraní API, je potřeba mít na paměti pár věcí:

- Formát každého komentáře k dokumentaci musí odpovídat, co kompilátor Q # očekává, aby se vaše dokumentace zobrazovala správně. Některé oddíly, například `/// # Remarks`, umožňují obsah volného tvaru, zatímco oddíly jako `/// # See Also` oddílu jsou více omezující.
- Čtenář si může přečíst dokumentaci k rozhraní API na hlavním referenčním webu rozhraní API, na shrnutí každého oboru názvů nebo dokonce i v rámci integrovaného vývojového prostředí pomocí informací o přechodu myší. Ujistěte se, že `/// # Summary` delší než o větu pomáhá čtenářům rychle seřadit informace o tom, jestli je potřeba je přečíst nebo najít jinde, a může vám pomoci při rychlém procházení souhrnů oborů názvů.
- Vaše dokumentace může být hodně delší než samotný kód, ale je to v pořádku! I malá část kódu může mít neočekávané efekty pro uživatele, kteří neznají kontext, ve kterém tento kód existuje. Poskytnutím konkrétních příkladů a jasným vysvětlením můžete uživatelům pomáhat s tím, že budou mít k dispozici nejlepší využití kódu, který je k dispozici.

<!-- ## LaTeX Formatting ##

**TODO** -->
