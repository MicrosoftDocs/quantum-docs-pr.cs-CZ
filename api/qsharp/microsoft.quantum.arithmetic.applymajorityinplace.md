---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Operace ApplyMajorityInPlace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: c32d7546fb753f78a72479cec11a6ed09c5e6179
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190730"
---
# <a name="applymajorityinplace-operation"></a>Operace ApplyMajorityInPlace

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje operaci se třemi qubity na místě v registru qubits.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Tato operace vypočítá funkci většina místa na 3 qubits.

Pokud si vyhledáme výstup qubit jako $z $ a vstupní qubits jako $x $ a $y $, operace provede následující transformaci: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{maj} (x, y, z)} $.

## <a name="input"></a>Vstup

### <a name="output--qubit"></a>výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)

První vstupní qubit Všimněte si, že výstup je vypočítán místně a je uložený v tomto qubit.


### <a name="input--qubit"></a>vstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Druhé a třetí vstupní qubits.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

