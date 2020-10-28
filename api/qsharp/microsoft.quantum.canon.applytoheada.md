---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: Operace ApplyToHeadA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: ba060243cb01782fd8529e0b05ee7258a66314f5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704792"
---
# <a name="applytoheada-operation"></a>Operace ApplyToHeadA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Použije operaci na první prvek pole.

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Head(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit-adj"></a>op: t => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)

Operace, která se má použít.


### <a name="targets--t"></a>cíle: t []

Pole cílů, na které se první použije `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která má být použita.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToHead. Canon.](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [Microsoft. proApplyToHeadC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [Microsoft. proApplyToHeadCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)