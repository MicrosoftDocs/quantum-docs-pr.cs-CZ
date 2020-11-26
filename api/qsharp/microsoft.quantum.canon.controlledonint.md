---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3cc5c00d9c7295106901149e06571ef1963d1323
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207254"
---
# <a name="controlledonint-function"></a>ControlledOnInt – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí operátor s jednotkou, který používá Oracle v cílovém registru, pokud stav registru ovládacího prvku odpovídá zadanému kladnému celému číslu.

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Kladné celé číslo.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Operátor s jednotkou.



## <a name="output--qubitt--unit--is-adj--ctl"></a>Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

Jednotkový operátor, který je použit `oracle` v cílovém registru, pokud stav registru ovládacího prvku odpovídá stavu číslo `numberState` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="remarks"></a>Poznámky

Hodnota `numberState` je interpretována pomocí kódování ve formátu Little endian.