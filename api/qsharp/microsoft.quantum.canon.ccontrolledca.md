---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 740461ee17bdda281a6bd8572a15d27b17be9535
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840960"
---
# <a name="ccontrolledca-function"></a>CControlledCA – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


V případě operace op vrátí novou operaci, která použije hodnotu op, pokud je klasický řídicí bit true. Pokud k `false` tomu nedojde, nic se nestane.
Modifikátor `CA` označuje, že operace je ovladatelné a s sousedními poli.

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a>Vstup

### <a name="op--t--unit--is-adj--ctl"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Operace, která se má podmíněně použít



## <a name="output--boolt--unit--is-adj--ctl"></a>Výstup: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Nová operace, která je op, pokud má klasický řídicí bit hodnotu true.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která se má podmíněně použít.

## <a name="see-also"></a>Viz také

- [Microsoft. proCControlled. Canon.](xref:Microsoft.Quantum.Canon.CControlled)