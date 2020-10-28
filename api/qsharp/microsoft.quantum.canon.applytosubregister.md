---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: Operace ApplyToSubregister
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: c9181b8962d36b20f7a9140eb7aaef11aee7faa0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704664"
---
# <a name="applytosubregister-operation"></a>Operace ApplyToSubregister

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje operaci na subregistry registru, kde qubits určil pole jeho indexů.

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--qubit--unit"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která se má použít pro podregistr


### <a name="idxs--int"></a>idxs: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole indexů, která označují, která qubits se operace použije.


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Zaregistrujte, na které operace funguje.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToSubregisterA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [Microsoft. proApplyToSubregisterC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [Microsoft. proApplyToSubregisterCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)