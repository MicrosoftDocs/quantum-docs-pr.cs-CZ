---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: Operace ApplyXControlledOnTruthTableWithCleanTarget
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 904ff7e2e7e81ee966846af120e9427f4e92301c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203259"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a>Operace ApplyXControlledOnTruthTableWithCleanTarget

Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje @"microsoft.quantum.intrinsic.x" operaci na `target` , pokud je logická funkce `func` vyhodnocena jako true pro klasické přiřazení v `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Tato operace implementuje zvláštní případ @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , ve kterém je známý cílový qubit ve stavu $ \ket {0} $.

Implementace využívá @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" brány a.  Implementace sousedících operací se optimalizuje a používá nevýpočetní na základě měření.

## <a name="input"></a>Vstup

### <a name="func--bigint"></a>Func: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Logická tabulka pravdy reprezentovaná jako velké celé číslo


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registrační qubits ovládacího prvku


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Cílový qubit (musí být ve stavu $ \ket {0} $)



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Viz také

- [Microsoft. proshrnutí. ApplyXControlledOnTruthTable](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)