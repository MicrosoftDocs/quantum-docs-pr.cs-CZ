---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterCA
title: Operace ApplyToSubregisterCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterCA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 3eb210debf8980f057ed150f647d545f68734459
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704640"
---
# <a name="applytosubregisterca-operation"></a>Operace ApplyToSubregisterCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje operaci na subregistry registru, kde qubits určil pole jeho indexů.
Modifikátor `CA` označuje, že operace je ovladatelné a s sousedními poli.

```qsharp
operation ApplyToSubregisterCA (op : (Qubit[] => Unit is Ctl + Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="op--qubit--unit-ctl--adj"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL a ADJ

Operace, která se má použít pro podregistr


### <a name="idxs--int"></a>idxs: [int](xref:microsoft.quantum.lang-ref.int)[]

Pole indexů, která označují, která qubits se operace použije.


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Zaregistrujte, na které operace funguje.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToSubregister. Canon.](xref:Microsoft.Quantum.Canon.ApplyToSubregister)