---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: Operace ApplyMultiControlledCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 5662efe0dc6f665206b8773596bf885ce631413c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705193"
---
# <a name="applymulticontrolledca-operation"></a>Operace ApplyMultiControlledCA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje vynásobení kontrolované verze samostatně kontrolované operace.
Modifikátor `CA` označuje, že operace s jedním qubit je ovladatelné a přiléhající.

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a>Vstup

### <a name="singlycontrolledop--qubit--unit-adj"></a>singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ

Operace řízená na jednom qubit.
První qubit v argumentu operace předpokládá, že se jedná o ovládací prvek a že zbytek se považuje za cílový qubits.
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

## <a name="references"></a>Odkazy

- [*Michal a. Nielsen, Petr L. Čuangština* , výpočet doby a informace o tom,](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyMultiControlledC. Canon.](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)