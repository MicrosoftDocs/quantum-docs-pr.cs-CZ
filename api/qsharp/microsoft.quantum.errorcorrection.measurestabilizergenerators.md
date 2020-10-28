---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: Operace MeasureStabilizerGenerators
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: a3f48ff24a39d13a57f7a144e21d4e41bb8a8b49
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697949"
---
# <a name="measurestabilizergenerators-operation"></a>Operace MeasureStabilizerGenerators

Obor názvů: [Microsoft. ErrorCorrection.](xref:Microsoft.Quantum.ErrorCorrection)

Balíček [](https://nuget.org/packages/)


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


### <a name="gadget--pauliqubit--__invalidresult__"></a>gadget: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]; [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __neplatné <Result>__ 

Operace, která určuje, jak změřit multiqubit Pauli operátor.



## <a name="output--syndrome"></a>Výstup: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Výsledek měření

## <a name="remarks"></a>Poznámky

Tato nekontroluje, zda daná sada generátorů dokončí dojíždění.
Pokud se dostanou, výsledek měření může být libovolný.