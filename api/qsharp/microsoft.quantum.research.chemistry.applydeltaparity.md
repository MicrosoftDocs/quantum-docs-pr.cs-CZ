---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Operace ApplyDeltaParity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: 40157b6a166b09c6fee63d86e203f92069d008f1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225750"
---
# <a name="applydeltaparity-operation"></a>Operace ApplyDeltaParity

Obor názvů: [Microsoft. Prohledávejte. Research. chemie](xref:Microsoft.Quantum.Research.Chemistry)

Balíček: [Microsoft. prostudoval. Research. chemie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Počítá rozdíl v paritě mezi předchozím PQRS... výrazy a další PQRS... doby. Tento rozdíl je vypočítán na základě pomocného qubitu.

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="prevfermionicterm--int"></a>prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]

Seznam indexů pro předchozí PQRS... uvedenými.


### <a name="nextfermionicterm--int"></a>nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]

Seznam indexů pro další PQRS... uvedenými.


### <a name="aux--qubit"></a>AUX: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pomocné qubit, na které se ukládají výsledky výpočtů parity.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit se jednalo o všechny PQRS... uvedenými.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Předpokládá se, že indexy P < Q < R < S <... pro prevPQ i pro nextPQ.