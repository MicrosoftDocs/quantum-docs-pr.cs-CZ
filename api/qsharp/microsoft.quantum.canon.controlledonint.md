---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 6c7f46c44f2a2427f702e463195f26660cb4fca1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840789"
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