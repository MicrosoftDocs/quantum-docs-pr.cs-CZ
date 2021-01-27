---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Operace ApplyDeltaParity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: f5f1d74274994f042f1bc3f2e0d5332f504be02c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851100"
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