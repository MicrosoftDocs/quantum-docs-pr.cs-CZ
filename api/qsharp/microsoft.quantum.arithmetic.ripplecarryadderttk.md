---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderTTK
title: Operace RippleCarryAdderTTK
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: cf7f8ed10de2243627a001b770a4d29ff7345f30
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842946"
---
# <a name="ripplecarryadderttk-operation"></a>Operace RippleCarryAdderTTK

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vratný, místní Ripple – přidání dvou celých čísel.
Pomocí dvou $n $ bitových celých čísel zakódovaných v registrech LittleEndian `xs` a `ys` qubit, operace vypočítá součet dvou celých čísel, kde $n $ nejméně významné bity výsledku jsou uchovávány v `ys` a bit, který je XORed na qubit `carry` .

```qsharp
operation RippleCarryAdderTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registruje kódování prvního celého čísla summand.


### <a name="ys--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registruje kódování druhého celého čísla summand, je upraveno tak, aby obsahovalo $n $ nejméně významné bity součtu.


### <a name="carry--qubit"></a>přenést: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Přenese qubit, je XORed s nejvýznamnějším bitem součtu.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Tato operace má stejné funkce jako RippleCarryAdderD a RippleCarryAdderCDKM, ale nepoužívá žádné ancilla qubits.

## <a name="references"></a>Reference

- Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "dopředné a nevázané ventilátory, informace o všech procesorech a výpočet, obj. 10, 2010.
  https://arxiv.org/abs/0910.2530