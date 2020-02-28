---
title: Přispívání do dokumentace k Microsoft QDK
description: Naučte se, jak přispívat k obsahu koncepčního nebo rozhraní API, do sady dokumentace pro každý produkt.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: d244a7841b4093031d6225230a6cbefb22cc6a39
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904889"
---
# <a name="improving-documentation"></a><span data-ttu-id="4d941-103">Vylepšení dokumentace</span><span class="sxs-lookup"><span data-stu-id="4d941-103">Improving Documentation</span></span> #

<span data-ttu-id="4d941-104">Dokumentace k vývojové sadě pro každé z nich přebírá několik různých forem. Tyto informace jsou snadno dostupné vývojářům ve více než jednou.</span><span class="sxs-lookup"><span data-stu-id="4d941-104">The documentation for the Quantum Development Kit takes on several different forms, such that information is readily available to quantum developers.</span></span>

<span data-ttu-id="4d941-105">V rámci zásad [dokumentů jako kódu](https://www.writethedocs.org/guide/docs-as-code/)se veškerá dokumentace k nástroji pro vývoj všech stavů naformátuje jako kód a je spravovaná pomocí Gitu stejným způsobem jako zdrojový kód, který se používá k sestavení vývojové sady pro práci s více operačními systémem.</span><span class="sxs-lookup"><span data-stu-id="4d941-105">Following the principles of [Docs as Code](https://www.writethedocs.org/guide/docs-as-code/), all Quantum Development Kit documentation is formatted as code and is managed using Git in the same way as the source code that is used to build the Quantum Development Kit.</span></span>
<span data-ttu-id="4d941-106">Ve většině případů se dokumentace pro vytváření kódu skládá z různých forem [Markdownu](https://daringfireball.net/projects/markdown/), jazyka pro zápis formátovaného textu ve formátu prostého textu, který se snadno používá v příkazovém řádku, v prostředích IDES a ve správě zdrojového kódu.</span><span class="sxs-lookup"><span data-stu-id="4d941-106">For the most part, the code backing documentation consists of various forms of [Markdown](https://daringfireball.net/projects/markdown/), a language for writing out richly formatted text in a plain text format that's easy to use at the command line, in IDEs, and with source control.</span></span>
<span data-ttu-id="4d941-107">Podobně připravujeme knihovnu [MathJax](https://www.mathjax.org/) , která umožňuje formátování matematické v dokumentaci pomocí jazyka latex, jak je popsáno níže.</span><span class="sxs-lookup"><span data-stu-id="4d941-107">We similarly adopt the [MathJax](https://www.mathjax.org/) library to allow for formatting mathematics in documentation using the LaTeX language, as detailed further below.</span></span>


<span data-ttu-id="4d941-108">Každá forma dokumentace se ale v podrobnostech liší:</span><span class="sxs-lookup"><span data-stu-id="4d941-108">That said, each form of documentation does vary somewhat in the details:</span></span>

- <span data-ttu-id="4d941-109">Tato **koncepční dokumentace** se skládá ze sady článků, které jsou publikovány na https://docs.microsoft.com/quantuma které popisují vše od základů pro práci s počítačem a technickými specifikacemi pro formáty výměny.</span><span class="sxs-lookup"><span data-stu-id="4d941-109">The **conceptual documentation** consists of a set of articles that are published to https://docs.microsoft.com/quantum, and that describe everything from the basics of quantum computing to the technical specifications for interchange formats.</span></span> <span data-ttu-id="4d941-110">Tyto články jsou napsány v [DocFX Markdownu (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), což je Markdownu varianta používaná pro vytváření bohatých sad dokumentace.</span><span class="sxs-lookup"><span data-stu-id="4d941-110">These articles are written in [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a Markdown variant used for creating rich documentation sets.</span></span>
- <span data-ttu-id="4d941-111">**Reference k rozhraní API** je sada stránek pro každou funkci Q #, operace a uživatelsky definované typy, které jsou publikovány na https://docs.microsoft.com/qsharp/api/.</span><span class="sxs-lookup"><span data-stu-id="4d941-111">The **API reference** is a set of pages for each Q# function, operation, and user-defined type, published to https://docs.microsoft.com/qsharp/api/.</span></span> <span data-ttu-id="4d941-112">Tyto stránky dokumentují vstupy a operace pro jednotlivé možné akce, spolu s příklady a odkazy na Další informace.</span><span class="sxs-lookup"><span data-stu-id="4d941-112">These pages document the inputs and operations to each callable, along with examples and links to more information.</span></span> <span data-ttu-id="4d941-113">Odkaz rozhraní API se automaticky extrahuje z malých dokumentů DFM ve zdrojovém kódu Q # jako součást každé vydané verze.</span><span class="sxs-lookup"><span data-stu-id="4d941-113">The API reference is automatically extracted from small DFM documents in Q# source code as a part of each release.</span></span>
- <span data-ttu-id="4d941-114">**Soubor readme<!---->. MD** , který je součástí jednotlivých ukázek a Kata, popisuje, jak použít tuto ukázku nebo Kata, co se zabývá a jak se vztahuje na zbytek vývojové sady pro plnění.</span><span class="sxs-lookup"><span data-stu-id="4d941-114">The **README<!---->.md** files included with each sample and kata describe how to use that sample or kata is used, what it covers, and how it relates to the rest of the Quantum Development Kit.</span></span> <span data-ttu-id="4d941-115">Tyto soubory jsou zapisovány pomocí [Markdownu (GFM)](https://github.github.com/gfm/), což je složitější alternativa k DFM, která je oblíbená pro připojení dokumentace přímo k úložištím kódu.</span><span class="sxs-lookup"><span data-stu-id="4d941-115">These files are written using [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), a more lightweight alternative to DFM that's popular for attaching documentation directly to code repositories.</span></span>

## <a name="contributing-to-the-conceptual-documentation"></a><span data-ttu-id="4d941-116">Přispívání do koncepční dokumentace</span><span class="sxs-lookup"><span data-stu-id="4d941-116">Contributing to the Conceptual Documentation</span></span> ##

<span data-ttu-id="4d941-117">Aby bylo možné přispívat do dokumentace k Koncepční dokumentaci nebo k souboru READme, pak začíná žádost o přijetí změn pro MicrosoftDocs/podklady [ **-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/** ](https://github.com/Microsoft/Quantum)prosazení nebo [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), jak je to vhodné.</span><span class="sxs-lookup"><span data-stu-id="4d941-117">To contribute an improvement to the conceptual or README documentation, then, starts with a pull request onto either [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum), or [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), as is appropriate.</span></span>
<span data-ttu-id="4d941-118">Další informace o žádostech o přijetí změn najdete níže, ale v současné době je k dispozici několik věcí, které byste měli mít na paměti při vylepšování dokumentace:</span><span class="sxs-lookup"><span data-stu-id="4d941-118">We'll describe more about pull requests below, but for now there's a few things that are good to keep in mind as you improve documentation:</span></span>

- <span data-ttu-id="4d941-119">Čtenáři přicházejí v dokumentaci k vývojové sadě pro spoustu velkých objemů dat z nejrůznějších pozadí.</span><span class="sxs-lookup"><span data-stu-id="4d941-119">Readers come to the Quantum Development Kit documentation from a very wide range of backgrounds.</span></span> <span data-ttu-id="4d941-120">Všichni od vysoce školních studentů, kteří se chtějí dozvědět něco nového a zajímavého až po držení vyučujícího, by měli být schopni získat z této dokumentace něco z přečtení.</span><span class="sxs-lookup"><span data-stu-id="4d941-120">Everyone from high school students looking to learn something new and exciting through to tenured faculty performing quantum computing research should be able to get something out of reading the documentation.</span></span> <span data-ttu-id="4d941-121">V rozsahu, ve kterém je to možné, nedělejte v rámci svých čtecích zařízení rozsáhlé znalosti, protože se dají jenom vysílat. Je nejužitečnější, pokud můžete zadat jasný a přístupný popis nebo můžete poskytnout odkazy na další zdroje, kde najdete další informace.</span><span class="sxs-lookup"><span data-stu-id="4d941-121">To the extent that's possible, please don't assume extensive knowledge on the part of your readers, as they may just be starting out. It's most helpful if you can provide clear and accessible descriptions, or can provide links to other resources for more information.</span></span>
- <span data-ttu-id="4d941-122">Sady dokumentace nejsou nastavované jako knihy nebo dokumenty. v těchto čtenářích dorazíte na to, co se může zdát jako střední.</span><span class="sxs-lookup"><span data-stu-id="4d941-122">Documentation sets aren't laid out like books or papers, in that readers will arrive in what might seem like the "middle."</span></span> <span data-ttu-id="4d941-123">Například vyhledávací stroje nemusí navrhovat index, nebo se jim může poslat odkaz, který se snaží s tím, že je bude pomáhat. Zkuste Pomocníkovi pomáhat tím, že vždy zadáte jasný kontext, spolu s odkazy tam, kde je to vhodné.</span><span class="sxs-lookup"><span data-stu-id="4d941-123">For example, search engines might not suggest the index, or they might have been sent a link by a friend trying to help them out. Try to help your reader by always providing a clear context, along with links where appropriate.</span></span>
- <span data-ttu-id="4d941-124">Někteří čtenáři naleznou abstraktní příkazy a definice, které jsou nejužitečnější, zatímco ostatní čtenáři fungují nejlépe pomocí extrapolace z konkrétních příkladů.</span><span class="sxs-lookup"><span data-stu-id="4d941-124">Some readers will find abstract statements and definitions most helpful, while other readers work best by extrapolating from concrete examples.</span></span> <span data-ttu-id="4d941-125">Poskytnutím obecného případu a specifických příkladů může pomocníkům získat maximum z programu.</span><span class="sxs-lookup"><span data-stu-id="4d941-125">Providing both the general case and specific examples can help both readers get the most out of quantum programming.</span></span>
- <span data-ttu-id="4d941-126">Zvlášť, pokud jste napsali i kód, který je dokumentován, může být zřejmé, že nebudete mít vůbec žádné zjevné pro čtenáře.</span><span class="sxs-lookup"><span data-stu-id="4d941-126">Especially if you also wrote the code being documented, things may be obvious to you that are not at all obvious to your reader.</span></span> <span data-ttu-id="4d941-127">Neexistuje žádný jedinečný způsob, jak programovat, takže bez ohledu na to, jakým způsobem chytřejší nebo se čtenář může stát, nemůžou odhadnout, jaké vzory návrhu se vám pro vyjádření vašich nápadů v kódu považují za užitečné.</span><span class="sxs-lookup"><span data-stu-id="4d941-127">There's no one unique best way to program, so no matter how clever or experienced a reader might be, they can't guess at what design patterns you found the most helpful to express your ideas in code.</span></span> <span data-ttu-id="4d941-128">Nemusíte mít jasné informace o tom, jak může čtenář očekávat použití kódu, což může přispět k poskytnutí tohoto kontextu.</span><span class="sxs-lookup"><span data-stu-id="4d941-128">Being clear about how a reader can expect to make use of your code can help provide that context.</span></span>
- <span data-ttu-id="4d941-129">Mnoho členů komunity pro programování po dobu nevyužívání předpisů je školními výzkumníky a jejich příspěvky se v komunitě uznávají hlavně prostřednictvím citace.</span><span class="sxs-lookup"><span data-stu-id="4d941-129">Many members of the quantum programming community are academic researchers, and are recognized mainly through citations for their contributions to the community.</span></span> <span data-ttu-id="4d941-130">Kromě pomoci čtenářů najít další materiály, aby se zajistilo správné uvedení školních výstupů, jako jsou například dokumenty, přednášky, blogové příspěvky a softwarové nástroje, mohou pomoci akademickým přispěvatelům zajistit jejich nejlepší práci pro zlepšení komunity.</span><span class="sxs-lookup"><span data-stu-id="4d941-130">In addition to helping readers find additional materials, making sure to properly cite academic outputs such as papers, talks, blog posts, and software tools can help academic contributors to keep doing their best work to improve the community.</span></span>
- <span data-ttu-id="4d941-131">Komunita pro programování pro velké množství je širokou a skvělou různorodou komunitou.</span><span class="sxs-lookup"><span data-stu-id="4d941-131">The quantum programming community is a broad and wonderfully diverse community.</span></span> <span data-ttu-id="4d941-132">Použití žen v prostředníkech v příkladech třetích osob (např.: "Pokud uživatel..., bude...") může fungovat jako vyloučené místo zahrnutí.</span><span class="sxs-lookup"><span data-stu-id="4d941-132">The use of gendered pronouns in third-person examples (e.g.: "if a user ..., he will ...") can work to exclude rather than include.</span></span> <span data-ttu-id="4d941-133">Společnost Cognizant jména lidí v citacích a odkazech a správným zahrnutím znaků, které nejsou ASCII, může obsluhovat různorodost komunity tím, že se bude brát ohled na její členy.</span><span class="sxs-lookup"><span data-stu-id="4d941-133">Being cognizant of people's names in citations and links, and of the correct inclusion of non-ASCII characters can serve the diversity of the community by showing respect to its members.</span></span> <span data-ttu-id="4d941-134">Podobně se mnoho slov v anglickém jazyce často používá Hateful způsobem, takže jejich použití v technické dokumentaci může způsobit poškození jak na jednotlivé čtenáře, tak na komunitě.</span><span class="sxs-lookup"><span data-stu-id="4d941-134">Similarly, many words in the English language are often used in a hateful manner, such that their use in technical documentation can cause harm both to individual readers and to the community at large.</span></span>

## <a name="contributing-to-the-api-references"></a><span data-ttu-id="4d941-135">Přispívání do referencí rozhraní API</span><span class="sxs-lookup"><span data-stu-id="4d941-135">Contributing to the API References</span></span> ##

<span data-ttu-id="4d941-136">Aby bylo možné přispívat do odkazů rozhraní API, je nejužitečnější otevřít žádost o přijetí změn přímo na dokumentovaném kódu.</span><span class="sxs-lookup"><span data-stu-id="4d941-136">To contribute an improvement to the API references, it's most helpful to open a pull request directly on the code being documented.</span></span>
<span data-ttu-id="4d941-137">Každá funkce, operace nebo uživatelsky definovaný typ podporuje dokumentační komentář (označený `///` místo `//`).</span><span class="sxs-lookup"><span data-stu-id="4d941-137">Each function, operation, or user-defined type supports a documentation comment (denoted with `///` instead of `//`).</span></span>
<span data-ttu-id="4d941-138">Když kompilujete jednotlivé verze vývojářské sady pro plnění, tyto komentáře se používají ke generování odkazu rozhraní API na https://docs.microsoft.com/qsharp/api/, včetně podrobností o vstupech a výstupech z jednotlivých vydaných odkazů, podle předpokladů, které jsou k dispozici, a příklady, jak je používat.</span><span class="sxs-lookup"><span data-stu-id="4d941-138">When we compile each release of the Quantum Development Kit, these comments are used to generate the API reference at https://docs.microsoft.com/qsharp/api/, including details about the inputs to and outputs from each callable, the assumptions each callable makes, and examples of how to use them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d941-139">Ujistěte se prosím, že jste ručně neupravili vygenerovanou dokumentaci k rozhraní API, protože tyto soubory jsou v každé nové verzi přepsány.</span><span class="sxs-lookup"><span data-stu-id="4d941-139">Please make sure to not manually edit the generated API documentation, as these files are overwritten with each new release.</span></span>
> <span data-ttu-id="4d941-140">Váš příspěvek připravujeme komunitě a chceme se ujistit, že vaše změny budou dál pomáhat uživatelům vydávat verze po vydání.</span><span class="sxs-lookup"><span data-stu-id="4d941-140">We value your contribution to the community, and want to make sure that your changes continue to help users release after release.</span></span>

<span data-ttu-id="4d941-141">Zvažte například funkci `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="4d941-141">For example, consider the function `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4d941-142">Komentář k dokumentaci by měl pomáhat uživateli, jak interpretovat `bits` a `oracle` a co je funkce pro.</span><span class="sxs-lookup"><span data-stu-id="4d941-142">A documentation comment should help a user learn how to interpret `bits` and `oracle` and what the function is for.</span></span>
<span data-ttu-id="4d941-143">Každou z těchto různých částí informací lze kompilátoru Q # poskytnout pomocí speciálně pojmenovaného oddílu Markdownu v komentáři k dokumentaci.</span><span class="sxs-lookup"><span data-stu-id="4d941-143">Each of these different pieces of information can be provided to the Q# compiler by a specially named Markdown section in the documentation comment.</span></span>
<span data-ttu-id="4d941-144">Pro příklad `ControlledOnBitString`můžeme napsat něco podobného jako následující:</span><span class="sxs-lookup"><span data-stu-id="4d941-144">For the example of `ControlledOnBitString`, we might write something like the following:</span></span>

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
<span data-ttu-id="4d941-145">Vykreslenou verzi kódu uvedenou výše můžete zobrazit v [dokumentaci k rozhraní API pro funkci `ControlledOnBitString`](xref:microsoft.quantum.canon.controlledonbitstring).</span><span class="sxs-lookup"><span data-stu-id="4d941-145">You can see the rendered version of the code above in the [API documentation for the `ControlledOnBitString` function](xref:microsoft.quantum.canon.controlledonbitstring).</span></span>

<span data-ttu-id="4d941-146">Kromě obecné praxe psaní dokumentace k rozhraní API, které vám pomůžou při psaní komentářů k rozhraní API, je potřeba mít na paměti pár věcí:</span><span class="sxs-lookup"><span data-stu-id="4d941-146">In addition to the general practice of documentation writing, in writing API documentation comments it helps to keep a few things in mind:</span></span>

- <span data-ttu-id="4d941-147">Formát každého komentáře k dokumentaci musí odpovídat, co kompilátor Q # očekává, aby se vaše dokumentace zobrazovala správně.</span><span class="sxs-lookup"><span data-stu-id="4d941-147">The format of each documentation comment has to match what the Q# compiler expects for your documentation to appear correctly.</span></span> <span data-ttu-id="4d941-148">Některé oddíly, například `/// # Remarks`, umožňují obsah volného tvaru, zatímco oddíly jako `/// # See Also` oddílu jsou více omezující.</span><span class="sxs-lookup"><span data-stu-id="4d941-148">Some sections, such as `/// # Remarks` allow for freeform content, while sections such as `/// # See Also` section are more restrictive.</span></span>
- <span data-ttu-id="4d941-149">Čtenář si může přečíst dokumentaci k rozhraní API na hlavním referenčním webu rozhraní API, na shrnutí každého oboru názvů nebo dokonce i v rámci integrovaného vývojového prostředí pomocí informací o přechodu myší.</span><span class="sxs-lookup"><span data-stu-id="4d941-149">A reader may read your API documentation on the main API reference site, on the summary for each namespace, or even from within their IDE through the use of hover information.</span></span> <span data-ttu-id="4d941-150">Ujistěte se, že `/// # Summary` delší než o větu pomáhá čtenářům rychle seřadit informace o tom, jestli je potřeba je přečíst nebo najít jinde, a může vám pomoci při rychlém procházení souhrnů oborů názvů.</span><span class="sxs-lookup"><span data-stu-id="4d941-150">Making sure that `/// # Summary` isn't longer than about a sentence helps your reader quickly sort out whether they need to read further or look elsewhere, and can help in quickly scanning through namespace summaries.</span></span>
- <span data-ttu-id="4d941-151">Vaše dokumentace může být hodně delší než samotný kód, ale je to v pořádku!</span><span class="sxs-lookup"><span data-stu-id="4d941-151">Your documentation may well wind up being much longer than the code itself, but that's OK!</span></span> <span data-ttu-id="4d941-152">I malá část kódu může mít neočekávané efekty pro uživatele, kteří neznají kontext, ve kterém tento kód existuje.</span><span class="sxs-lookup"><span data-stu-id="4d941-152">Even a small piece of code can have unexpected effects to users that don't know the context in which that code exists.</span></span> <span data-ttu-id="4d941-153">Poskytnutím konkrétních příkladů a jasným vysvětlením můžete uživatelům pomáhat s tím, že budou mít k dispozici nejlepší využití kódu, který je k dispozici.</span><span class="sxs-lookup"><span data-stu-id="4d941-153">By providing concrete examples and clear explanations, you can help users make the best use of the code that's available to them.</span></span>

<!-- ## LaTeX Formatting ##

**TODO** -->
