---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: Operace CarryOutCoreCDKM
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 19a692a3b54a413f25a474c361e773ab6c65579e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223540"
---
# <a name="carryoutcorecdkm-operation"></a>Operace CarryOutCoreCDKM

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Základní operace v RippleCarryAdderCDKM, která se používá s výše uvedenou operací ApplyOuterCDKMAdder, tj. sdružená s touto operací k získání vnitřní operace RippleCarryAdderCDKM. Tato operace vypočítá qubit a v rámci vstupu aplikuje sekvenci Nebran `ys` .

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

První qubit registrace


### <a name="ys--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Druhý qubit registr.


### <a name="ancilla--qubit"></a>ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Do této operace byla předána ancilla qubit použitá v RippleCarryAdderCDKM.


### <a name="carry--qubit"></a>přenést: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Proveďte qubit v operaci RippleCarryAdderCDKM.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Reference

- Steven A. Cuccaro, Tomáš G. Draper, Samuel A. Kutin, David Petrie Moulton: "nové v rámci Ripple – přenést okruh", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1