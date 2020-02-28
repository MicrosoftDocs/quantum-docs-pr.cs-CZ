---
title: 'Lokální proměnné – techniky Q #'
description: 'Naučte se definovat a pracovat s místními proměnnými v Q #.'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: cb6c662137c31a13c3dd6e9ca3f67879c469f788
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906861"
---
# <a name="local-variables"></a>Místní proměnné #

Hodnotu libovolného typu v Q # lze přiřadit proměnné pro opětovné použití v rámci operace nebo funkce pomocí klíčového slova `let`.
Příklad:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

To přiřadí konkrétní pole operátorů Pauli proměnné s názvem `measurementOperator`.

> [!TIP]
> Všimněte si, že nepotřebujeme explicitně zadat typ naší nové proměnné, protože výraz na pravé straně příkazu `let` je nejednoznačný a tento typ je odvozený kompilátorem. 

Proměnné v Q # jsou *neměnné*, což znamená, že jakmile je proměnná definována tímto způsobem, nelze ji již žádným způsobem změnit.
To umožňuje několik užitečných optimalizací, včetně optimalizace klasické logiky, která působí na proměnné, aby bylo možné použít `Adjoint` variantu operace.

Proměnné definované pomocí vazby `let`, jak je uvedeno výše, jsou místní pro určitý rozsah, jako je například tělo operace nebo obsah `for` smyčky.


## <a name="mutability"></a>Proměnlivost ##

Jako alternativu k vytvoření proměnné pomocí `let`klíčové slovo `mutable` vytvoří speciální proměnlivou proměnnou, která může být po prvním vytvoření pomocí klíčového slova `set` znovu svázána.

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

Všechny typy v Q #, včetně polí, dodržují sémantiku hodnot. Konkrétně není možné aktualizovat položky pole. Chcete-li upravit existující pole, je nutné využívat mechanismus kopírování a aktualizace podobně jako u záznamů v F#nástroji. Pomocí nástrojů knihovny pro pole, která jsou k dispozici v [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), můžeme například snadno definovat funkci, která vrací pole Paul, kde Pauli na indexu `i` přebírá danou hodnotu a všechny ostatní položky jsou identity: 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

Podíváme se na to, jak pracovat s poli při diskuzi o příkazech a výrazech Q #. 

Proměnlivost v rámci Q # je koncept, který se vztahuje na *symbol* , nikoli na typ nebo hodnotu. Konkrétně neobsahuje reprezentace v systému typů, implicitně nebo explicitně a zda je vazba proměnlivá (jak je uvedeno v klíčovém slovu `mutable`) nebo neměnných (jak je uvedeno v `let`) nemění typ vázaných proměnných. To poskytuje důležitý způsob, jak izolovat proměnlivost uvnitř specializovaných funkcí a operací.
Zejména i v případě, že se v rámci operace, která používá proměnlivou proměnnou, nemůže automaticky generovat automaticky generovaná specializace typu, může automatická generace fungovat pro operaci, která volá funkci, která používá proměnlivost.
Z tohoto důvodu je vhodné provádět funkce a operace, které používají proměnlivost co nejkratší a kompaktní, aby zbytek programu pro práci s více operačními systémem mohl být napsán pomocí běžných neměnných proměnných.


## <a name="deconstruction"></a>Dekonstrukce ##

Kromě přiřazování jedné proměnné, klíčová slova `let` a `mutable` – nebo ve skutečnosti jakékoliv jiné konstrukce vazby – umožňují také rozbalení obsahu [typu řazené kolekce členů](xref:microsoft.quantum.language.type-model#tuple-types).
Přiřazení tohoto formuláře se říká k *dekonstrukci* prvků této řazené kolekce členů.
Například pokud budeme modelovat pojem v Hamiltonian podle řazené kolekce členů, můžeme použít dekonstrukci k přístupu k různým datům, ke kterým musíme simulovat za tento termín:

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


