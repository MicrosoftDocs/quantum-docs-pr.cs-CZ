---
uid: Microsoft.Quantum.Logical.Conditioned
title: Podmíněně – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817286"
---
# <a name="conditioned-function"></a>Podmíněně – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```