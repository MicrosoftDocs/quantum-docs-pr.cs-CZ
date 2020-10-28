---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706128"
---
# <a name="cumulativefolded-function"></a>CumulativeFolded – funkce

Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)

Balíček [](https://nuget.org/packages/)


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