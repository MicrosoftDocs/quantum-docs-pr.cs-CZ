---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Operace ApplyControlledOnInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3dd17e6bc913e84941a6b81f134e60536a4c4122
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219001"
---
# <a name="applycontrolledonint-operation"></a>Operace ApplyControlledOnInt

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplikuje jednotnou operaci v cílovém registru, pokud stav registru ovládacího prvku odpovídá zadanému kladnému celému číslu.

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Vstup

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Nezáporné celé číslo, na kterém `oracle` by měla být operace řízena.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL

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