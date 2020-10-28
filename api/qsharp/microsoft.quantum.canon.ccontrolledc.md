---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704401"
---
# <a name="ccontrolledc-function"></a>CControlledC – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


V případě operace op vrátí novou operaci, která použije hodnotu op, pokud je klasický řídicí bit true. Pokud k `false` tomu nedojde, nic se nestane.
Modifikátor `C` označuje, že operace je ovladatelné.

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a>Vstup

### <a name="op--t--unit-ctl"></a>op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL

Operace, která se má podmíněně použít



## <a name="output--boolt--unit-ctl"></a>Výstup: ([bool](xref:microsoft.quantum.lang-ref.bool), t) = seznam CTL>ch [jednotek](xref:microsoft.quantum.lang-ref.unit)

Nová operace, která je op, pokud má klasický řídicí bit hodnotu true.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která se má podmíněně použít.

## <a name="see-also"></a>Viz také

- [Microsoft. proCControlled. Canon.](xref:Microsoft.Quantum.Canon.CControlled)