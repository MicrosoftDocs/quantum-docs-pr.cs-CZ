---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Operace ApplyControlledOnInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705432"
---
# <a name="applycontrolledonint-operation"></a>Operace ApplyControlledOnInt

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Aplikuje jednotnou operaci v cílovém registru, pokud stav registru ovládacího prvku odpovídá zadanému kladnému celému číslu.

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>Vstup

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Nezáporné celé číslo, na kterém `oracle` by měla být operace řízena.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Jednotná operace, která se má řídit.


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Každé z nich registruje registraci řízení aplikací `oracle` .


### <a name="targetregister--t"></a>targetRegister: 'T

Registrace, na které se má použít `oracle` .



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S



## <a name="remarks"></a>Poznámky

Hodnota `numberState` je interpretována pomocí kódování ve formátu Little endian.

`numberState` musí být maximálně $2 ^ \texttt{Length (controlRegister)}-$1.
Například `numberState = 537` to znamená, že `oracle` se použije pouze v případě, že `controlRegister` je ve stavu $ \ket {537} $.