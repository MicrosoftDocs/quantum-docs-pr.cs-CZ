---
uid: Microsoft.Quantum.Logical.Or
title: Or – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 7093d908696a8cfda6b5ef648f9dfafcfac97144
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197122"
---
# <a name="or-function"></a>Or – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí logickou disjunkci dvou hodnot.

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Vstup

### <a name="a--bool"></a>Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)

První hodnota, která má být považována za.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Druhá hodnota, která má být považována za.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` pouze v případě, že `a` `b` jsou nebo `true` .

## <a name="remarks"></a>Poznámky

Na rozdíl od `or` operátoru Tato funkce nemá krátký okruh, takže oba vstupy jsou plně vyhodnoceny.

V případě chování až po krátkého okruhu jsou následující ekvivalenty:

```Q#
let x = a or b;
let x = Or(a, b);
```