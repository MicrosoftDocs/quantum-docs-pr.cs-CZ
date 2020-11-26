---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverA
title: Operace ApplyOpRepeatedlyOverA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 65675a3a83f0ac730b9e3a58f80f77c096c1ce57
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209141"
---
# <a name="applyoprepeatedlyovera-operation"></a>Operace ApplyOpRepeatedlyOverA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje stejnou operaci op přes qubit registr několikrát.

```qsharp
operation ApplyOpRepeatedlyOverA (op : (Qubit[] => Unit is Adj), targets : Int[][], register : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Vstup

### <a name="op--qubit--unit--is-adj"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace, která se má v registru qubit použít několikrát


### <a name="targets--int"></a>cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []

Vnořená pole popisující cíle pro op. Každé pole by mělo obsahovat seznam čísla popisujících qubits, které se mají použít.


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit registrace, na které se má pracovat.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. proApplySeriesOfOps. Canon.](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)