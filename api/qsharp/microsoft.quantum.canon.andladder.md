---
uid: Microsoft.Quantum.Canon.AndLadder
title: Operace AndLadder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 05a0e8110539742501883fea75ac368d9946164d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705520"
---
# <a name="andladder-operation"></a>Operace AndLadder

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Provede řízený "a žebřík" v registru cílového qubits.

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="description"></a>Popis

Tato operace používá transformaci popsanou následujícím mapováním výpočetního základu, $ $ \begin{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \dots, y \_ {n-1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2), \dots, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}, \end{align} $ $ WHERE $ \ket{x \_ 1, \dots, x \_ n} $ odkazuje na výpočetní stavy na bázi `controls` a kde $ \ket{y \_ 1, \dots, y \_ {n-1}} $ odkazuje na výpočetní stavy pro `targets` .

## <a name="input"></a>Vstup

### <a name="ccnot--ccnotop"></a>ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

Brána CCNOT, která se má použít pro konstrukci


### <a name="controls--qubit"></a>ovládací prvky: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registr qubits, který se má použít jako ovládací prvky pro žebřík a.
Tato operace opouští výpočetní základní stav `controls` invariantní.
Délka `controls` musí být alespoň 2 a musí být rovna jedné hodnotě plus délka `targets` .


### <a name="targets--qubit"></a>cíle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Délka `targets` musí být alespoň 1 a rovná se délce `controls` minus jedna.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

- Používá se jako součást <xref:microsoft.quantum.canon.applymulticontrolledc> a <xref:microsoft.quantum.canon.applymulticontrolledca> .
- Diagram vysvětlení a okruhu viz obrázek 4,10, část 4,3 v Nielsen & Čuangština.

## <a name="references"></a>Odkazy

- [*Michal a. Nielsen, Petr L. Čuangština* , výpočet doby a informace o tom,](http://doi.org/10.1017/CBO9780511976667)