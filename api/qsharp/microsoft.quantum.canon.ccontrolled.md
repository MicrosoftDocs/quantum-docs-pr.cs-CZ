---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: f4d91471eae859b7018c9e7ea0c1c853619c484d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841013"
---
# <a name="ccontrolled-function"></a>CControlled – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


V případě operace op vrátí novou operaci, která použije hodnotu op, pokud je klasický řídicí bit true. Pokud k `false` tomu nedojde, nic se nestane.

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a>Vstup

### <a name="op--t--unit"></a>op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Operace, která se má podmíněně použít



## <a name="output--boolt--unit"></a>Výstup: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit) 

Nová operace, která je op, pokud má klasický řídicí bit hodnotu true.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Vstupní typ operace, která se má podmíněně použít.

## <a name="see-also"></a>Viz také

- [Microsoft. proCControlledC. Canon.](xref:Microsoft.Quantum.Canon.CControlledC)
- [Microsoft. proCControlledA. Canon.](xref:Microsoft.Quantum.Canon.CControlledA)
- [Microsoft. proCControlledCA. Canon.](xref:Microsoft.Quantum.Canon.CControlledCA)