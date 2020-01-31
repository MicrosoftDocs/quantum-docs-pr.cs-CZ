---
title: Struktura souborů | Microsoft Docs
description: 'Struktura souborů Q #'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 364d353c55bda38f227456909755d13dc7e67080
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821078"
---
# <a name="file-structure"></a>Struktura souborů

Soubor Q # se skládá z sekvence deklarací oboru názvů.
Každá deklarace oboru názvů obsahuje deklarace pro uživatelsky definované typy, operace a funkce.
Deklarace oboru názvů může obsahovat libovolný počet každého typu deklarace a v libovolném pořadí.
Jediný text, který se může zobrazit mimo deklaraci oboru názvů, je komentáře.
Konkrétně dokumentační komentáře pro obor názvů předcházejí deklaraci.

## <a name="namespace-declarations"></a>Deklarace oboru názvů

Soubor Q # má obvykle přesně jednu deklaraci oboru názvů, ale může mít hodnotu None (a být prázdný nebo obsahovat pouze komentáře) nebo může obsahovat více oborů názvů.
Deklarace oboru názvů nesmí být vnořené.

Stejný obor názvů může být deklarován ve více souborech Q #, které jsou kompilovány společně, pokud neexistují deklarace typu, operace nebo funkce se stejným názvem.
Konkrétně je neplatný pro definování stejného typu ve stejném oboru názvů ve více souborech, a to i v případě, že deklarace jsou identické.

Deklarace oboru názvů se skládá z klíčového slova `namespace`následovaný názvem oboru názvů, levou složenou závorkou `{`, deklaracemi obsaženými v oboru názvů a `}`uzavírací závorkou.
Názvy oborů názvů následují podle vzoru .NET sekvence jednoho nebo více přípustných symbolů oddělených tečkami `.`.
Například `MyQuantumStuff` a `Microsoft.Quantum.Canon` jsou platné názvy oborů názvů.
Podle konvence jsou symboly v názvu oboru názvů velkými písmeny, ale to není vyžadováno.

Deklarace můžou být v libovolném pořadí v deklaraci oboru názvů.
Odkazy na typy nebo volat deklarované níže v souboru jsou správně vyřešeny. není nutné, aby deklarace typu, operace nebo funkce předcházely odkaz na ni.

## <a name="open-directives"></a>Otevřít direktivy

V rámci bloku oboru názvů lze použít direktivu `open` pro import všech typů a volání, která jsou definována v určitém oboru názvů a odkazují na ně podle jejich nekvalifikovaného názvu. 

Taková direktiva `open` sestává z klíčového slova `open` následovaným oborem názvů, který se má otevřít, a koncovým středníkem.

Například

```qsharp
open Microsoft.Quantum.Canon;
```

Volitelně může být definován krátký název pro otevřený obor názvů tak, aby všechny elementy z tohoto oboru názvů mohly (a musí) být kvalifikovány definovaným krátkým názvem. Tento krátký název je definován přidáním klíčového slova `as` následovaný požadovaným krátkým názvem před středníkem v direktivě `open`:

```qsharp
open Microsoft.Quantum.Math as Math;
```

Všechny direktivy `open` musí být uvedeny před všemi deklaracemi `function`, `operation`nebo `newtype` v bloku Namespace.
Direktiva `open` se vztahuje na celý blok oboru názvů v rámci souboru.

## <a name="user-defined-type-declarations"></a>Deklarace uživatelem definovaných typů

Q # poskytuje uživatelům způsob, jak deklarovat nové uživatelsky definované typy, jak je popsáno v části [model typu Q #](xref:microsoft.quantum.language.type-model) .
Uživatelsky definované typy jsou odlišné, i když základní typy jsou identické.
Konkrétně neexistuje žádný automatický převod mezi hodnotami dvou uživatelsky definovaných typů i v případě, že jsou základní typy identické.

Uživatelsky definovaná deklarace typu se skládá z klíčového slova `newtype`následovaný názvem uživatelsky definovaného typu, `=`, platné specifikace typu a ukončující středník.

Například:

```qsharp
newtype PairOfInts = (Int, Int);
```

Každý zdrojový soubor Q # může deklarovat libovolný počet uživatelsky definovaných typů.
Názvy typů musí být v rámci oboru názvů jedinečné a nemusí být v konfliktu s názvy operací a funkcí.

Mezi uživatelsky definovanými typy není možné definovat cyklické závislosti. Rekurzivní typy nejsou proto možné v rámci Q #.

## <a name="operation-declarations"></a>Deklarace operací

Operace jsou základem Q #, zhruba podobným funkcím v jiných jazycích.
Každý zdrojový soubor Q # může definovat libovolný počet operací.

Názvy operací musí být v rámci oboru názvů jedinečné a nemusí být v konfliktu s názvy typu a funkce.

Deklarace operací se skládají z klíčového slova `operation`následovaný symbolem, který představuje název operace, typ řazené kolekce členů definující argumenty operace, dvojtečku `:`, anotaci typu, která popisuje typ výsledku operace, volitelně poznámku s charakteristikou operace, levou složenou závorku `{`, tělo deklarace operace a Poslední uzavírací závorku `}`.

Tělo deklarace operace se skládá buď z výchozí implementace, nebo ze seznamu specializací.
Výchozí implementaci lze zadat přímo v rámci deklarace, pokud je nutné explicitně zadat pouze implementaci výchozí specializace těla.
V tomto případě Poznámka s charakteristikou operace v deklaraci je užitečná pro zajištění, že kompilátor automaticky generuje jiné specializace na základě výchozí implementace. 

Například 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

Charakteristiky operace definují, jaké druhy funktory lze použít pro deklarovanou operaci a jaký má vliv. Pokud operace implementuje jednotnou transformaci, je možné definovat způsob, jakým operace funguje při *adjointed* nebo *řízených*.
Existence těchto specializací se dá deklarovat jako součást signatury operace. Odpovídající implementace pro každou takovou implicitně deklarovanou specializaci je následně vygenerována kompilátorem. V předchozím příkladu jsou v kompilátoru generovány sousední a řízené specializace. 

V případě, že se implementace nemůže generovat kompilátorem, je možné ji explicitně zadat. Tyto explicitní deklarace specializace mohou být buď tvořeny vhodnou direktivou generace, která vysvětluje, jak je konkrétní specializace sestavena, nebo uživatelem definovaná implementace. Kód v `PrepareEntangledPair` výše je například ekvivalentní následujícímu kódu, který obsahuje explicitní deklarace specializace: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
Klíčové slovo `auto` označuje, že kompilátor by měl určit, jak se má vygenerovat implementace specializace.
Pokud kompilátor nemůže vygenerovat implementaci pro určitou specializaci bez dalších pokynů, jako je přesnější direktiva generace, nebo pokud je možné zadat účinnější implementaci, pak může být implementace také ručně definovaná.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```

Ve výše uvedeném příkladu `adjoint invert;` označuje, že specializace sousedící-by měla být vygenerována vrácením implementace těla a `controlled adjoint invert;` označuje, že řízená specializace, která je řízena, je vygenerována obrácením dané implementace řízené specializace.

Aby operace podporovala použití `Adjoint` a/nebo `Controlled` funktor, musí být jeho návratový typ nutně `Unit`. 


### <a name="explicit-specialization-declarations"></a>Explicitní deklarace specializace

Operace Q # můžou obsahovat následující explicitní deklarace specializace:

- Specializace `body` určuje implementaci operace bez použití funktory.
- Specializace `adjoint` určuje implementaci operace s aplikovaným `Adjoint` funktor.
- Specializace `controlled` určuje implementaci operace s aplikovaným `Controlled` funktor.
- Specializace `controlled adjoint` určuje implementaci operace s použitým `Adjoint`m i `Controlled`m funktory.
  Tato specializace může mít také název `adjoint controlled`, protože dvě dojíždění do funktory.


Specializace operace se skládá z tagu specializace (například `body`nebo `adjoint`atd.) následovaný jedním z těchto:

- Explicitní deklarace, jak je popsáno níže.
- Direktiva, která instruuje kompilátor, jak vygenerovat specializaci, jedna z těchto:
  - `intrinsic`, která označuje, že specializace je poskytována cílovým počítačem.
  - `distribute`, které lze použít s specializacemi `controlled` a `controlled adjoint`.
    Při použití s `controlled`označuje, že má kompilátor vypočítat specializaci použitím `Controlled` na všechny operace v `body`.
    Při použití s `controlled adjoint`označuje, že má kompilátor vypočítat specializaci použitím `Controlled` na všechny operace v rámci `adjoint` specializace.
  - `invert`, která označuje, že má kompilátor vypočítat `adjoint` specializaci, vrácením `body`, tj. zrušením pořadí operací a aplikováním sousedících na každý.
    Při použití s `adjoint controlled`to znamená, že kompilátor má vypočítat specializaci vrácením `controlled` specializace.
  - `self`pro indikaci, že specializace přiléhajícího je stejná jako `body` specializace.
    To je platné pro `adjoint` a `adjoint controlled` specializace.
    Pro `adjoint controlled``self` znamená, že specializace `adjoint controlled` je stejná jako `controlled` specializace.
  - `auto`, aby označoval, že má kompilátor vybrat vhodnou direktivu, která se má použít.
    `auto` se nedá použít pro specializaci `body`.

Direktivy a `auto` všechny vyžadují uzavírání středníkem `;`.
Direktiva `auto` překládá na následující direktivu generace, pokud je k dispozici explicitní deklarace `body`:

- Specializace `adjoint` je vygenerována podle direktivy `invert`.
- Specializace `controlled` je vygenerována podle direktivy `distribute`.
- Specializace `adjoint controlled` je vygenerována podle direktivy `invert`, pokud je zadána explicitní deklarace pro `controlled`, ale ne jednu pro `adjoint`a `distribute` jinak.

> [!TIP]   
> Pokud je operace samostatně sousedící, explicitně určete buď sousední, nebo řízená sousední specializace, pomocí direktivy generace `self`, aby kompilátor mohl používat tyto informace pro účely optimalizace.

Deklarace specializace obsahující uživatelsky definovanou implementaci se skládá z argumentů řazené kolekce členů následovaný blokem příkazu Q #, který implementuje specializaci.
V seznamu argumentů se `...` slouží k reprezentaci argumentů deklarovaných pro operaci jako celku.
Pro `body` a `adjoint`by měl být seznam argumentů vždy `(...)`; v případě `controlled` a `adjoint controlled`by měl být seznam argumentů symbolem, který představuje pole ovládacího prvku qubits, po kterém následuje `...`, uzavřené v závorkách. například `(controls,...)`.

Pokud je nutné explicitně deklarovat jednu nebo více specializací, než je výchozí tělo, musí být implementace pro výchozí tělo zabalena do vhodné deklarace specializace:

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a>Sousednít

Sousední operace v operaci určuje, jak je implementace komplexní sdružené operace implementována, tj. způsob, jakým operace funguje v opačném případě.
Je právní určení operace bez souseda; například operace měření nemají žádný sousední, protože nejsou inverzi.
Operace podporuje `Adjoint` funktor, pokud jeho deklarace obsahuje implicitní nebo explicitní deklaraci sousední specializace.
Explicitně deklarovaná řízená specializace typu předpokládá existenci sousedící specializace. 

Pro operaci, jejíž tělo obsahuje smyčky Repeat-do-úspěch, nastavte příkazy, měření, příkazy Return nebo volání jiných operací, které nepodporují `Adjoint` funktor, automatické generování sousední specializace ' po `invert` nebo `auto` direktivy není možné.

### <a name="controlled"></a>Kontrol

Řízená verze operace určuje, jak je verze operace řízená procesorem, tj. to, jak operace funguje, když se aplikuje v podmínkách pro stav registru.
V části [řízená](xref:microsoft.quantum.language.type-model#controlled) je uveden Úplnější popis.

Je právní určení operace bez řízené verze; například operace měření nemají žádnou řízenou verzi, protože nejsou ovladatelné.
Operace podporuje `Controlled` funktor pouze v případě, že deklarace obsahuje implicitní nebo explicitní deklaraci řízené specializace.
Explicitně deklarovaná řízená specializace typu předpokládá existenci řízené specializace. 

Pro operaci, jejíž tělo obsahuje volání do jiných operací, které nepodporují `Controlled` funktor, automatické generování řízené specializace následující po `distribute` nebo `auto` direktivy není možné.

### <a name="controlled-adjoint"></a>Řízený sousedící

Řízená verze inřízených operací operace určuje, jak je implementována verze sousedících operací s řízenou počátečními událostmi.
Je právní určení operace bez řízené sousední verze; například operace měření nemají řízenou sousední verzi, protože nejsou ani ovladatelné ani inverzi.

Řízená sousední specializace pro operaci musí existovat, pokud je a jenom v případě, že existují sousední i řízená specializace. V takovém případě je existence řízené specializace instalovaná a příslušná specializace je vygenerována kompilátorem, pokud nebyla explicitně definována žádná implementace. 

Pro operaci, jejíž tělo obsahuje volání na jiné operace, které nemají řízenou sousední verzi, automatické generování sousední specializace typu, která následuje po `invert`, `distribute` nebo `auto` direktiva není možná.


### <a name="examples"></a>Příklady

Deklarace operace může být jednoduchá, jak je uvedeno níže, což definuje primitivní operaci Pauli X:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

Následující definuje operaci teleport.

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a>Deklarace funkcí

Funkce jsou čistě klasickými rutinami v Q #.
Každý zdrojový soubor Q # může definovat libovolný počet funkcí.

Deklarace funkce se skládá z klíčového slova `function`následovaný symbolem, který je název funkce, typ řazené kolekce členů, anotace typu, která popisuje návratový typ funkce, a blok příkazu, který popisuje implementaci funkce.

Blok příkazů definující funkci musí být uzavřený v `{` a `}` jako jakýkoli jiný blok příkazů.

Názvy funkcí musí být jedinečné v rámci oboru názvů a nemusí být v konfliktu s názvy operací a typů.
Funkce nemusí přidělovat ani půjčovat qubits nebo volat operace. Částečné použití operací nebo předávání hodnot typu operace je přesné.

Například:

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```
