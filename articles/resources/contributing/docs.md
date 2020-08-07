---
title: Přispívání do dokumentace k Microsoft QDK
description: Naučte se, jak přispívat k obsahu koncepčního nebo rozhraní API, do sady dokumentace pro každý produkt.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1110f32a6486de1a346b115fa928a098749b6690
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866872"
---
# <a name="improving-documentation"></a>Vylepšování dokumentace

Dokumentace k vývojové sadě pro každé z nich přebírá několik různých forem. Tyto informace jsou snadno dostupné vývojářům ve více než jednou.

V rámci zásad [dokumentů jako kódu](https://www.writethedocs.org/guide/docs-as-code/)se veškerá dokumentace k nástroji pro vývoj všech stavů naformátuje jako kód a je spravovaná pomocí Gitu stejným způsobem jako zdrojový kód, který se používá k sestavení vývojové sady pro práci s více operačními systémem.
Ve většině případů se dokumentace pro vytváření kódu skládá z různých forem [Markdownu](https://daringfireball.net/projects/markdown/), jazyka pro zápis formátovaného textu ve formátu prostého textu, který se snadno používá v příkazovém řádku, v prostředích IDES a ve správě zdrojového kódu.
Podobně připravujeme knihovnu [MathJax](https://www.mathjax.org/) , která umožňuje formátování matematické v dokumentaci pomocí jazyka latex, jak je popsáno níže.


Každá forma dokumentace se ale v podrobnostech liší:

- V **Koncepční dokumentaci** se skládá ze sady článků, které jsou publikovány v nástroji https://docs.microsoft.com/quantum , a které popisují vše od základů pro práci s výpočetními prostředky až po technické specifikace formátů pro výměnu. Tyto články jsou napsány v [DocFX Markdownu (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), což je Markdownu varianta používaná pro vytváření bohatých sad dokumentace.
- **Reference k rozhraní API** je sada stránek pro každou Q# funkci, operaci a uživatelsky definovaný typ, který je publikován do https://docs.microsoft.com/qsharp/api/ . Tyto stránky dokumentují vstupy a operace pro jednotlivé možné akce, spolu s příklady a odkazy na Další informace. Odkaz rozhraní API je automaticky extrahován z malých dokumentů DFM ve Q# zdrojovém kódu jako součást každé vydané verze.
- Soubory **Readme <!----> . MD** , které jsou součástí jednotlivých ukázek a Kata, popisují, jak se používá tato ukázka nebo Kata, co se zabývá a jak se vztahuje na zbytek vývojové sady pro plnění. Tyto soubory jsou zapisovány pomocí [Markdownu (GFM)](https://github.github.com/gfm/), což je složitější alternativa k DFM, která je oblíbená pro připojení dokumentace přímo k úložištím kódu.

## <a name="contributing-to-the-conceptual-documentation"></a>Přispívání do koncepční dokumentace

Aby bylo možné přispívat do dokumentace k Koncepční dokumentaci nebo k souboru READme, pak začíná žádost o přijetí změn pro MicrosoftDocs/podklady [**-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/**](https://github.com/Microsoft/Quantum)prosazení nebo [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), jak je to vhodné.
Další informace o žádostech o přijetí změn najdete níže, ale v současné době je k dispozici několik věcí, které byste měli mít na paměti při vylepšování dokumentace:

- Čtenáři přicházejí v dokumentaci k vývojové sadě pro spoustu velkých objemů dat z nejrůznějších pozadí. Všichni od vysoce školních studentů, kteří se chtějí dozvědět něco nového a zajímavého až po držení vyučujícího, by měli být schopni získat z této dokumentace něco z přečtení. V rozsahu, ve kterém je to možné, nedělejte v rámci svých čtecích zařízení rozsáhlé znalosti, protože se dají jenom vysílat. Je nejužitečnější, pokud můžete zadat jasný a přístupný popis nebo můžete poskytnout odkazy na další zdroje, kde najdete další informace.
- Sady dokumentace nejsou nastavované jako knihy nebo dokumenty. v těchto čtenářích dorazíte na to, co se může zdát jako střední. Například vyhledávací stroje nemusí navrhovat index, nebo se jim může poslat odkaz, který se snaží s tím, že je bude pomáhat. Zkuste Pomocníkovi pomáhat tím, že vždy zadáte jasný kontext, spolu s odkazy tam, kde je to vhodné.
- Někteří čtenáři naleznou abstraktní příkazy a definice, které jsou nejužitečnější, zatímco ostatní čtenáři fungují nejlépe pomocí extrapolace z konkrétních příkladů. Poskytnutím obecného případu a specifických příkladů může pomocníkům získat maximum z programu.
- Zvlášť, pokud jste napsali i kód, který je dokumentován, může být zřejmé, že nebudete mít vůbec žádné zjevné pro čtenáře. Neexistuje žádný jedinečný způsob, jak programovat, takže bez ohledu na to, jakým způsobem chytřejší nebo se čtenář může stát, nemůžou odhadnout, jaké vzory návrhu se vám pro vyjádření vašich nápadů v kódu považují za užitečné. Nemusíte mít jasné informace o tom, jak může čtenář očekávat použití kódu, což může přispět k poskytnutí tohoto kontextu.
- Mnoho členů komunity pro programování po dobu nevyužívání předpisů je školními výzkumníky a jejich příspěvky se v komunitě uznávají hlavně prostřednictvím citace. Kromě pomoci čtenářů najít další materiály, aby se zajistilo správné uvedení školních výstupů, jako jsou například dokumenty, přednášky, blogové příspěvky a softwarové nástroje, mohou pomoci akademickým přispěvatelům zajistit jejich nejlepší práci pro zlepšení komunity.
- Komunita pro programování pro velké množství je širokou a skvělou různorodou komunitou. Použití žen v prostředníkech v příkladech třetích osob (např.: "Pokud uživatel..., bude...") může fungovat jako vyloučené místo zahrnutí. Společnost Cognizant jména lidí v citacích a odkazech a správným zahrnutím znaků, které nejsou ASCII, může obsluhovat různorodost komunity tím, že se bude brát ohled na její členy. Podobně se mnoho slov v anglickém jazyce často používá Hateful způsobem, takže jejich použití v technické dokumentaci může způsobit poškození jak na jednotlivé čtenáře, tak na komunitě.

### <a name="referencing-sample-code-from-conceptual-articles"></a>Odkazování na vzorový kód z koncepčních článků

Pokud chcete zahrnout kód z [úložiště ukázek](https://github.com/Microsoft/Quantum), můžete tak učinit pomocí speciálního příkazu Markdownu DocFX:

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

Tento příkaz naimportuje řádky 4 do 8 [ `Game.qs` souboru z `chsh-game` ukázky](https://github.com/microsoft/Quantum/blob/master/samples/algorithms/chsh-game/Game.qs)a označí je jako Q# kód pro účely zvýrazňování syntaxe.
Pomocí tohoto příkazu se můžete vyhnout duplikování kódu mezi koncepčními články a úložištěm ukázek, aby byl vzorový kód v dokumentaci vždy aktuální.

## <a name="contributing-to-the-api-references"></a>Přispívání do referencí rozhraní API

Aby bylo možné přispívat do odkazů rozhraní API, je nejužitečnější otevřít žádost o přijetí změn přímo na dokumentovaném kódu.
Každá funkce, operace nebo uživatelsky definovaný typ podporuje dokumentační komentář (označený `///` místo `//` ).
Když kompilujeme jednotlivé verze vývojářské sady pro plnění stavů, použijí se tyto komentáře k vygenerování odkazu rozhraní API na https://docs.microsoft.com/qsharp/api/ , včetně podrobností o vstupech a výstupech z každého navýšení, předpokladů, které každá z nich vyvolá, a příklady, jak je používat.

> [!IMPORTANT]
> Ujistěte se prosím, že jste ručně neupravili vygenerovanou dokumentaci k rozhraní API, protože tyto soubory jsou v každé nové verzi přepsány.
> Váš příspěvek připravujeme komunitě a chceme se ujistit, že vaše změny budou dál pomáhat uživatelům vydávat verze po vydání.

Zvažte například funkci `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` .
Komentář k dokumentaci by měl dát uživateli vědět, jak interpretovat `bits` a `oracle` co je funkce pro.
Každou z těchto různých informací lze Q# kompilátoru poskytnout pomocí speciálně pojmenovaného oddílu Markdownu v komentáři k dokumentaci.
Pro příklad `ControlledOnBitString` můžete napsat něco podobného jako následující:

```qsharp
 /// # Summary
 /// Returns a unitary operation that applies an oracle on the target register if the 
 /// control register state corresponds to a specified bit mask.
 ///
 /// # Description
 /// The output of this function is an operation that can be represented by a
 /// unitary transformation $U$ such that
 /// \begin{align}
 ///     U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes
 ///     \begin{cases}
 ///         V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\
 ///         \ket{\psi} & \textrm{otherwise}
 ///     \end{cases},
 /// \end{align}
 /// where $V$ is a unitary transformation that represents the action of the
 /// `oracle` operation.
 ///
 /// # Input
 /// ## bits
 /// The bit string to control the given unitary operation on.
 /// ## oracle
 /// The unitary operation to be applied on the target register.
 ///
 /// # Output
 /// A unitary operation that applies `oracle` on the target register if the control 
 /// register state corresponds to the bit mask `bits`.
 ///
 /// # Remarks
 /// The length of `bits` and `controlRegister` must be equal.
 ///
 /// Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function
 /// is an operation that performs the following steps:
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits`;
 /// * apply `Controlled oracle` to the control and target registers;
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits` again to return the control register to the original state.
 ///
 /// The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.
 ///
 /// # Example
 /// The following code snippets are equivalent:
 /// ```qsharp
 /// (ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
 /// ```
 /// and
 /// ```qsharp
 /// within {
 ///     ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
 /// } apply {
 ///     Controlled oracle(controlRegister, targetRegister);
 /// }
 /// ```
 ///
 /// The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:
 /// ```qsharp
 /// using (register = Qubit[2]) {
 ///     ApplyToEach(H, register);
 ///     (ControlledOnBitString([false], Z))(register[0..0], register[1]);
 /// }
 /// ```
 function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
 {
     return ControlledOnBitStringImpl(bits, oracle, _, _);
 }
```

Vykreslenou verzi kódu uvedenou výše můžete zobrazit v [dokumentaci k rozhraní API pro danou `ControlledOnBitString` funkci](xref:microsoft.quantum.canon.controlledonbitstring).

Kromě obecné praxe psaní dokumentace k rozhraní API, které vám pomůžou při psaní komentářů k rozhraní API, je potřeba mít na paměti pár věcí:

- Formát každého komentáře k dokumentaci musí odpovídat, co Q# kompilátor očekává, aby se vaše dokumentace zobrazovala správně. Některé oddíly, jako `/// # Remarks` je například povolení pro volný obsah, zatímco oddíly, jako `/// # See Also` je oddíl, jsou přísnější.
- Čtenář si může přečíst dokumentaci k rozhraní API na hlavním referenčním webu rozhraní API, na shrnutí každého oboru názvů nebo dokonce i v rámci integrovaného vývojového prostředí pomocí informací o přechodu myší. Zajistěte, aby to `/// # Summary` ještě déle nepokračovalo v tom, že vaše čtečka rychle vyřadí, jestli je potřeba číst, nebo najít jiné místo a může vám pomoci při rychlém procházení souhrnů oborů názvů.
- Vaše dokumentace může být hodně delší než samotný kód, ale je to v pořádku! I malá část kódu může mít neočekávané efekty pro uživatele, kteří neznají kontext, ve kterém tento kód existuje. Poskytnutím konkrétních příkladů a jasným vysvětlením můžete uživatelům pomáhat s tím, že budou mít k dispozici nejlepší využití kódu, který je k dispozici.

<!-- ## LaTeX Formatting ##

**TODO** -->
