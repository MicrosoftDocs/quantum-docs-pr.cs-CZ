---
title: 'Struktura souborů Q #'
description: 'Popisuje strukturu a syntaxi souboru Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: b8c24dae6cc8d8f37ad4f1f74017c05cabe3a4b4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327454"
---
# <a name="q-file-structure"></a>Struktura souborů Q #

Každá operace Q #, funkce a uživatelsky definovaný typ je definována v rámci oboru názvů.

Soubor Q # se skládá z sekvence *deklarací oboru názvů*.
Každá deklarace oboru názvů obsahuje deklarace pro uživatelsky definované typy, operace a funkce.
Deklarace oboru názvů může obsahovat libovolný počet každého typu deklarace a v libovolném pořadí.
Pomocí těchto odkazů můžete zobrazit další podrobnosti o deklaraci [uživatelsky definovaných typů](xref:microsoft.quantum.guide.types#user-defined-types), [operací](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)a [funkcí](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) v rámci oboru názvů.

Jediný text, který se může zobrazit mimo deklaraci oboru názvů, je komentáře.
Konkrétně dokumentační komentáře (další podrobnosti níže) pro obor názvů předchází deklaraci.

## <a name="namespace-declarations"></a>Deklarace oboru názvů

Soubor Q # má obvykle přesně jednu deklaraci oboru názvů, ale může mít hodnotu None (a být prázdný nebo obsahovat pouze komentáře) nebo může obsahovat více oborů názvů.
Deklarace oboru názvů nesmí být vnořené.

Stejný obor názvů může být deklarován ve více souborech Q #, které jsou kompilovány společně, pokud neexistují deklarace typu, operace nebo funkce se stejným názvem.
Konkrétně je neplatný pro definování stejného typu ve stejném oboru názvů ve více souborech, a to i v případě, že deklarace jsou identické.

Deklarace oboru názvů se skládá z klíčového slova `namespace` , za kterým následuje název oboru názvů, levou složenou závorku `{` , deklarace obsažená v oboru názvů a uzavírací závorka `}` .
Názvy oborů názvů následují podle vzoru .NET sekvence jednoho nebo více přípustných symbolů oddělených tečkami `.` .
Například `MyQuantumStuff` a `Microsoft.Quantum.Intrinsic` jsou platné názvy oboru názvů.
Podle konvence jsou symboly v názvu oboru názvů velkými písmeny, ale to není vyžadováno.

Odkazy na typy nebo volat deklarované níže v souboru jsou správně vyřešeny. není nutné, aby deklarace typu, operace nebo funkce předcházely odkaz na ni.

## <a name="open-directives"></a>Otevřít direktivy

V rámci bloku oboru názvů `open` lze direktivu použít k importu všech typů a volání deklarovaných v určitém oboru názvů a jejich odkazování podle jejich nekvalifikovaného názvu.
Taková `open` direktiva se skládá z `open` klíčového slova, za nímž následuje obor názvů, který se má otevřít a ukončující středník.

> [!NOTE] 
> Všechny `open` direktivy musí být uvedeny před všemi `function` `operation` `newtype` deklaracemi, nebo v bloku Namespace.

Volitelně může být definován krátký název pro otevřený obor názvů tak, aby všechny elementy z tohoto oboru názvů mohly (a musí) být kvalifikovány definovaným krátkým názvem. Například s ohledem na následující deklaraci oboru názvů a direktivy Open,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

Pokud operace, kterou deklarujeme, používá operaci `Op` z `Microsoft.Quantum.Intrinsic` , budeme ji volat jednoduše pomocí `Op` .
Nicméně, pokud jsme chtěli zavolat určitou funkci `Fn` z `Microsoft.Quantum.Math` , museli byste ji volat pomocí `Math.Fn` .

`open`Direktiva se vztahuje na celý blok oboru názvů v rámci souboru.
Proto pokud jsme museli definovat další obor názvů ve stejném souboru Q # jako v `NS` předchozím kroku, pak všechny operace, funkce/typy definované v druhém oboru názvů nebudou mít přístup k cokoli z `Microsoft.Quantum.Intrinsic` nebo `Microsoft.Quantum.Math` , pokud jsme neopakovali otevřené direktivy Open v rámci. 

Typ nebo volat, který je definován v jiném oboru názvů, *který není otevřen* v aktuálním oboru názvů, musí být odkazován pomocí jeho plně kvalifikovaného názvu.
Například operace s názvem `Op` z `X.Y` oboru názvů musí být odkazována pomocí plně kvalifikovaného názvu `X.Y.Op` , pokud `X.Y` obor názvů nebyl otevřen dříve v aktuálním bloku. Jak je uvedeno výše, i když byl `X` obor názvů otevřen, není možné odkazovat na operaci jako `Y.Op` .
Pokud byl `Z` `X.Y` v tomto oboru názvů a souboru definován krátký název, `Op` musí být odkazován jako `Z.Op` . 

Je obvykle lepší zahrnout obor názvů pomocí `open` direktivy.
Použití plně kvalifikovaného názvu je vyžadováno, pokud dva obory názvů definují konstrukce se stejným názvem a aktuální zdroj používá konstrukce z obou.

Q # se řídí stejnými pravidly pro pojmenování jako jiné jazyky .NET.
Q # ale nepodporuje relativní odkazy na obory názvů.
To znamená, že pokud byl obor názvů `a.b` otevřen, odkaz na operaci s názvem `c.d` nebude přeložen *not* na operaci s úplným názvem `a.b.c.d` .

## <a name="formatting"></a>Formátování

Většina příkazů Q # a direktiv končí zakončeným středníkem, `;` .
Příkazy a deklarace, jako například `for` a `operation` , které končí blokem příkazu (viz níže), nevyžadují ukončující středník.
Každý Popis příkazu Poznamenejte, zda je nutný ukončovací středník.

Příkazy, jako jsou výrazy, deklarace a direktivy, mohou být rozděleny na více řádků.
Je třeba zabránit více příkazům na jednom řádku.

## <a name="statement-blocks"></a>Bloky příkazů

Příkazy Q # jsou seskupeny do bloků příkazů.
Blok příkazu začíná levou `{` a ukončenou uzávěrkou `}` .

Blok příkazu, který je vložený v jiném bloku, se považuje za dílčí blok obsahujícího bloku. obsahující a dílčí bloky se označují také jako vnější a vnitřní bloky.

## <a name="comments"></a>Komentáře

Komentáře začínají dvěma lomítky, `//` a pokračují až do konce řádku.
Komentář se může objevit kdekoli ve zdrojovém souboru Q #.

## <a name="documentation-comments"></a>Komentáře dokumentace

Komentáře, které začínají třemi lomítky, `///` , jsou zpracovány speciálně kompilátorem, když se objeví bezprostředně před definicí oboru názvů, operace, specializace, funkce nebo typu.
V takovém případě je jejich obsah považován za dokumentaci pro definovaný typ s možnou podporou nebo uživatelem, jako u jiných jazyků .NET.

V rámci `///` komentářů se text, který se má zobrazit jako součást dokumentace k rozhraní API, formátuje jako [Markdownu](https://daringfireball.net/projects/markdown/syntax), s různými částmi dokumentace, které jsou označeny pomocí hlaviček se speciálně jmenovanými.
V rámci rozšíření na Markdownu mohou být křížové odkazy na operace, funkce a uživatelsky definované typy v Q # zahrnuty pomocí `@"<ref target>"` , kde `<ref target>` je nahrazen plně kvalifikovaným názvem odkazovaného objektu kódu.
V případě potřeby může také modul dokumentace podporovat další rozšíření Markdownu.

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

Následující názvy se rozpoznávají jako hlavičky komentářů k dokumentaci.

- **Summary**: stručný souhrn chování funkce nebo operace nebo účelu typu. První odstavec souhrnu se používá pro informace o přechodu myší. Měl by být prostý text.
- **Popis**: Popis chování funkce nebo operace nebo účelu typu. Souhrn a popis jsou zřetězeny, aby tvořily vygenerovaný soubor dokumentace pro funkci, operaci nebo typ.
  Popis může obsahovat symboly a rovnice ve formátu LaTeX v řádcích.
- **Input**: Popis vstupní řazené kolekce členů pro operaci nebo funkci.
  Může obsahovat další pododdíly Markdownu označující jednotlivé prvky vstupní řazené kolekce členů.
- **Výstup**: Popis řazené kolekce členů vrácený operací nebo funkcí.
- **Parametry typu**: prázdný oddíl, který obsahuje jeden další pododdíl pro každý parametr obecného typu.
- **Příklad**: krátký příklad operace, funkce nebo typu se používá.
- **Poznámky**: různé prose popisující nějaký aspekt operace, funkce nebo typu.
- **Viz také**: seznam plně kvalifikovaných názvů, které označují související funkce, operace nebo uživatelsky definované typy.
- **Odkazy**: seznam odkazů a citace pro položku, která je popsána.

## <a name="next-steps"></a>Další kroky

Přečtěte si o [operacích a funkcích](xref:microsoft.quantum.guide.operationsfunctions) v Q #.