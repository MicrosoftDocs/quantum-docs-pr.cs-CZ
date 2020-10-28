---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704400"
---
# <a name="ccontrolledca-function"></a>CControlledCA – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


V případě operace op vrátí novou operaci, která použije hodnotu op, pokud je klasický řídicí bit true. Pokud k `false` tomu nedojde, nic se nestane.
Modifikátor `CA` označuje, že operace je ovladatelné a s sousedními poli.

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a>Vstup

### <a name="op--t--unit-ctl--adj"></a>op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL a ADJ

Operace, která se má podmíněně použít



## <a name="output--boolt--unit-ctl--adj"></a>Výstup: ([bool](xref:microsoft.quantum.lang-ref.bool), t) [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ

Nová operace, která je op, pokud má klasický řídicí bit hodnotu true.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která se má podmíněně použít.

## <a name="see-also"></a>Viz také

- [Microsoft. proCControlled. Canon.](xref:Microsoft.Quantum.Canon.CControlled)