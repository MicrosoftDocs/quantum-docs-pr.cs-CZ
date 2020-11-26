---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Provozovaná operace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 53f8d2a8ba89a912e3d4c08452208a899b2b85de
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223591"
---
# <a name="carry-operation"></a>Provozovaná operace

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementuje bránu vratného přenosu. S ohledem na zakódovaný bit v qubit `carryIn` a dvou summand bitů kódovaný v `summand1` a `summand2` , vypočítá logickou XOR `carryIn` , `summand1` a `summand2` v qubit `summand2` a přenese XORed na qubit `carryOut` .

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="carryin--qubit"></a>carryIn: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Provádění qubit.


### <a name="summand1--qubit"></a>summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

First summand qubit.


### <a name="summand2--qubit"></a>summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Druhý summand qubit je nahrazen nižším bitem součtu `summand1` a `summand2` .


### <a name="carryout--qubit"></a>vykonání: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit se bude XORed s vyšším bitem součtu.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

