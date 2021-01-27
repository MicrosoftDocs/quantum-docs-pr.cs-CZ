---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: 95cd5233a09a1234bba4de9fe870b9d93c0f86a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846250"
---
# <a name="cumulativefolded-function"></a>CumulativeFolded – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kombinuje namapovaná a přeložení na jednu funkci

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>Popis

Tato funkce provede iteraci `fn` funkce prostřednictvím pole, počínaje počátečním stavem `state` a vrátí všechny mezilehlé hodnoty, včetně počátečního stavu.

## <a name="input"></a>Vstup

### <a name="fn--statet---state"></a>FN: (' State, t)-> ' State

Funkce, která se má v poli přeloží


### <a name="state--state"></a>stav: stav

Počáteční stav, který se má přeloží


### <a name="array--t"></a>Array: t []

Pole hodnot, které se mají přeloží



## <a name="output--state"></a>Výstup: State []

Všechny přechodné stavy, včetně konečného stavu, ale ne počátečního stavu.
Délka výstupního pole má stejnou délku jako `array` .

## <a name="type-parameters"></a>Parametry typu

### <a name="state"></a>Stav

Typ stavů, na kterých `fn` funkce funguje, tj., přijímá jako první vstup a vrátí.
### <a name="t"></a>'S

Typ `array` prvků.

## <a name="example"></a>Příklad

```qsharp
// same as sums = [1, 3, 6, 10, 15]
let sums = CumulativeFolded(PlusI, 0, SequenceI(1, 5));
```