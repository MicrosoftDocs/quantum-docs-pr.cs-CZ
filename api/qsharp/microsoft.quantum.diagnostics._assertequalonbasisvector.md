---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: operace _assertEqualOnBasisVector
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: d8f2195f75de49918032053dc8d1fa4fb4eba840
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213765"
---
# <a name="_assertequalonbasisvector-operation"></a>operace _assertEqualOnBasisVector

Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Kontroluje, zda je výsledek použití dvou operací `givenU` a `expectedU` na základní stav stejný. Základní stav je popsán podle `basis` parametru.
<xref:microsoft.quantum.extensions.fliptobasis>Další podrobnosti o tomto popisu najdete v tématu funkce.

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Vstup

### <a name="basis--int"></a>Základna: [int](xref:microsoft.quantum.lang-ref.int)[]

Základní stav určený ID stavu s jednou qubit (0 <= ID <= 3) pro každý $n $ qubits.


### <a name="givenu--qubit--unit"></a>předané: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Bude zkontrolována operace na $n $ qubits.


### <a name="expectedu--qubit--unit--is-adj"></a>očekává se: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace reference na $n $ qubits, která má být porovnána s.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)

