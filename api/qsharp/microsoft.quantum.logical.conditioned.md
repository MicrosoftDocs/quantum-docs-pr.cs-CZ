---
uid: Microsoft.Quantum.Logical.Conditioned
title: Podmíněně – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: 8aabe8b018129ddee3b934c207d0a62e59fb6f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707056"
---
# <a name="conditioned-function"></a>Podmíněně – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček [](https://nuget.org/packages/)


Vrátí jednu ze dvou hodnot v závislosti na hodnotě logické podmínky.

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a>Vstup

### <a name="condition--bool"></a>podmínka: [bool](xref:microsoft.quantum.lang-ref.bool)

Podmínka sloužící k řízení, který vstup je vrácen.


### <a name="iftrue--t"></a>Hodnotu ifTrue: 'T

Hodnota, která má být vrácena, pokud `condition` je `true` .


### <a name="iffalse--t"></a>Hodnotu IfFalse: 'T

Hodnota, která má být vrácena, pokud `condition` je `false` .



## <a name="output--t"></a>Výstup: 'T

`ifTrue` Pokud `condition` je `true` , a `ifFalse` jinak.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="remarks"></a>Poznámky

Na rozdíl od `?|` operátoru Tato funkce nemá krátký okruh, takže oba vstupy jsou plně vyhodnoceny.

V případě chování až po krátkého okruhu jsou následující ekvivalenty:

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```