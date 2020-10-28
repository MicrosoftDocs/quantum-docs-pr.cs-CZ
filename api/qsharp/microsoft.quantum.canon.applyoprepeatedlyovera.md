---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverA
title: Operace ApplyOpRepeatedlyOverA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 2e8ef7e943cfd2c0634f16566a018f386aad659f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705128"
---
# <a name="applyoprepeatedlyovera-operation"></a>Operace ApplyOpRepeatedlyOverA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje stejnou operaci op přes qubit registr několikrát.

```qsharp
operation ApplyOpRepeatedlyOverA (op : (Qubit[] => Unit is Adj), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--qubit--unit-adj"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ

Operace, která se má v registru qubit použít několikrát


### <a name="targets--int"></a>cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []

Vnořená pole popisující cíle pro op. Každé pole by mělo obsahovat seznam čísla popisujících qubits, které se mají použít.


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit registrace, na které se má pracovat.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. proApplySeriesOfOps. Canon.](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)