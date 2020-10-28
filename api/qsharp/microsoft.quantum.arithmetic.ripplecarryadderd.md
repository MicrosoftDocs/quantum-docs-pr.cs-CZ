---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: Operace RippleCarryAdderD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: c4466feebb8ff6afcdcb5bf385ec10e807c00537
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706256"
---
# <a name="ripplecarryadderd-operation"></a>Operace RippleCarryAdderD

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček [](https://nuget.org/packages/)


Vratný, místní Ripple – přidání dvou celých čísel.
Pomocí dvou $n $ bitových celých čísel zakódovaných v registrech LittleEndian `xs` a `ys` qubit, operace vypočítá součet dvou celých čísel, kde $n $ nejméně významné bity výsledku jsou uchovávány v `ys` a bit, který je XORed na qubit `carry` .

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
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

Určená řízená operace využívá symetrii a vzájemné rušení operací pro zlepšení výchozí implementace, která přidává ovládací prvek ke každé operaci.

## <a name="references"></a>Odkazy

- Tomáš G. Draper: "Přihlaste se na počítač s více počítači a 2000.
  https://arxiv.org/abs/quant-ph/0008033