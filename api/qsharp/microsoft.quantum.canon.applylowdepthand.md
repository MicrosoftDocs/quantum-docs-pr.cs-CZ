---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: Operace ApplyLowDepthAnd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 7fa9d9bf2f1905bf1b59e783d7bceb8cb2e09fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841709"
---
# <a name="applylowdepthand-operation"></a>Operace ApplyLowDepthAnd

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Invertuje daný cílový qubit, pokud je a pouze v případě, že oba ovládací prvky qubits jsou v 1 stavu s T-hloubkou 1, pomocí měření k provedení sousedící operace.

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Popis

Invertuje `target` pouze v případě, že jsou oba ovládací prvky 1, ale předpokládá, že `target` je ve stavu 0.  Operace má T-Count 4, T-Depth 1 a vyžaduje jeden pomocný qubit a může proto být vhodnější pro operaci CCNOT, pokud `target` je známo, že má hodnotu 0.  Sousední funkce této operace měří na základě měření a nevyžaduje žádné brány T a žádné pomocné qubity.

## <a name="input"></a>Vstup

### <a name="control1--qubit"></a>Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit prvního ovládacího prvku


### <a name="control2--qubit"></a>Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Druhý qubit ovládacího prvku


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Cílová pomocná qubit; musí být ve stavu 0.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Reference

- Cody Novotný: "nové konstrukce pro bránu Toffoli odolné proti chybám", fyz. rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) doi: 10.1103/PhysRevA. 87.022328
- Petra Selinger: "okruhy T-Depth One", fyz. A 87, 042302, 2013 [arXiv: 1210.0974](https://arxiv.org/abs/1210.0974) doi: 10.1103/PhysRevA. 87.042302