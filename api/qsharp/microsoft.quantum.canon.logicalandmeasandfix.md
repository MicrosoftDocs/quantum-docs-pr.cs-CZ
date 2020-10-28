---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: Operace LogicalANDMeasAndFix
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704032"
---
# <a name="logicalandmeasandfix-operation"></a>Operace LogicalANDMeasAndFix

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vypočítá logickou a více qubits.

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a>Vstup

### <a name="ctrlregister--qubit"></a>ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits vstup do vícenásobného vstupu a brány.


### <a name="target--qubit"></a>cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, na který výstup a se zapisuje. Předpokládá se, že se vždycky spustí ve stavu $ \ket {0} $.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Pokud `ctrlRegister` má přesně $2 $ qubits, jedná se o ekvivalent `CCNOT` operace, ale fáze se fází $e ^ {i \ pi/2} $ v $ \ket {001} $ a $-e ^ {i \ pi/2} $ v $ \ket {101} $ a $ \ket {011} $.
Sousedícít je také metoda měření a opravy, která je inverzní k původní operaci pouze ve zvláštních případech (viz odkazy), ale používá méně T-bran.

## <a name="references"></a>Odkazy

- [*Craig Gidney* , 1709,06648](https://arxiv.org/abs/1709.06648)