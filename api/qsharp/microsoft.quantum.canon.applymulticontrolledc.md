---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: Operace ApplyMultiControlledC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: bf6b78cd18a827a9a4fd9d61dfd4d240de3503e9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844872"
---
# <a name="applymulticontrolledc-operation"></a>Operace ApplyMultiControlledC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje vynásobení kontrolované verze samostatně kontrolované operace.
Modifikátor `C` označuje, že operace s jedním qubit je ovladatelné.

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Vstup

### <a name="singlycontrolledop--qubit--unit"></a>singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace řízená na jednom qubit.
První qubit v argumentu operace se považuje za ovládací prvek a zbytek se předpokládá jako cílový qubits.
`ApplyMultiControlled` vždy volá `singlyControlledOp` s argumentem délky alespoň 1.


### <a name="ccnot--ccnotop"></a>ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

Nekontrolovaná brána, která se má použít pro konstrukci.


### <a name="controls--qubit"></a>ovládací prvky: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits, na kterém má `singlyControlledOp` být kontrolována.
Délka `controls` musí být aspoň 1.


### <a name="targets--qubit"></a>cíle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Cílová qubits, na které `singlyControlledOp` působí.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Tato operace používá pouze čistě ancilla qubits.

Diagram vysvětlení a okruhu viz obrázek 4,10, část 4,3 v Nielsen & Čuangština

## <a name="references"></a>Reference

- [*Michal a. Nielsen, Petr L. Čuangština*, výpočet doby a informace o tom,](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyMultiControlledCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)