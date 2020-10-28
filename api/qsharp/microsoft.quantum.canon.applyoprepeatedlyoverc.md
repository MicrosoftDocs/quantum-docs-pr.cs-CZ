---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverC
title: Operace ApplyOpRepeatedlyOverC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverC
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: effd61e6c012dcf81a83383c3fd43cf745d18117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705120"
---
# <a name="applyoprepeatedlyoverc-operation"></a>Operace ApplyOpRepeatedlyOverC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje stejnou operaci op přes qubit registr několikrát.

```qsharp
operation ApplyOpRepeatedlyOverC (op : (Qubit[] => Unit is Ctl), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--qubit--unit-ctl"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = seznam Ctl pro> [jednotku](xref:microsoft.quantum.lang-ref.unit)

Operace, která se má v registru qubit použít několikrát


### <a name="targets--int"></a>cíle: [int](xref:microsoft.quantum.lang-ref.int)[] []

Vnořená pole popisující cíle pro op. Každé pole by mělo obsahovat seznam čísla popisujících qubits, které se mají použít.


### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit registrace, na které se má pracovat.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. proApplySeriesOfOps. Canon.](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)