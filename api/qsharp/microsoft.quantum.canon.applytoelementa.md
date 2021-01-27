---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Operace ApplyToElementA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 57d870c7fbd099212b13f75bd85e57c046280d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850771"
---
# <a name="applytoelementa-operation"></a>Operace ApplyToElementA

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije operaci na daný prvek pole.

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>Popis

Pro danou operaci se `op` použije index `index` a pole cílů `targets` `op(targets[index])` .

## <a name="input"></a>Vstup

### <a name="op--t--unit--is-adj"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.

Operace, která se má použít.


### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)

Index do pole cílů.


### <a name="targets--t"></a>cíle: t []

Pole možných cílů pro `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která má být použita.

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToElement. Canon.](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [Microsoft. proApplyToElementC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [Microsoft. proApplyToElementCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToElementCA)