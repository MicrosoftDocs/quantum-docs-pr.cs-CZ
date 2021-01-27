---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: Operace MeasureStabilizerGenerators
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: d7c8df079e49b2ce0a5106e430ef4060df85cdc4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825752"
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