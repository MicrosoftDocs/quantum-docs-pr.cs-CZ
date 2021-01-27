---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: Operace ApplyToTailA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 5ca22be7a38d466f9413977de663f10606171dea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841170"
---
# <a name="applytotaila-operation"></a>Operace ApplyToTailA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije operaci na poslední prvek pole.

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Tail(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit--is-adj"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace, která se má použít.


### <a name="targets--t"></a>cíle: t []

Pole cílů, z nichž poslední bude použito `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která má být použita.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToTail. Canon.](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [Microsoft. proApplyToTailC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [Microsoft. proApplyToTailCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToTailCA)