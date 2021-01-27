---
uid: Microsoft.Quantum.Logical.Xor
title: XOR – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: 4a4af7f628ca64170e046584d9caffe7ceee3d56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848453"
---
# <a name="xor-function"></a>XOR – funkce

Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí logickou nevýlučnou disjunkci dvou hodnot.

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Vstup

### <a name="a--bool"></a>Odpověď: [bool](xref:microsoft.quantum.lang-ref.bool)

První hodnota, která má být považována za.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Druhá hodnota, která má být považována za.



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` IF a je pouze v případě, že právě jedna z `a` a `b` je `true` .