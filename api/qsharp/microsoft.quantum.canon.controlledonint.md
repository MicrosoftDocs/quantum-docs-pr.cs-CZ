---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704312"
---
# <a name="controlledonint-function"></a>ControlledOnInt – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vrátí operátor s jednotkou, který používá Oracle v cílovém registru, pokud stav registru ovládacího prvku odpovídá zadanému kladnému celému číslu.

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Kladné celé číslo.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operátor s jednotkou.



## <a name="output--qubitt--unit-adj--ctl"></a>Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Jednotkový operátor, který je použit `oracle` v cílovém registru, pokud stav registru ovládacího prvku odpovídá stavu číslo `numberState` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="remarks"></a>Poznámky

Hodnota `numberState` je interpretována pomocí kódování ve formátu Little endian.