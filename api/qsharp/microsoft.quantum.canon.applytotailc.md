---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: Operace ApplyToTailC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 8408dff24c5c57efbedb649ac182fac49e836a3e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850417"
---
# <a name="applytotailc-operation"></a>Operace ApplyToTailC

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije operaci na poslední prvek pole.

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Tail(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit--is-ctl"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL

Operace, která se má použít.


### <a name="targets--t"></a>cíle: t []

Pole cílů, z nichž poslední bude použito `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která má být použita.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToTail. Canon.](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [Microsoft. proApplyToTailA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [Microsoft. proApplyToTailCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToTailCA)