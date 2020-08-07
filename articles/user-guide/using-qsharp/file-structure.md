---
title: Q#Struktura souborů
description: Popisuje strukturu a syntaxi Q# souboru.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: ac73962b1a718cd04aa87ee3476c66781fe3ac2b
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867926"
---
# <a name="no-locq-file-structure"></a>Q#Struktura souborů

Q#Soubor se skládá z sekvence *deklarací oboru názvů*.
Každá deklarace oboru názvů obsahuje deklarace pro uživatelsky definované typy, operace a funkce a může obsahovat libovolný počet každého typu deklarace a v libovolném pořadí.
Další informace o deklaracích v rámci oboru názvů najdete v tématu [uživatelsky definované typy](xref:microsoft.quantum.guide.types#user-defined-types), [operace](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)a [funkce](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).

Jediný text, který se může zobrazit mimo deklaraci oboru názvů, je komentáře.
Konkrétně dokumentační komentáře pro obor názvů předcházejí deklaraci. Další informace najdete v [dokumentačních komentářích](#documentation-comments) v tomto článku. 

## <a name="namespace-declarations"></a>Deklarace oboru názvů

Q#Soubor obvykle obsahuje pouze jednu deklaraci oboru názvů, ale může mít hodnotu None (a být prázdný nebo obsahovat pouze komentáře) nebo může obsahovat více oborů názvů.
Deklarace oboru názvů nelze vnořovat.

Můžete deklarovat stejný obor názvů ve více Q# souborech, které jsou kompilovány společně, pokud neexistují deklarace typu, operace nebo funkce se stejným názvem.
Konkrétně je neplatný pro definování stejného typu ve stejném oboru názvů ve více souborech, a to i v případě, že deklarace jsou identické.

Deklarace oboru názvů se skládá z klíčového slova `namespace` , následovaný názvem oboru názvů a deklaracemi obsaženými v oboru názvů uzavřenými ve složených závorkách `{ }` .
Názvy oborů názvů následují podle vzoru .NET sekvence jednoho nebo více přípustných symbolů oddělených tečkami `.` .
Například `MyQuantumStuff` a `Microsoft.Quantum.Intrinsic` jsou platné názvy oborů názvů.
Podle konvence na velká písmena v názvu oboru názvů to ale není potřeba.

Odkazy na typy nebo volat deklarované níže v souboru jsou správně přeloženy; není nutné, aby deklarace typu, operace nebo funkce předcházely odkaz na ni.

## <a name="open-directives"></a>Otevřít direktivy

V rámci bloku oboru názvů použijte `open` direktivu pro import všech typů a volání deklarované v určitém oboru názvů a odkazujte na ně podle jejich nekvalifikovaného názvu.
Taková `open` direktiva se skládá z `open` klíčového slova, za nímž následuje obor názvů, který se má otevřít a ukončující středník.

> [!NOTE] 
> Všechny `open` direktivy musí být uvedeny před všemi `function` `operation` `newtype` deklaracemi, nebo v bloku Namespace.

Volitelně můžete definovat krátký název pro otevřený obor názvů. Pokud je definován krátký název, je nutné kvalifikovat všechny prvky z oboru názvů pomocí definovaného krátkého názvu. Například s ohledem na následující deklaraci oboru názvů a direktivy Open,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

Pokud deklarovaná operace používá operaci `Op` z `Microsoft.Quantum.Intrinsic` , zavolejte ji jednoduše pomocí `Op` .
Chcete-li však volat určitou funkci `Fn` z `Microsoft.Quantum.Math` , je nutné ji volat pomocí `Math.Fn` .

`open`Direktiva se vztahuje na celý blok oboru názvů v rámci souboru.
Proto pokud definujete další obor názvů ve stejném Q# souboru jako `NS` dříve, pak všechny operace, funkce/typy definované v druhém oboru názvů nebudou mít přístup k cokoli z `Microsoft.Quantum.Intrinsic` nebo, `Microsoft.Quantum.Math` Pokud jste neopakovali direktivy Open v rámci. 

Chcete-li odkazovat na typ nebo volat, který je definován v jiném oboru názvů, *který není otevřen* v aktuálním oboru názvů, je nutné na něj odkazovat pomocí plně kvalifikovaného názvu.
Například s ohledem na operaci s názvem `Op` z `X.Y` oboru názvů:

* Je nutné na něj odkazovat pomocí plně kvalifikovaného názvu `X.Y.Op` , pokud `X.Y` obor názvů nebyl otevřen dříve v aktuálním bloku. 
* I v případě `X` , že je obor názvů otevřený, není možné odkazovat na operaci jako `Y.Op` .
* Pokud jste definovali krátký název `Z` `X.Y` v tomto oboru názvů a souboru, musíte odkazovat na `Op` `Z.Op` . 

Je obvykle lepší zahrnout obor názvů pomocí `open` direktivy.
Použití plně kvalifikovaného názvu je vyžadováno, pokud dva obory názvů definují konstrukce se stejným názvem a aktuální zdroj používá konstrukce z obou.

Q#řídí se stejnými pravidly pro pojmenování jako jiné jazyky .NET.
Nicméně nepodporuje Q# relativní odkazy na obory názvů.
Například pokud je obor názvů `a.b` otevřený, odkaz na operaci s názvem se `c.d` nevyřeší na *not* operaci s úplným názvem `a.b.c.d` .

## <a name="formatting"></a>Formátování

Většina Q# příkazů a direktiv končí zakončeným středníkem, `;` .
Příkazy a deklarace, jako například `for` a `operation` , které končí blokem příkazu (viz následující oddíl), nevyžadují ukončující středník.
Každý Popis příkazu Poznamenejte, zda je nutný ukončovací středník.

Příkazy, jako jsou výrazy, deklarace a direktivy, mohou být rozděleny na více řádků.
Vyhněte se vložení více příkazů na jeden řádek.

## <a name="statement-blocks"></a>Bloky příkazů

Q#příkazy jsou seskupeny do bloků příkazů, které jsou obsaženy ve složených závorkách `{ }` . Blok příkazu začíná levou `{` a ukončenou uzávěrkou `}` .

Blok příkazu, který je vložený v jiném bloku, se považuje za dílčí blok obsahujícího bloku. obsahující a dílčí bloky se označují také jako vnější a vnitřní bloky.

## <a name="comments"></a>Komentáře

Komentáře začínají dvěma lomítky, `//` a pokračují až do konce řádku.
Komentář se může objevit kdekoli ve Q# zdrojovém souboru.

## <a name="documentation-comments"></a>Komentáře dokumentace

Komentáře, které začínají třemi lomítky, `///` , jsou zpracovány speciálně kompilátorem, když se objeví bezprostředně před definicí oboru názvů, operace, specializace, funkce nebo typu.
V takovém případě ho kompilátor považuje za dokumentaci pro definovaný typ, který je k nebo uživatelsky definovaný, stejně jako ostatní jazyky .NET.

V rámci `///` komentářů se text, který se má zobrazit jako součást dokumentace k rozhraní API, formátuje jako [Markdownu](https://daringfireball.net/projects/markdown/syntax), s různými částmi dokumentace, které jsou označeny pomocí hlaviček se speciálně jmenovanými.
V Markdownu použijte `@"<ref target>"` rozšíření pro operace křížového odkazu, funkce a uživatelsky definované typy v Q# . Nahraďte `<ref target>` plně kvalifikovaným názvem odkazovaného objektu kódu.
Různé moduly dokumentace můžou podporovat i další rozšíření Markdownu.

Příklad:

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

Následující názvy jsou platné jako hlavičky komentáře k dokumentaci.

- **Summary**: stručný souhrn chování funkce nebo operace nebo účelu typu. První odstavec souhrnu se používá pro informace o přechodu myší. Měl by být prostý text.
- **Popis**: Popis chování funkce nebo operace nebo účelu typu. Souhrn a popis společně tvoří vygenerovaný soubor dokumentace pro funkci, operaci nebo typ.
  Popis podporuje vložené symboly a rovnice ve formátu LaTeX.
- **Input**: Popis vstupní řazené kolekce členů pro operaci nebo funkci.
  Může obsahovat další pododdíly Markdownu označující jednotlivé prvky vstupní řazené kolekce členů.
- **Výstup**: Popis řazené kolekce členů vrácený operací nebo funkcí.
- **Parametry typu**: prázdný oddíl, který obsahuje jeden další pododdíl pro každý parametr obecného typu.
- **Příklad**: krátký příklad operace, funkce nebo typu, který se používá.
- **Poznámky**: různé prose popisující nějaký aspekt operace, funkce nebo typu.
- **Viz také**: seznam plně kvalifikovaných názvů, které označují související funkce, operace nebo uživatelsky definované typy.
- **Odkazy**: seznam odkazů a citace pro popsanou položku.

## <a name="next-steps"></a>Další kroky

Přečtěte si o [operacích a funkcích](xref:microsoft.quantum.guide.operationsfunctions) v Q# .