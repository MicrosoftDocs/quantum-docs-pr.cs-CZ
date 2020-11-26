---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: Operace MeasureStabilizerGenerators
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: 6c048c17df21d1026dc671f30d72a13ed8d8b7f5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200624"
---
# <a name="measurestabilizergenerators-operation"></a>Operace MeasureStabilizerGenerators

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Měří danou sadu generátorů skupiny stabilizace.

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a>Vstup

### <a name="stabilizergroup--pauli"></a>stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Pole operátorů Pauli multiqubit
Například `stabilizerGroup[0]` je seznam matic qubit Pauli, což je tensor produkt, který je generátorem stabilizace.


### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Pole qubits, kde je definován kód stabilizace.


### <a name="gadget--pauliqubit--__invalidresult__"></a>gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[];[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __neplatné <Result>__ 

Operace, která určuje, jak změřit multiqubit Pauli operátor.



## <a name="output--syndrome"></a>Výstup: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Výsledek měření

## <a name="remarks"></a>Poznámky

Tato nekontroluje, zda daná sada generátorů dokončí dojíždění.
Pokud se dostanou, výsledek měření může být libovolný.