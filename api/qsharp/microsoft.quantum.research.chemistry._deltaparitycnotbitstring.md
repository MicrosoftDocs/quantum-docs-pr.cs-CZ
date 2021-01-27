---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 3dd2d299a094577d377780d731e76287815e8d03
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847602"
---
# <a name="_deltaparitycnotbitstring-function"></a>_DeltaParityCNOTbitstring funkce

Obor názvů: [Microsoft. Prohledávejte. Research. chemie](xref:Microsoft.Quantum.Research.Chemistry)

Balíček: [Microsoft. prostudoval. Research. chemie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Krok klasického zpracování `ApplyDeltaParity` .
Tato operace vypočítá seznam qubits ovládacího prvku pro vyhodnocení rozdílu parity mezi dvěma PQRS... stejné délky.

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a>Vstup

### <a name="prevfermionicterm--int"></a>prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="nextfermionicterm--int"></a>nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--intbool"></a>Výstup: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])



## <a name="remarks"></a>Poznámky

To předpokládá, že délka podmínek je sudá.
Vypočítá seznam ovládacích prvků pro rozdíly mezi dvěma podmínkami.
To předpokládá, že vstupní seznamy jsou seřazené ve vzestupném pořadí.