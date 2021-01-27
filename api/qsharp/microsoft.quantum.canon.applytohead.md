---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: Operace ApplyToHead
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e627b467e9354e774c2ead8b89ddd3ff3a42ef7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841323"
---
# <a name="applytohead-operation"></a>Operace ApplyToHead

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije operaci na první prvek pole.

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Head(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která se má použít.


### <a name="targets--t"></a>cíle: t []

Pole cílů, na které se první použije `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která má být použita.

## <a name="example"></a>Příklad

Následující fragmenty Q # jsou ekvivalentní:

```qsharp
ApplyToHead(H, register);
H(Head(register));
```

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToHeadA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [Microsoft. proApplyToHeadC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [Microsoft. proApplyToHeadCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)