---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 7bad044db9e2229c85cb3909dc4802bceaee6382
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847291"
---
# <a name="modulusi-function"></a>ModulusI – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vypočítá kanonický zbytek `value` modulo `modulus` .

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a>Vstup

### <a name="value--int"></a>hodnota: [int](xref:microsoft.quantum.lang-ref.int)

Hodnota, kterou je vypočítáno reziduum


### <a name="modulus--int"></a>Modulus: [int](xref:microsoft.quantum.lang-ref.int)

Zbytky, podle kterých jsou zbytky vzaty, musí být kladné



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Celé číslo $r $ mezi 0 a `modulus - 1` to `value - r` je dělitelé modulem.

## <a name="remarks"></a>Poznámky

Tato funkce se chová jinak, než se operátor `%` chová v jazyce C# a Q #, protože ve výsledku je vždy nezáporné celé číslo mezi 0 a `modulus - 1` , i když je hodnota záporná.