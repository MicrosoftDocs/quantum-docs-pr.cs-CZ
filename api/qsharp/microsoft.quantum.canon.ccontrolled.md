---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: a155b00806b17258b3f87629659bc7d786e4e11d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704409"
---
# <a name="ccontrolled-function"></a>CControlled – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


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