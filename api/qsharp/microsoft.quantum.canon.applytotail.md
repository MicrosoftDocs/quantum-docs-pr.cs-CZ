---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: Operace ApplyToTail
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 077e6dedee68b0bd05a668387b22f8bec87a4041
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850438"
---
# <a name="applytotail-operation"></a>Operace ApplyToTail

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Použije operaci na poslední prvek pole.

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Popis

Daná operace `op` a pole cílů `targets` platí `op(Tail(targets))` .

## <a name="input"></a>Vstup

### <a name="op--t--unit"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která se má použít.


### <a name="targets--t"></a>cíle: t []

Pole cílů, z nichž poslední bude použito `op` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která má být použita.

## <a name="example"></a>Příklad

Následující fragmenty Q # jsou ekvivalentní:

```qsharp
ApplyToTail(H, register);
H(Tail(register));
```

## <a name="see-also"></a>Viz také

- [Microsoft. proApplyToTailA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [Microsoft. proApplyToTailC. Canon.](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [Microsoft. proApplyToTailCA. Canon.](xref:Microsoft.Quantum.Canon.ApplyToTailCA)