---
uid: Microsoft.Quantum.Logical.And
title: And – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707064"
---
# <a name="and-function"></a>And – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček [](https://nuget.org/packages/)


Vrátí logickou kombinaci dvou hodnot.

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Vstup

### <a name="a--bool"></a>Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)

První hodnota, která má být považována za.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Druhá hodnota, která má být považována za.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` pouze v případě, že `a` a `b` jsou obojí `true` .

## <a name="remarks"></a>Poznámky

Na rozdíl od `and` operátoru Tato funkce nemá krátký okruh, takže oba vstupy jsou plně vyhodnoceny.

V případě chování až po krátkého okruhu jsou následující ekvivalenty:

```Q#
let x = a and b;
let x = And(a, b);
```