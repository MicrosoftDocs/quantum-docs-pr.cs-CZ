---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Operace Sum
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: e659c77a876e10df75f28ca1798fb0335e1bfb22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847753"
---
# <a name="sum-operation"></a>Operace Sum

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementuje bránu vratného součtu. Má-li bit zakódovaný v qubit `carryIn` a dvě summand bity zakódované v `summand1` a `summand2` , vypočítá logickou XOR `carryIn` `summand1` a `summand2` v qubit `summand2` .

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="carryin--qubit"></a>carryIn: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Provádění qubit.


### <a name="summand1--qubit"></a>summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

First summand qubit.


### <a name="summand2--qubit"></a>summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Druhý summand qubit je nahrazen nižším bitem součtu `summand1` a `summand2` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Na rozdíl od `Carry` operace to nepočítá bit přenosu.